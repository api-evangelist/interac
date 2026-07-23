# Interac (interac)

Interac Corp. is Canada's domestic payments and digital verification network, founded in 1984 (as the Interac Association) and reorganized as a for-profit corporation in 2018. Owned by a consortium of Canadian financial institutions and payment processors and headquartered in Toronto, Interac is shared national payment infrastructure — not a chartered bank — operating Interac Debit, Interac e-Transfer, and Interac verification / digital identity services across 300+ connected financial institutions.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/interac/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/interac/refs/heads/main/apis.yml)

## Open Finance Posture

Canada has no operational open-banking mandate yet — the federal Consumer-Driven Banking framework (Budget 2024 / Fall Economic Statement 2024, overseen by the FCAC) is legislated but not yet live, so access remains voluntary. Interac is one of the core Canadian rails, alongside Payments Canada. It runs the **Interac Innovation Hub** developer program ([innovation.interac.ca](https://innovation.interac.ca/)). The most openly documented public API surface is the **Interac Hub Verification Service**, an HTTP identity-verification API built on OAuth 2.0 / OpenID Connect (Authorization Code Grant with Pushed Authorization Requests), with a self-serve developer sandbox. Full production access and other products (Business Request Money, Interac Direct) are partner-gated behind a commercial relationship with an issuing financial institution. No first-party FDX or 1033-style data-access API is published; the Hub Verification API's public OpenID Connect discovery document is live and machine-readable.

## Tags

- Financial Services
- Payments
- Canada
- Interac
- Digital Identity
- Verification
- Open Banking
- Consumer-Driven Banking
- Infrastructure

## Timestamps

- **Created:** 2026-07-23
- **Modified:** 2026-07-23

## APIs

### Interac Hub Verification API

The Interac Hub is an HTTP API that simplifies digital identity verification. Relying parties obtain verified identity data through financial-institution authentication (Interac Verification Service, IVS) and/or government-ID plus biometric selfie checks (Interac Document Verification Service, IDVS). It uses the OAuth 2.0 / OpenID Connect 1.0 Authorization Code Grant flow with Pushed Authorization Requests, and offers a self-serve developer sandbox.

- **Human URL:** [https://documents.hub-verify.innovation.interac.ca/docs/overview](https://documents.hub-verify.innovation.interac.ca/docs/overview)
- **Base URL:** `https://gateway-portal.hub-verify.innovation.interac.ca`

#### Tags

- Digital Identity
- Verification
- OpenID Connect
- KYC

#### Properties

- [Documentation](https://documents.hub-verify.innovation.interac.ca/docs/welcome)
- [Documentation](https://documents.hub-verify.innovation.interac.ca/docs/overview)
- [API Reference](https://documents.hub-verify.innovation.interac.ca/docs/31-api-endpoints)
- [Quick Start Guide](https://documents.hub-verify.innovation.interac.ca/docs/quick-start-guide)
- [OpenID Connect Discovery](https://gateway-portal.hub-verify.innovation.interac.ca/.well-known/openid-configuration)

## Common Properties

- [Website](https://www.interac.ca/)
- [Developer Portal](https://innovation.interac.ca/)
- [Documentation](https://documents.hub-verify.innovation.interac.ca/docs/welcome)
- [GitHub Organization](https://github.com/Interac)
- [LinkedIn](https://www.linkedin.com/company/interac-corp/)
- [Blog / News](https://www.interac.ca/en/content-category/news/)
- [Privacy Policy](https://www.interac.ca/en/privacy/)
- [Terms of Service](https://www.interac.ca/en/legal/)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
