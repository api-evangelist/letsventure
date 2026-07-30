# LVX (formerly LetsVenture)

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
