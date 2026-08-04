# FXRatesAPI (fxratesapi)

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

FXRatesAPI is a foreign exchange rates REST API that delivers real-time and historical currency exchange rates for 185+ fiat currencies plus major cryptocurrencies and precious metals. It exposes JSON endpoints for the latest rates, historical rates for any past date, time-series ranges, currency conversion, and a currencies list. All endpoints are served from a single base host, `https://api.fxratesapi.com`, over HTTPS (HTTP/2, TLS 1.3).

## Access Model (read this first)

- **Free / limited tier — no API key required.** During this review (2026-07-12) `GET /latest`, `/historical`, `/timeseries`, `/convert`, and `/currencies` all returned HTTP 200 with valid JSON when called **anonymously**. An obviously invalid `api_key` value was ignored (the request still succeeded as anonymous) rather than rejected.
- **Paid tiers — API key required for the good stuff.** Higher monthly request quotas, more frequent rate updates, base-currency switching, and full historical depth are gated behind a paid API key, per the pricing page.
- **How the key is passed:** as the `api_key` query parameter (confirmed accepted, HTTP 200) or as an `Authorization: Bearer YOUR_KEY` header (per the authentication docs).
- **Pricing values are not reconciled.** The `fxratesapi.com/pricing` page is client-rendered and could not be read without signing in, so exact tier names, prices, and quotas in `plans/` and `finops/` are modeled and marked `reconciled: false`.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/fxratesapi/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/fxratesapi/refs/heads/main/apis.yml)

## Tags

- Foreign Exchange
- FX
- Currency
- Exchange Rates
- Forex
- Currency Conversion
- Historical Rates
- Financial Data
- Cryptocurrencies

## Timestamps

- **Created:** 2026-07-12
- **Modified:** 2026-07-12

## APIs

All five APIs below were confirmed by live probing of the API on 2026-07-12. Base URL for every endpoint is `https://api.fxratesapi.com`.

### FXRatesAPI Latest Rates API

Returns the most recent exchange rates for a chosen base currency against all or a selected set of currencies. `GET /latest` accepts `base` and `currencies` (comma-separated) query parameters.

- **Human URL:** [https://fxratesapi.com/docs/endpoints/latest-exchange-rates](https://fxratesapi.com/docs/endpoints/latest-exchange-rates)
- **Base URL:** `https://api.fxratesapi.com`

#### Tags

- Latest Rates
- Exchange Rates
- Real Time

#### Properties

- [API Reference](https://fxratesapi.com/docs/endpoints/latest-exchange-rates)
- [Documentation](https://fxratesapi.com/docs)
- [OpenAPI](openapi/fxratesapi-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/fxratesapi.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/fxratesapi.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### FXRatesAPI Historical Rates API

Returns exchange rates as they were on a specific past date. `GET /historical` accepts a required `date` parameter plus optional `base` and `currencies` parameters.

- **Human URL:** [https://fxratesapi.com/docs/endpoints/historical-rates](https://fxratesapi.com/docs/endpoints/historical-rates)
- **Base URL:** `https://api.fxratesapi.com`

#### Tags

- Historical Rates
- Exchange Rates
- Time Travel

#### Properties

- [API Reference](https://fxratesapi.com/docs/endpoints/historical-rates)
- [Documentation](https://fxratesapi.com/docs)
- [OpenAPI](openapi/fxratesapi-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/fxratesapi.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/fxratesapi.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### FXRatesAPI Time-Series API

Returns daily exchange rates across a date range for a base currency and a set of target currencies. `GET /timeseries` accepts `start_date`, `end_date`, `base`, and `currencies` parameters.

- **Human URL:** [https://fxratesapi.com/docs/endpoints/time-series-exchange-rates](https://fxratesapi.com/docs/endpoints/time-series-exchange-rates)
- **Base URL:** `https://api.fxratesapi.com`

#### Tags

- Time Series
- Historical Rates
- Ranges

#### Properties

- [API Reference](https://fxratesapi.com/docs/endpoints/time-series-exchange-rates)
- [Documentation](https://fxratesapi.com/docs)
- [OpenAPI](openapi/fxratesapi-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/fxratesapi.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/fxratesapi.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### FXRatesAPI Convert API

Converts an amount from one currency to another at the latest or a historical rate. `GET /convert` accepts `from`, `to`, `amount`, and an optional `date` parameter.

- **Human URL:** [https://fxratesapi.com/docs/endpoints/convert-currency](https://fxratesapi.com/docs/endpoints/convert-currency)
- **Base URL:** `https://api.fxratesapi.com`

#### Tags

- Currency Conversion
- Convert
- FX

#### Properties

- [API Reference](https://fxratesapi.com/docs/endpoints/convert-currency)
- [Documentation](https://fxratesapi.com/docs)
- [OpenAPI](openapi/fxratesapi-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/fxratesapi.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/fxratesapi.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### FXRatesAPI Currencies API

Lists every supported currency with code, name, plural name, symbol, native symbol, and decimal digits. `GET /currencies` takes no parameters and was confirmed live returning 185 currency entries.

- **Human URL:** [https://fxratesapi.com/docs/endpoints/list-available-currencies](https://fxratesapi.com/docs/endpoints/list-available-currencies)
- **Base URL:** `https://api.fxratesapi.com`

#### Tags

- Currencies
- Metadata
- Symbols

#### Properties

- [API Reference](https://fxratesapi.com/docs/endpoints/list-available-currencies)
- [Documentation](https://fxratesapi.com/docs/currency-list)
- [OpenAPI](openapi/fxratesapi-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/fxratesapi.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/fxratesapi.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Not Offered

- **No OHLC endpoint.** Unlike several competing FX APIs, FXRatesAPI does **not** expose an open/high/low/close endpoint. `GET /ohlc` (and path variants) returned `Endpoint Not Found`, and no OHLC page appears in the docs sitemap. It is deliberately excluded from this catalog rather than modeled.
- **No WebSocket API.** FXRatesAPI's public surface is entirely request/response REST over HTTPS. There is no documented WebSocket (`wss://`) or SSE streaming channel; rate updates are obtained by polling `/latest`.

## Common Properties

- [Domain Security](security/fxratesapi-domain-security.yml)
- [Authentication](authentication/fxratesapi-authentication.yml)
- [Website](https://fxratesapi.com)
- [Documentation](https://fxratesapi.com/docs)
- [Plans](plans/fxratesapi-plans-pricing.yml)
- [Rate Limits](rate-limits/fxratesapi-rate-limits.yml)
- [Fin Ops](finops/fxratesapi-finops.yml)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
