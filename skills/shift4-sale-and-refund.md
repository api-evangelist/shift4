---
name: Make a sale and refund it
description: Run a one-call sale/purchase and later refund or void it with the Shift4 Payment API.
api: openapi/shift4-payment-api.yml
operations: [accesstokenexchange, transactionssale, refund, void, getinvoice]
---

# Make a sale and refund it (Shift4)

Use this when you want to authorize and capture in a single call (card-not-present e-commerce or immediate retail sale).

## Auth
Header `AccessToken` + `Authorization: HMAC-SHA256 ...` signature on every call. Obtain the Access Token via `accesstokenexchange` if needed.

## Steps
1. **Sale** — `transactionssale` (`POST /transactions/sale`) with `amount`, `card` (or `card.token`), `customer`, and a unique `invoice`. Check `transaction.responseCode`.
2. **Void (same batch, not settled)** — `void` (`DELETE /transactions/invoice`) referencing the `invoice` to cancel before settlement.
3. **Refund (after settlement)** — `refund` (`POST /transactions/refund`) for a full or partial return. A refund amount greater than the original returns error.code mapped from legacy `9879`.
4. **Confirm** — `getinvoice` (`GET /transactions/invoice`).

## Rules
- Prefer **void** for same-day/unsettled reversals and **refund** once the batch is closed.
- Keep `invoice` stable; use `INVMUSTEXIST` to prevent accidental new-invoice creation when amending.
- Decline/referral handling: see `errors/shift4-decline-codes.yml`. AVS/CSC results are on `transaction.avs.result` and `card.securityCode.result`.
- Sandbox: `amount.total = 19.19` triggers a declined refund; declines trigger at `amount.total > 999999`.
