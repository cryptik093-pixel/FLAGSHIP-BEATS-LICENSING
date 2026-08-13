# Flagship Beats Licensing

Production Shopify app for issuing, managing, and verifying Omega House Studio LLC / Flagship Beats licenses.

## Purpose

The application turns qualifying Shopify purchases into durable license records with a verifiable license ID, license tier, customer/order linkage, audit history, and future certificate/verification support.

## Architecture

- Shopify Admin: merchant-facing embedded application
- React Router + TypeScript: application UI and routes
- Shopify Admin GraphQL API: Shopify data access
- PostgreSQL: production application data and license records
- Prisma: database access and migrations
- Shopify webhooks: purchase/uninstall/privacy lifecycle events
- License domain layer: authoritative rules for license issuance and status
- Verification endpoint: public validation of issued licenses

## Core domain

```text
Store
Customer
Product
LicenseTier
License
LicenseEvent
Certificate
```

## License lifecycle

```text
Shopify order
    -> validate qualifying product/variant
    -> resolve license tier
    -> idempotency check
    -> create license
    -> record audit event
    -> generate certificate (later phase)
    -> expose verification record (later phase)
```

## Development

The app should be scaffolded from Shopify's current React Router template:

```bash
shopify app init --template=https://github.com/Shopify/shopify-app-template-react-router
```

Then run:

```bash
shopify app dev
```

Shopify's React Router template is the recommended starting point for most new Shopify apps and provides authentication, App Bridge integration, GraphQL access, and webhook foundations.

## Production principles

1. Shopify is the purchase/event source of truth; the licensing database is the license-rights source of truth.
2. License issuance is idempotent.
3. Public license IDs are not authentication secrets.
4. Secrets never enter source control.
5. Shopify scopes remain minimal.
6. Webhooks are authenticated and handled defensively.
7. Destructive license actions are audited.
8. Production deployment is separate from development configuration.

## Repository contents

- `Omega_House_Flagship_Beats_Beta_Master_License_v1.0.docx` — existing legal/license reference document.
- `docs/ARCHITECTURE.md` — system architecture and boundaries.
- `docs/LICENSE-MODEL.md` — canonical licensing model.
