# AVORA Agent Forge (avora-agent-forge)

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

AVORA Agent Forge is an evidence-first Solana SPL token risk scanner and public AI interoperability service built for humans, wallets, and autonomous agents. It publishes two OpenAPI 3.1 REST APIs, a hosted streamable-HTTP MCP server whose tools/list responds anonymously with eleven fully-schemad tools, and an A2A agent card with three published skills. Every operation is unauthenticated: there are no accounts, no API keys, and no OAuth. Paid tiers are gated instead by non-custodial, user-signed Solana Pay (USDC) settlement verified on-chain, where the payment reference doubles as the idempotency key. Public-sector assessments return Ed25519 JWS receipts that any third party can verify offline against a published JWKS, and the service ships a voluntary NIST AI RMF alignment profile that explicitly disclaims certification and government approval and requires human review.

**APIs.json:** [https://avora-agent-forge.apievangelist.com/apis.yml](https://avora-agent-forge.apievangelist.com/apis.yml)

## Tags

- Blockchain
- Crypto
- Solana
- Token Risk
- Due Diligence
- On-chain Evidence
- Fraud Intelligence
- AI Agents
- MCP
- A2A
- Signed Receipts
- Provenance
- Non-custodial Payments
- USDC
- Solana Pay
- Public-sector AI Interoperability

## Timestamps

- **Created:** 2026-07-30
- **Modified:** 2026-08-09

## APIs

### AVORA Agent Forge MCP Server

Hosted streamable-HTTP MCP server exposing eleven tools across scanning, offers, Solana Pay ordering, settlement verification, and aggregate commerce telemetry. tools/list responds 200 anonymously with a full JSON Schema inputSchema and MCP annotations per tool.

- **Human URL:** [https://avora-agent-forge.netlify.app/ai/](https://avora-agent-forge.netlify.app/ai/)
- **Base URL:** `https://avora-agent-forge.netlify.app/mcp`

#### Tags

- MCP
- AI Agents
- Solana

#### Properties

- [M C P Server](mcp/avora-agent-forge-mcp.yml)
- [Tool Crosswalk](mcp/avora-agent-forge-tool-crosswalk.yml)
- [Documentation](https://avora-agent-forge.netlify.app/ai/)
- [Postman Collection](collections/avora-agent-forge-agent-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/avora-agent-forge-agent-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Postman Collection](collections/avora-agent-forge-public-evidence-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/avora-agent-forge-public-evidence-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### AVORA Agent Forge Agent API

The Agent API from AVORA Agent Forge — 5 operation(s) for agent.

- **Human URL:** [https://avora-agent-forge.netlify.app/agent-forge/](https://avora-agent-forge.netlify.app/agent-forge/)
- **Base URL:** `https://avora-agent-forge.netlify.app`

#### Tags

- Agent

#### Properties

- [OpenAPI](openapi/avora-agent-forge-agent-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/avora-agent-forge-agent-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/avora-agent-forge-agent-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Documentation](https://avora-agent-forge.netlify.app/agent-forge/)
- [Documentation](https://avora-agent-forge.netlify.app/public-sector/)

### AVORA Agent Forge Public Evidence API

Public-data token evidence with mandatory human-review controls.

- **Human URL:** [https://avora-agent-forge.netlify.app/agent-forge/](https://avora-agent-forge.netlify.app/agent-forge/)
- **Base URL:** `https://avora-agent-forge.netlify.app`

#### Tags

- Public Evidence

#### Properties

- [OpenAPI](openapi/avora-agent-forge-public-evidence-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/avora-agent-forge-public-evidence-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/avora-agent-forge-public-evidence-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Documentation](https://avora-agent-forge.netlify.app/agent-forge/)
- [Documentation](https://avora-agent-forge.netlify.app/public-sector/)

## Common Properties

- [Developer Portal](https://avora-agent-forge.netlify.app/agent-forge/)
- [Documentation](https://avora-agent-forge.netlify.app/agent-forge/)
- [API Reference](https://avora-agent-forge.netlify.app/agent-forge/openapi.json)
- [Getting Started](https://avora-agent-forge.netlify.app/ai/)
- [Pricing](https://avora-agent-forge.netlify.app/agent-forge/pricing.json)
- [Plans](plans/avora-agent-forge-plans.yml)
- [M C P Server](mcp/avora-agent-forge-mcp.yml)
- [Tool Crosswalk](mcp/avora-agent-forge-tool-crosswalk.yml)
- [Agent Card](a2a/avora-agent-forge-a2a.yml)
- [Agent Skill](skills/_index.yml)
- [Agentic Access](agentic-access/avora-agent-forge-agentic-access.yml)
- [L L Ms Txt](llms/avora-agent-forge-llms.txt)
- [Well Known](well-known/avora-agent-forge-well-known.yml)
- [Authentication](authentication/avora-agent-forge-authentication.yml)
- [Conventions](conventions/avora-agent-forge-conventions.yml)
- [Idempotency](conventions/avora-agent-forge-conventions.yml)
- [Error Catalog](errors/avora-agent-forge-problem-types.yml)
- [Lifecycle](lifecycle/avora-agent-forge-lifecycle.yml)
- [Conformance](conformance/avora-agent-forge-conformance.yml)
- [Data Model](data-model/avora-agent-forge-data-model.yml)
- [Domain Security](security/avora-agent-forge-domain-security.yml)
- [JSON-LD](json-ld/avora-agent-forge-catalog.jsonld) — [JSON-LD](https://www.w3.org/TR/json-ld11/)
- [Overlay](overlays/avora-agent-forge-commerce-overlay.yaml)
- [Overlay](overlays/avora-agent-forge-public-sector-overlay.yaml)

## Maintainers

**FN:** AVORA Agent Forge
**URL:** https://avora-agent-forge.netlify.app/
