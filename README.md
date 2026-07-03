# Vagaro (vagaro)

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
