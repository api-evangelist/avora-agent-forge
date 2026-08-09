---
name: Order and collect a paid evidence packet
description: >-
  Walk a user through buying a Signed Risk Snapshot, Pro Evidence Packet, or Portfolio Due
  Diligence bundle with Solana Pay (USDC), then collect the artifact once settlement is
  verified on-chain.
api: openapi/avora-agent-forge-commerce-openapi.json
operations:
  - listEvidenceOffers
  - createPaidEvidenceOrder
  - verifyPaymentAndDeliverEvidence
mcp_tools:
  - list_avora_offers
  - create_starter_snapshot_order
  - create_pro_report_order
  - create_portfolio_report_order
  - verify_starter_snapshot_payment
  - verify_pro_report_payment
  - verify_portfolio_report_payment
generated: '2026-08-09'
method: generated
source: >-
  openapi/avora-agent-forge-commerce-openapi.json +
  mcp/avora-agent-forge-tools-list.json + plans/avora-agent-forge-pricing.json
---

# Order and collect a paid evidence packet

This flow moves real money. Read the money rules before the steps.

## Money rules — non-negotiable

- **The agent never pays.** Order creation returns a Solana Pay URL. Funds move only when
  the **user** reviews and signs the transaction in their own wallet. The service is
  non-custodial.
- **Never present an order as a completed purchase.** Until settlement is verified, nothing
  has been bought.
- **Never ask for a private key or seed phrase.** The service never requests one.
- **Never create a second order to resolve a `402`.** That asks the user to pay twice.

## Steps

1. **Run a free scan first.** Use the `Scan a Solana token for risk` skill. Do not sell a
   paid artifact for a mint that fails basic validation.

2. **List the offers** — `listEvidenceOffers` (`GET /api/agent/offers`). Take prices from
   the live response, never from memory. At time of capture: starter 1 USDC (1 mint), pro
   9 USDC (1 mint), portfolio 49 USDC (2–10 mints).

3. **Create the order** — `createPaidEvidenceOrder`
   (`GET /api/agent/payment-order?tier={tier}`).
   - `tier` is required and must be `starter`, `pro`, or `portfolio`.
   - `starter` and `pro` require `mint`. `portfolio` requires `mints` — 2 to 10
     comma-separated base58 mints.
   - Optional `campaign` attribution code.

   Keep the returned `orderId` and settlement `reference`. **You cannot collect the
   artifact without both.** This operation is *not* idempotent — calling it again mints a
   new order.

4. **Hand the Solana Pay URL / QR to the user** and wait for them to sign in their wallet.

5. **Verify and collect** — `verifyPaymentAndDeliverEvidence`
   (`POST /api/agent/pro-scan`). Body must satisfy one of `StarterVerification`,
   `ProVerification`, or `PortfolioVerification`; `reference` and `orderId` are required on
   all three. The provider validates recipient, USDC mint, amount, unique reference,
   product subject hash, campaign memo, and payment age before delivering.

6. **Poll on `402`.** This operation is idempotent and keyed on `reference` — repeating it
   returns the same packet and never re-charges.

## Error handling

| Status | Meaning | What to do |
|---|---|---|
| `400` | Invalid tier, mint count, address, or verification body | Fix the request. For `portfolio`, check you sent `mints` with 2–10 entries, not `mint`. |
| `402` | Matching on-chain payment not found **yet** | **Expected state, not a failure.** Poll with backoff using the *same* `reference` and `orderId`. Tell the user their signature may still be confirming. |

## Rules

- Treat `reference` as the idempotency key for the whole purchase.
- Do not retry indefinitely on `402` — after a reasonable window, tell the user the payment
  was not observed and let them decide, rather than silently looping.
- No response schema is declared for the evidence packet; parse defensively.
- Reports are technical information, not investment, legal, or tax advice.
