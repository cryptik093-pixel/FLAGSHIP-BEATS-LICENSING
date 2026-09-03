# Shopify Packaging Map — Studio Drop.002

## Product

**REBELLION VOL. ONE | CINEMATIC MELODIES & STEMS**

### Customer-facing assets

1. Product hero / primary image: `assets/rebellion/Rebellion_Studio_Drop_002_Box.png`
2. Secondary product image: `assets/rebellion/Rebellion_Vol_One_Sample_Pack.png`
3. Customer-facing license: `docs/rebellion/REBELLION_VOL_ONE_MASTER_PRODUCT_LICENSE.pdf`

### Digital delivery package

The final downloadable ZIP should contain the frozen production payload:

- `STEMS/` — 18 assets
- `MELODIES/` — 20 assets
- `MIDI/` — 9 assets
- `DOCUMENTATION/` — license + product readme + metadata

Do not upload unfinished source sessions, alternate renders, internal rights notes, or development files to the customer download.

### Freeze gate

Before publishing the Shopify digital delivery file:

- confirm exact asset counts;
- confirm filenames and folder structure;
- verify every audio/MIDI asset opens correctly;
- generate a SHA-256 manifest for the final ZIP;
- record the release version/date;
- attach the exact license version to the product record.

**Important:** the Git repository is the packaging source of truth; Shopify is the customer-facing distribution layer.
