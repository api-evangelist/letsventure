# LVX (formerly LetsVenture)

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
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

LVX — formerly LetsVenture — is an India-based private market investing platform founded in 2013 by Shanti Mohan and headquartered in Bengaluru, with teams in Delhi and Mumbai. It connects startup founders raising capital with angel investors, family offices and VCs, and has been a SEBI-regulated entity since its Angel AIF was approved in 2018.

Products: **LVX start** (early-stage angel investing), **LVX grow** (growth-stage and co-investment), **LVXschool** (investor education), **LVX Debt** (non-dilutive debt financing) and **LVX Track** (portfolio dashboards), alongside the sister platform [trica](https://www.trica.co).

Backed by: accel — https://lvxventures.com

## Enrichment findings (2026-07-19)

- **Rebrand.** `letsventure.com` now **301-redirects to `lvxventures.com`**. The company announced the LetsVenture → LVX rebrand on 2025-07-09.
- **No public API program.** No developer portal, API reference, OpenAPI/Swagger definition, SDKs, CLI, MCP server, webhooks or Postman collection were found. `api.`/`developer.`/`docs.letsventure.com` do not resolve.
- **Private platform API discovered.** `api.lvxventures.com` is live: a Python/ASGI (`uvicorn`) service returning `401` with `WWW-Authenticate: Token`, a versioned `/v1/` path behind auth, and `/health` → `200`. No public spec is served (`/openapi.json`, `/docs`, `/redoc`, `/api/schema/` all `404`). Captured in `authentication/`.
- **llms.txt published.** `https://lvxventures.com/llms.txt` returns `200` — a genuine, auto-generated full-site dump (1.4 MB). Saved verbatim to `llms/`.
- **No `.well-known` surface.** Every probed discovery document returns `404` on all hosts — recorded in `well-known/`.
- **No vulnerability-disclosure program or trust center** found by probe.
- **Domain security probed**: TLS 1.3, HSTS (max-age 31536000), SPF and DMARC (`quarantine`) present; **no DNSSEC, no CAA**.

## Artifacts

| Dir | File | Method |
|---|---|---|
| `llms/` | `letsventure-llms.txt` | searched (verbatim `/llms.txt`) |
| `well-known/` | `letsventure-well-known.yml` | searched (all 404 — negative result) |
| `security/` | `letsventure-domain-security.yml` | probed |
| `authentication/` | `letsventure-authentication.yml` | probed (private, undocumented) |

Artifact types that require a public OpenAPI or a published developer surface — `openapi/`, `mcp/`, `skills/`, `overlays/`, `packages/`, `sandbox/`, `conventions/`, `changelog/`, `cli/`, `components/`, `data-model/`, `errors/`, `scopes/`, `conformance/`, `lifecycle/`, `asyncapi/`, `grpc/` — were **skipped rather than fabricated**: LVX publishes none of them.
