# Recurso Documentation

The documentation for [Recurso](https://github.com/swapnull-in/recur-so), the
open-source billing engine for SaaS — subscriptions, invoicing, multi-currency
payments (Stripe + Razorpay), tax (India GST, EU VAT, US sales tax), smart
dunning, a double-entry ledger, and a self-service customer portal.

Published at **[docs.recurso.dev](https://docs.recurso.dev)** (Mintlify).

## Structure

- `index.mdx`, `quickstart.mdx` — landing and getting started
- `core/` — customers, plans, subscriptions, invoices, payments
- `portal/` — hosted checkout and the customer self-service portal
- `advanced/` — payment gateways, multi-currency, and deeper topics
- `compliance/` — India GST/e-invoicing, US sales tax, VAT
- `api-reference/` — endpoint reference generated from `openapi.yaml`
- `docs.json` — navigation and site config

The `openapi.yaml` here is a copy of the spec served by the API
(`cmd/api/openapi.yaml` in the main repo); re-copy it when the API surface
changes. A CI test in the main repo (`TestOpenAPISpecCoversRegisteredRoutes`)
fails if a served route is missing from the spec, so the documented surface
can't silently drift.

## Local preview

```bash
npm i -g mint      # Mintlify CLI
mint dev           # serves at http://localhost:3000
```

Run from the directory containing `docs.json`. Changes merged to the default
branch deploy to production automatically via the Mintlify GitHub app.

## Contributing

Docs live alongside the product. If you change API behavior in the main repo,
update the matching page here (and re-copy `openapi.yaml` if the spec moved).
