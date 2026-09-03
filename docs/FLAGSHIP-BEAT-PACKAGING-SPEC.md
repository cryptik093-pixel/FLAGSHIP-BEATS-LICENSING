# Omega House Flagship Beats — Packaging Specification v1

## Objective

Create one deterministic product package that can be consumed by the artist, Shopify digital fulfillment, and the Flagship Beats licensing application.

## Canonical package

`packages/flagship-beat-template/` is the reusable source template. Each released beat should become a versioned package derived from it.

## Asset classes

| Class | Purpose | Required |
|---|---|---|
| Master | Full-resolution beat delivery | Yes |
| Preview | Store/player preview | Yes |
| Stems | Flexible production/editing | Tier-dependent |
| MIDI | Musical reconstruction/editing | Tier-dependent |
| Artwork | Product identity | Yes |
| License | Rights grant | Yes |
| Metadata | Commerce + audio automation | Yes |
| Checksums | Delivery integrity | Yes |

## Data flow

```text
Production session
  -> final master
  -> stems / MIDI
  -> metadata normalization
  -> package assembly
  -> SHA-256 integrity manifest
  -> Shopify product/variant mapping
  -> qualifying purchase
  -> Flagship license issuance
  -> tier-specific digital fulfillment
```

## Source-of-truth boundaries

Shopify remains the commerce source of truth. The licensing application remains the source of truth for issued license rights, status, version, and audit history. This aligns with the repository's existing architecture and canonical license model.

## Versioning

Package versions are immutable after publication. Corrections create a new package version; historical licenses retain the rights configuration/legal-document version used at issuance.

## Naming

`OHFB-YYYY-NNNN_TITLE_ASSET_KEY_BPM_VN.ext`

Examples:

- `OHFB-2026-0001_NIGHTFALL_MASTER_FMIN_140_V1.wav`
- `OHFB-2026-0001_NIGHTFALL_PREVIEW_FMIN_140_V1.mp3`
- `OHFB-2026-0001_NIGHTFALL_STEM_DRUMS_FMIN_140_V1.wav`
- `OHFB-2026-0001_NIGHTFALL_MIDI_FMIN_140_V1.mid`

## Release gates

`DRAFT -> QA -> READY -> PUBLISHED -> ARCHIVED`

A package cannot become `READY` until the delivery checklist passes and the legal license reference is approved.
