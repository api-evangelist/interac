# Interac (interac)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

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
