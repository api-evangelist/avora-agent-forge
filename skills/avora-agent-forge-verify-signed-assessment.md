---
name: Obtain and verify a signed public-sector assessment
description: >-
  Request a signed, public-data Solana token assessment and independently verify its
  Ed25519 JWS receipt against the provider's published JWKS before relying on it.
api: openapi/avora-agent-forge-public-sector-openapi.json
operations:
  - getPublicAiServiceHealth
  - createSignedSolanaTokenAssessment
  - getReceiptVerificationKeys
mcp_tool: scan_solana_token_public_sector
a2a_skill: public-sector-solana-token-risk
generated: '2026-08-09'
method: generated
source: >-
  openapi/avora-agent-forge-public-sector-openapi.json +
  well-known/avora-agent-forge-ai-governance.json
---

# Obtain and verify a signed public-sector assessment

The point of this API is not the assessment — it is that the assessment is **independently
verifiable**. If you skip verification, you have gained nothing over the free scan.

## Steps

1. **Optionally check health** — `getPublicAiServiceHealth`
   (`GET /api/gov/v1/health`). A `503` means signing or an upstream public data source is
   unavailable, so no assessment can be signed. Do not proceed on `503`.

2. **Request the assessment** — `createSignedSolanaTokenAssessment`
   (`GET /api/gov/v1/scan?mint={mint}`).
   - `mint` is required, base58 SPL format.
   - Pass an optional `requestId` (letters, numbers, dot, underscore, hyphen) as a caller
     trace ID; it is echoed into the signed assessment. Use it — it is what ties your audit
     log to the receipt.

3. **Fetch the verification keys** — `getReceiptVerificationKeys`
   (`GET /.well-known/jwks.json`). Returns `application/jwk-set+json` with OKP Ed25519
   keys.

4. **Verify the JWS receipt** against the JWKS using EdDSA. Key rotation is not documented,
   so on an unrecognized `kid`, re-fetch the JWKS rather than assuming a cached key is
   still current. **Reject the assessment if verification fails.**

5. **Carry the provenance forward.** The `SignedAssessment` includes provenance, the named
   upstream public dependencies, and explicit known limitations. When you relay the result,
   relay those limitations with it — stripping them misrepresents the assessment.

## Decision boundaries — published by the provider

These are the provider's own stated constraints in
`/.well-known/ai-governance.json`, not our additions:

- Use is `INFORMATIONAL_ONLY`.
- **Human review is mandatory.**
- **Autonomous adverse action is prohibited.** Do not block, flag, delist, or deny anything
  on the strength of this output without a human in the loop.
- Investment recommendations are not permitted.
- No certification and no government approval is claimed. The NIST AI RMF reference is a
  voluntary alignment profile, not accreditation. Do not describe it as certified.

## Known limitations to state when relaying

- Point-in-time results can become stale immediately.
- Upstream public services can be incomplete, delayed, unavailable, or inconsistent.
- Token-account concentration does not identify beneficial owners.
- Market discoverability does not establish liquidity quality, legality, value, or safety.
- The risk score is a technical heuristic, not an official rating.

## Error handling

| Status | Meaning | What to do |
|---|---|---|
| `400` | Invalid mint | Fix the base58 mint. |
| `503` | Signing key or upstream dependency unavailable | Retry later. Do not fall back to an unsigned scan and present it as signed. |

## Rules

- Input is limited to a public Solana mint. Never send personal data, secrets, or wallet
  private keys — the provider states none are accepted.
- An unverified assessment is not an assessment. Verify or discard.
