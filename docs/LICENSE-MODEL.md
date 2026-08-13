# Flagship Beats — Canonical License Model

## License tiers

License tiers are configuration/data, not UI conditionals.

Initial planned tiers:

- `BETA`
- `BASIC`
- `PREMIUM`
- `EXCLUSIVE`

The exact rights text is governed by the approved legal license documents. The application stores a reference/version rather than silently changing historical rights when a tier is edited.

## License identity

Each issued license has:

- internal database ID
- public license number, e.g. `FB-2026-000001`
- cryptographically generated secret/verification material where required
- immutable issuance timestamp
- Shopify shop/install reference
- Shopify order reference
- Shopify customer reference
- Shopify product/variant reference
- license tier/version
- status
- audit history

## Statuses

Initial lifecycle:

```text
ACTIVE
REVOKED
EXPIRED
CANCELLED
```

A license should never be silently deleted after issuance. Historical records are retained according to the application's privacy/retention policy and represented by an explicit status change.

## Idempotency

A qualifying order/line-item must not issue duplicate licenses when Shopify retries a webhook. The database must enforce a unique business key for the issuance event.

## Historical integrity

A license stores the version of the rights configuration/legal document used at issuance. Updating the current tier must not retroactively rewrite existing licenses.

## Product mapping

Product/variant-to-tier mapping belongs in persistent configuration. Do not hard-code Shopify product IDs into React components or webhook handlers.
