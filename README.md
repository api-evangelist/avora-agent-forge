# AVORA Agent Forge (avora-agent-forge)

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
