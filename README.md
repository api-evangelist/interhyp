# Interhyp

Interhyp AG is Germany's leading platform for residential mortgage financing (Baufinanzierung), comparing offers from 500+ loan partners. It is part of ING Group and runs the broker brand Prohyp.

Through its Developer Studio ([developer.ehyphome.de](https://developer.ehyphome.de/)) Interhyp publishes partner-facing REST APIs — the **Submission API** (financing applications, applicants, estates, households, financial standings, offers, submissions, logbooks, commands, pre-submission checks) and the **Submission Documents API** — secured with OAuth 2.0 JWT bearer tokens plus an Api-Key header, using cursor pagination, RFC 7807 problem+json errors, and a `traceId` for support correlation.

Source: added to the API Evangelist network as a portfolio company of earlybird (fintech), then enriched from the public developer portal and the [Interhyp GitHub org](https://github.com/Interhyp).

## Artifacts
- `openapi/` — Submission API (v6.10.0) + Submission Documents API OpenAPI 3.0 specs
- `authentication/`, `conventions/`, `errors/`, `lifecycle/`, `conformance/`, `data-model/`
- `mcp/` — candidate MCP tool list derived from operations
- `skills/` — agent skills for reading a financing application and managing a submission
- `sandbox/`, `changelog/`, `packages/`, `overlays/`, `security/`, `well-known/`, `llms/`

Backed by: earlybird
