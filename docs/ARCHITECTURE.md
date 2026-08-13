# Flagship Beats Licensing — Architecture

## System boundary

Shopify owns commerce facts: products, variants, orders, customers, and installation state.

The licensing application owns license facts: license tier, issued license, status, rights configuration, certificate metadata, verification state, and audit events.

## Runtime flow

```text
Shopify order
  -> authenticated webhook
  -> idempotency guard
  -> qualifying product/variant resolver
  -> license tier resolver
  -> license service
  -> PostgreSQL
  -> audit event
```

## Admin application

The embedded Admin UI is the merchant control plane. It should expose:

- Dashboard
- Licenses
- License detail
- Products / license mapping
- License tiers
- Audit events
- Settings

The UI should never contain licensing rules that belong in the domain/service layer.

## Public verification

A future public endpoint will accept a public license ID and return only intentionally public verification data. It must not expose customer PII, internal IDs, secrets, or raw Shopify session data.

## Webhooks

Initial lifecycle topics:

- `orders/create` — issue qualifying licenses
- `app/uninstalled` — clean up or deactivate the installation according to retention requirements
- Shopify mandatory privacy/compliance topics required for the selected distribution model

Webhook processing must be:

- authenticated
- idempotent
- bounded in execution time
- observable
- retry-safe

## Security boundaries

- Shopify access/session tokens are server-side secrets.
- Database credentials are environment secrets.
- Public license IDs are identifiers, not bearer credentials.
- License mutations require authenticated merchant authorization.
- Certificate downloads must authorize access before serving private customer information.

## Deployment

Development and production configurations remain separate. Production deployment requires explicit environment configuration, database migration, webhook registration, and post-deploy smoke tests.
