---
name: Verify a user's identity with the Interac Hub
description: >-
  Run the Interac Hub Verification Service OAuth 2.0 / OpenID Connect flow to
  obtain verified identity claims for a user, via financial-institution
  authentication (IVS), government-ID + selfie (IDVS), or both.
api: Interac Hub Verification API
source: https://documents.hub-verify.innovation.interac.ca/docs/quick-start-guide
operations:
- 'GET /auth (authorization_endpoint)'
- 'POST /auth/par (pushed_authorization_request_endpoint)'
- 'POST /oauth2/token (token_endpoint)'
- 'GET /userinfo (userinfo_endpoint)'
- 'GET /.well-known/openid-configuration'
---

# Verify a user's identity with the Interac Hub

The Interac Hub is an OAuth 2.0 / OpenID Connect (Authorization Code Grant) API.
It returns verified identity claims sourced from a Canadian financial institution
(Interac Verification Service, **IVS**) and/or a scanned government ID plus a live
selfie (Interac Document Verification Service, **IDVS**). All endpoints are OAuth/
OIDC endpoints — there is no REST resource surface.

## Prerequisites (from partner onboarding)
- **OIDC Client ID** — sent on every Hub request.
- **OIDC scope** — the pre-configured product scope for your flow (see below).
- **OIDC well-known URL** — `https://gateway-portal.hub-verify.innovation.interac.ca/.well-known/openid-configuration`.
- **Redirect URI(s)** — where the user returns after verification.
- **Your JWKS URL** — hosts your public RS256 signing key; used to verify your
  signed request objects and `private_key_jwt` client assertions.

## Choose a scope (always prefixed with `openid`)
- `openid onlyVme_scope` — IVS only (financial-institution selection screen).
- `openid document_scope` — IDVS only (document + selfie scan).
- `openid general_scope` — let the user pick IVS or IDVS.
- `openid dual_scope` — IVS then IDVS, with match scores between the two.

## Flow
1. **Discover endpoints** — `GET /.well-known/openid-configuration`. Do not
   hard-code endpoint URLs; re-query periodically (they may change).
2. **Push the authorization request** — `POST /auth/par` with your signed JWT
   request object (client_id, redirect_uri, scope, state, nonce). Prefer PAR over
   putting the request object on the front channel. You receive a `request_uri`.
3. **Send the user to authorize** — redirect to `GET /auth` with the `request_uri`
   from step 2. The user completes IVS/IDVS. On success you get an authorization
   `code` back at your redirect URI (with the same `state`).
4. **Exchange the code** — `POST /oauth2/token` with `grant_type=authorization_code`,
   the `code`, and a `private_key_jwt` client assertion. Receive an access token
   (and a refresh token if you requested `offline_access`).
5. **Fetch verified claims** — `GET /userinfo` with the bearer access token. IVS
   returns `"source": "bank"`; IDVS returns `"source": "driving_licence"` with
   `doc_type`, `scan_result`, validity dates, and identity claims. `dual_scope`
   returns both plus match scores (populated when both complete with `CLEAR`).
6. **Retain identifiers** — store the returned `license_id` / `job_id` for
   **7 years** alongside non-PII transaction metadata (per Interac's retention
   policy) to support later investigation of unauthorized transactions.

## Error handling
- Authorization errors come back on the redirect as
  `?error=&error_description=&locale=&state=` (RFC 6749 4.1.2.1). Common codes:
  `access_denied` (user cancelled / verification failed), `session_expired`.
- Token/UserInfo errors are JSON `{error, error_description}`: `invalid_grant`
  (bad/expired code or refresh token → restart authorization), `invalid_token`
  (expired access token → refresh and retry), `request_unauthorized`.
- IDVS `access_denied` carries `Document S` (suspected) or `Document R` (rejected).
- Always implement a fallback for unrecognized codes and give the user a next step.

See `authentication/interac-authentication.yml`, `scopes/interac-scopes.yml`, and
`errors/interac-problem-types.yml` for the full auth, scope, and error contracts.
