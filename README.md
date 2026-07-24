# Shift4 (shift4)

Shift4 (NYSE: FOUR) is a US-based integrated payments and commerce technology company headquartered in Center Valley, Pennsylvania, and a Fortune 1000 business serving restaurants, hospitality, retail, gaming, stadiums, e-commerce, and nonprofit verticals. It operates as an end-to-end acquirer-processor, owning the full stack from its own gateway and card acquiring through in-person SkyTab POS hardware, online checkout, and alternative payment methods, and has expanded internationally through acquisitions including Finaro (Credorax) and Global Blue.

Shift4 ships a genuinely API-native developer surface: a Redocly-powered portal at [docs.shift4.com](https://docs.shift4.com) publishing the **Shift4 Payment API** as a single downloadable OpenAPI 3.1 definition (v1.7.57, 70 paths, 3 webhooks), authenticated with a header `AccessToken` (API key) plus `HMAC-SHA256` request signing, backed by webhook event notifications, a sandbox, SDKs, and a published Postman collection.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/shift4/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/shift4/refs/heads/main/apis.yml)

## Tags

- Payments
- United States
- Payment Processing
- Payment Gateway
- Acquiring
- Payment Terminal
- Tokenization
- ACH
- 3D Secure
- Gift Cards
- Payment Links
- Card Present

## Timestamps

- **Created:** 2026-07-24
- **Modified:** 2026-07-24

## APIs

All product families below are surfaced by the single **Shift4 Payment API** OpenAPI 3.1 definition ([openapi/shift4-payment-api.yml](openapi/shift4-payment-api.yml)). Production base URL: `https://api.shift4api.net/api/rest/v1` (test: `https://api.shift4test.com/api/rest/v1`).

### Shift4 Transactions API

Core card payment processing — authorize, capture, sale, refund, plus card entry, processing mode, dynamic currency conversion (DCC), and batch settlement.

- **Reference:** [https://docs.shift4.com/apis/payments-platform-rest/openapi](https://docs.shift4.com/apis/payments-platform-rest/openapi)

### Shift4 Tokens API

Tokenization — create, retrieve, and manage single-use and card-on-file tokens, plus the account updater for stored credentials.

### Shift4 Gift Cards API

Stored-value gift card activation, add-value, redemption, and balance inquiry.

### Shift4 Devices API

In-person / card-present terminal control, EMV/contactless acceptance, and the Commerce Engine for attended and unattended hardware.

### Shift4 ACH API

ACH bank-account debit/credit transactions with asynchronous webhook status notifications.

### Shift4 Alternative & QR Payments API

QR-code payments (Citcon, WeChat Pay, Alipay) and PayPal acceptance.

### Shift4 3D Secure & Risk API

3D Secure (3DS) cardholder authentication plus risk scoring and rule evaluation.

### Shift4 Payment Links API

Create, configure, share, and reconcile hosted payment links, with payment-link webhooks.

### Shift4 Checkout Sessions API

Hosted checkout sessions for online payment collection, with checkout-session webhooks.

### Shift4 OCT Payouts API

Original Credit Transaction (OCT) push-to-card payouts and disbursements.

### Shift4 Reports & Merchants API

Transaction reporting plus merchant and credentials lookups.

## Common Properties

- [Website](https://www.shift4.com)
- [Developer Portal](https://docs.shift4.com)
- [API Reference](https://docs.shift4.com/apis/payments-platform-rest/openapi)
- [Getting Started](https://docs.shift4.com/guides/quickstart)
- [Postman](https://docs.shift4.com/tools/postman)
- [Changelog](https://docs.shift4.com/changelog)
- [Support](https://docs.shift4.com/guides/support)
- [Status Page](https://status.shift4.com)
- [JavaScript Library (Shift4.js)](https://dev.shift4.com/docs/js/)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
