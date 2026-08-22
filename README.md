# Vagaro (vagaro)

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
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Vagaro is a cloud platform for salon, spa, and fitness/wellness business management - scheduling, point of sale and payments, marketing, and a consumer booking marketplace (Vagaro.com and the Vagaro app). Vagaro publishes a real developer surface at docs.vagaro.com, a readme.io-hosted "PUBLIC - Enterprise Business API V2" site with a documented OAuth-style Access Token endpoint, five REST capability areas (Employee Management, Locations, Appointments, Customers, Employees), and an outbound Webhooks system covering Appointments, Customers, Employees, Transactions, Form Responses, and Business Locations plus booking-widget interaction events, with fully specified event payloads.

**Access model: partner/approval-gated, not self-serve.** Enabling APIs & Webhooks requires a request submitted from Settings > Developers > APIs & Webhooks inside a Vagaro business account, a paid non-trial subscription with Credit Card Processing enabled on the computer, tablet, Pay Desk, or PayPro version, and roughly five to seven business days of Vagaro review before credentials and the full authenticated reference become visible. Only the Access Token endpoint (method, path, request fields, response codes) and the Webhook event payload schemas are visible on the public documentation without an approved account. The Appointments, Customers, Employees, Employee Management, and Locations REST endpoints documented in this repository are **honestly modeled** from Vagaro's own capability-level descriptions of those areas and from confirmed webhook payload field names - real resource nouns and fields, not fabricated, but not independently verified against a live authenticated response.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/vagaro/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/vagaro/refs/heads/main/apis.yml)

## Tags

- Salon
- Spa
- Fitness
- Wellness
- Scheduling
- Booking
- Vertical SaaS

## Timestamps

- **Created:** 2026-07-03
- **Modified:** 2026-07-03

## APIs

### Vagaro Access Token API

Exchanges a partner clientId and clientSecretKey, plus a comma-separated list of requested scopes, for a bearer access token scoped to a business region - `POST https://api.vagaro.com/{region}/api/v2/merchants/generate-access-token`. Documented response codes are 200 (issued), 400 (bad request), 401 (unauthorized), and 429 (too many requests). **Confirmed real** from Vagaro's public reference page.

- **Human URL:** [https://docs.vagaro.com/public/reference/generate-access-token](https://docs.vagaro.com/public/reference/generate-access-token)
- **Base URL:** `https://api.vagaro.com`

#### Properties

- [Documentation](https://docs.vagaro.com/public/reference/api-introduction)
- [API Reference](https://docs.vagaro.com/public/reference/generate-access-token)
- [OpenAPI](openapi/vagaro-openapi.yml)

### Vagaro Appointments API

Retrieve appointment records - booking status, start/end time, service and service provider, customer, and booking source. Modeled from Vagaro's documented capability summary and the confirmed Appointment webhook payload schema.

- **Human URL:** [https://docs.vagaro.com/public/reference/api-introduction](https://docs.vagaro.com/public/reference/api-introduction)
- **Base URL:** `https://api.vagaro.com`
- **Endpoints modeled:** yes

### Vagaro Customers API

Retrieve customer contact information and profile tags. Modeled from Vagaro's documented capability summary and the confirmed Customer webhook payload schema.

- **Human URL:** [https://docs.vagaro.com/public/reference/api-introduction](https://docs.vagaro.com/public/reference/api-introduction)
- **Base URL:** `https://api.vagaro.com`
- **Endpoints modeled:** yes

### Vagaro Employees API

Retrieve service provider details - contact information and reporting relationships. Modeled from Vagaro's documented capability summary and the confirmed Employee webhook payload schema.

- **Human URL:** [https://docs.vagaro.com/public/reference/api-introduction](https://docs.vagaro.com/public/reference/api-introduction)
- **Base URL:** `https://api.vagaro.com`
- **Endpoints modeled:** yes

### Vagaro Employee Management API

Assign and unassign employees across multiple business locations with a specified access level, and provision or deprovision a bookable calendar for an employee. Modeled from Vagaro's documented capability summary.

- **Human URL:** [https://docs.vagaro.com/public/reference/api-introduction](https://docs.vagaro.com/public/reference/api-introduction)
- **Base URL:** `https://api.vagaro.com`
- **Endpoints modeled:** yes

### Vagaro Locations API

Retrieve single- or multi-location business details for a Vagaro account. Modeled from Vagaro's documented capability summary and the confirmed Business Location webhook payload schema.

- **Human URL:** [https://docs.vagaro.com/public/reference/api-introduction](https://docs.vagaro.com/public/reference/api-introduction)
- **Base URL:** `https://api.vagaro.com`
- **Endpoints modeled:** yes

### Vagaro Webhooks

Outbound event notifications - HTTP POST requests to a merchant-registered HTTPS endpoint, not a WebSocket - fired whenever Appointments, Customers, Employees, Transactions, Form Responses, or Business Locations change, plus booking-widget interaction events. Each event carries an `id`, `createdDate`, `type`, `action` (created/updated/deleted), and a typed payload. A business may register up to 10 webhooks. **Confirmed real** and fully documented, though enabling it requires Enterprise Sales approval.

- **Human URL:** [https://docs.vagaro.com/public/docs/introduction](https://docs.vagaro.com/public/docs/introduction)

#### Properties

- [Introduction](https://docs.vagaro.com/public/docs/introduction)
- [Webhook Events Index](https://docs.vagaro.com/public/docs/webhook-events)
- [Appointment Events](https://docs.vagaro.com/public/docs/appointment-events)
- [Securing Webhook Endpoint](https://docs.vagaro.com/public/docs/securing-webhook-endpoint)
- [Retry Policy](https://docs.vagaro.com/public/docs/retry-policy)
- [Support: Set Up Webhooks From Vagaro](https://support.vagaro.com/hc/en-us/articles/29521637950875-Set-Up-Webhooks-From-Vagaro)

## Common Properties

- [LinkedIn](https://www.linkedin.com/company/vagaro)
- [Website](https://www.vagaro.com/pro)
- [Documentation](https://docs.vagaro.com/)
- [Plans](plans/vagaro-plans-pricing.yml)
- [Rate Limits](rate-limits/vagaro-rate-limits.yml)
- [Fin Ops](finops/vagaro-finops.yml)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
