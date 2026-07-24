---
name: Authorize and capture a card payment
description: Place an authorization hold on a card, then capture it to settle, using the Shift4 Payment API.
api: openapi/shift4-payment-api.yml
operations: [accesstokenexchange, transactionsauthorization, transactionscapture, getinvoice]
---

# Authorize and capture a card payment (Shift4)

Use this two-step flow when you need to hold funds now and settle later (e.g. hospitality/retail with a tip or adjustment before batch close).

## Auth
- Every request carries a header `AccessToken` (the merchant/interface alias) plus an `Authorization: HMAC-SHA256 Credential=...&Signature=...` request signature.
- If you do not yet have an Access Token, call **`accesstokenexchange`** (`POST /credentials/accesstoken`) with the Client GUID + Auth Token, then store the returned Access Token securely.

## Steps
1. **Authorize** — `transactionsauthorization` (`POST /transactions/authorization`). Send `amount`, `card`, `customer`, and a unique `invoice`. Response returns `transaction.responseCode` (`A` approved, `P` partial, `R` referral, `D` declined).
2. **Capture** — `transactionscapture` (`POST /transactions/capture`) referencing the same `invoice`. The Gateway searches the current batch for that invoice and amends it rather than creating a duplicate.
3. **Confirm** — `getinvoice` (`GET /transactions/invoice`) to read the settled status.

## Rules
- **Idempotency / double-charge prevention:** keep `invoice` stable across the authorize→capture pair. To amend a settled/closed transaction safely, send the `INVMUSTEXIST` API option so an unknown invoice errors instead of silently creating a new charge. Duplicate authorizations return error.code `64500`.
- **Partial approval (`P`):** only when `ALLOWPARTIALAUTH` is sent; compare the approved `amount.total` in the response against the requested amount and collect the remainder.
- **Referral (`R`):** obtain a 6-char voice auth code and submit via `manualauthorization`/`manualsale`; e-commerce treats `R` as a decline (auto-voided).
- Errors use `error.code` / `error.shortText` / `error.longText` / `error.severity` — see `errors/shift4-error-codes.yml`.
- Test with the sandbox amount triggers in `sandbox/shift4-sandbox.yml` (e.g. `amount.total = 219` for a partial approval).
