# Interhyp

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
