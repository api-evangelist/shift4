# Shift4 (shift4)

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
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

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
