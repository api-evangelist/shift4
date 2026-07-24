---
name: Create and reconcile a payment link
description: Create a hosted Shift4 payment link, share it, and track payment status via webhooks.
api: openapi/shift4-payment-api.yml
operations: [accesstokenexchange, paymentslinkcreate, paymentslinklist, paymentslinkretrieve, paymentslinkupdate]
---

# Create and reconcile a payment link (Shift4)

Use this to collect a payment without building a checkout UI — Shift4 hosts the page and notifies you when it's paid.

## Auth
Header `AccessToken` + HMAC-SHA256 signature. Obtain via `accesstokenexchange` if needed. Payment Links use the host `https://api.shift4.com/api/rest/v1`.

## Steps
1. **Create** — `paymentslinkcreate` (`POST /paymentlinks/create`) with `amount`, description, and optional `lineItems[].product.description`. The response returns the shareable link URL and its id.
2. **Share** — deliver the returned URL to the customer.
3. **Update** — `paymentslinkupdate` (`POST /paymentlinks/update`) to change amount/config; **list/retrieve** — `paymentslinklist` (`GET /paymentlinks/list`) and `paymentslinkretrieve` (`GET /paymentlinks/retrieve`) to check state.
4. **Reconcile** — register a callback to receive the `paymentlinks-notification` webhook (see `asyncapi/shift4-webhooks.yml`) for asynchronous paid/expired/cancelled status instead of polling.

## Rules
- Treat the webhook as the source of truth for final status; list/retrieve are for on-demand checks.
- Errors use the standard `error.code` envelope (`errors/shift4-error-codes.yml`).
