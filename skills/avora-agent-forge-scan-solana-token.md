---
name: Scan a Solana token for risk
description: >-
  Run a free, unauthenticated risk preview on one Solana SPL token mint and report the
  findings to a human without acting on them.
api: openapi/avora-agent-forge-commerce-openapi.json
operations:
  - scanSolanaTokenFree
mcp_tool: scan_solana_token
generated: '2026-08-09'
method: generated
source: openapi/avora-agent-forge-commerce-openapi.json + mcp/avora-agent-forge-tools-list.json
---

# Scan a Solana token for risk

Free, no credential required. Use this before recommending any paid tier.

## Prerequisites

None. There is no API key, no account, and no OAuth. All operations are anonymous.

## Steps

1. **Validate the mint before you call.** The `mint` must be a base58 Solana SPL token
   mint matching `^[1-9A-HJ-NP-Za-km-z]{32,44}$`. Validating client-side avoids a `400`,
   which this operation also uses for upstream failures — so a `400` is ambiguous between
   "your mint is wrong" and "the upstream data source failed."

2. **Call `scanSolanaTokenFree`** — `GET /api/agent/scan?mint={mint}`.
   Optionally pass `campaign` (max 16 chars, `^[A-Za-z0-9_-]+$`) for aggregate attribution.
   The operation is idempotent; retrying is safe.

3. **Read the result as point-in-time evidence.** The scan checks mint and freeze
   authority, top-account concentration, DexScreener discovery, and Jupiter routing.

4. **Report, do not act.** The provider's published governance profile forbids autonomous
   adverse action on this output and requires human review. Present the findings and let a
   person decide.

## Error handling

| Status | Meaning | What to do |
|---|---|---|
| `400` | Invalid mint **or** upstream scan failure | Re-check the base58 pattern first; if the mint is valid, treat it as a transient upstream failure and retry once. |

## Rules

- The response has no declared schema in the spec — parse defensively and do not assume
  field names are stable.
- Results can go stale immediately. Always show the caller when the scan was run.
- This is technical information, not investment, legal, or tax advice. Say so when
  relaying it.
- Never ask the user for a private key or seed phrase. This service never needs one.
