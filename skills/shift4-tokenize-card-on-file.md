---
name: Tokenize a card for card-on-file
description: Store a card in Shift4 TokenStore and charge the token later, keeping PAN out of your systems.
api: openapi/shift4-payment-api.yml
operations: [accesstokenexchange, tokensadd, tokensdelete, transactionssale]
---

# Tokenize a card for card-on-file (Shift4)

Use this to save a customer's card once and bill it on future visits without handling the PAN.

## Auth
Header `AccessToken` + HMAC-SHA256 signature. Obtain via `accesstokenexchange` if needed.

## Steps
1. **Add token** — `tokensadd` (`POST /tokens/add`) with the card data. Send the `TOKENAUTH` API option to trigger a $0/$1 validation authorization before storing (invalid cards return error `9858`). Use `IGNOREEXPIRY` to tokenize/import expired cards.
2. **Charge the token** — `transactionssale` (`POST /transactions/sale`) using `card.token.value` instead of a PAN, with a unique `invoice`.
3. **Delete token** — `tokensdelete` (`POST /tokens/delete`) when the customer removes the card on file.

## Rules
- CSC/track data cannot be stored — `TOKENAUTH` is ignored if CSC or track data is present (it would be consumed by the validation auth).
- For stored-credential compliance, keep the card-on-file token current with the Account Updater (`updaterrequest` / `updaterstatus`).
- A missing/purged token returns error.code `40105` ("Token not found") or `9846` ("BAD UNIQUE ID"); expired token returns `40106`.
- Never invent test PANs — use the published test cards in `sandbox/shift4-sandbox.yml`.
