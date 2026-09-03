# Omega House Product Packaging Manifest

**Branch:** `packaging/omega-house-products-2026-09-03`

This branch consolidates the canonical documentation and packaging map for the current Omega House product system.

## Product map

| Product | Studio Drop | Canonical docs | Visual assets | Shopify role |
|---|---|---|---|---|
| FLAGSHIP BEATS | STUDIO-DROP.001 | `docs/products/STUDIO-DROP-001/` + historical beta license | `assets/flagship/Omega_House_Flagship_Beats_Box.png` | Production / flagship suite |
| REBELLION VOL. ONE | STUDIO-DROP.002 | `docs/products/STUDIO-DROP-002/` + `docs/rebellion/` | `assets/rebellion/` | Studio Drop / premium production product |

## Included in this packaging branch

- Existing canonical Studio Drop.001 filing for FLAGSHIP BEATS
- FLAGSHIP BEATS beta licensing document
- FLAGSHIP BEATS packaging artwork
- New canonical Studio Drop.002 filing for REBELLION VOL. ONE
- REBELLION VOL. ONE master product license
- REBELLION VOL. ONE packaging artwork
- Shopify packaging maps and release controls

## Binary asset delivery note

The repository packaging layer contains the canonical paths and release metadata. Large binary payloads should be transferred through the local Git working copy with Git LFS where appropriate. GitHub recommends Git LFS for large binary files, and regular Git blocks files above 100 MiB.

The local staging set prepared for this branch is:

- `assets/flagship/Omega_House_Flagship_Beats_Box.png`
- `assets/rebellion/Rebellion_Studio_Drop_002_Box.png`
- `assets/rebellion/Rebellion_Vol_One_Sample_Pack.png`
- `docs/flagship/Omega_House_Flagship_Beats_Beta_Licensing_Package_v1.0.docx`
- `docs/rebellion/REBELLION_VOL_ONE_MASTER_PRODUCT_LICENSE.pdf`

Final customer-download ZIPs should be generated from the frozen production payload, not from the repository source archive.
