# Omega House Flagship Beat — Packaging Template v1

Production-ready package structure for a single flagship beat sold through Omega House Beats.

## Package contract

Every flagship beat package is built around one canonical `beat.json` manifest. Audio filenames, metadata, licensing, artwork, delivery files, and checksums resolve from that manifest.

```text
<BEAT-SLUG>/
├── README.md
├── beat.json
├── metadata/
│   ├── product.csv
│   ├── audio.csv
│   └── licensing.csv
├── audio/
│   ├── preview/
│   ├── master/
│   └── stems/
├── midi/
├── artwork/
├── licenses/
│   ├── basic/
│   ├── premium/
│   └── exclusive/
├── docs/
└── checksums/
```

## Required delivery assets

- Full beat master WAV
- Tagged/preview MP3 or WAV
- Individual stems, if included by license tier
- MIDI, if included by license tier
- Product artwork
- License document/reference for purchased tier
- Machine-readable metadata
- SHA-256 checksum manifest

## Naming standard

Use:

`OHFB-<YEAR>-<SEQUENCE>_<TITLE>_<ASSET>_<KEY>_<BPM>_<VERSION>.<EXT>`

Example:

`OHFB-2026-0001_NIGHTFALL_MASTER_FMIN_140_V1.wav`

Rules:

- lowercase or uppercase must be consistent within a package
- no spaces
- key and BPM are mandatory for audio assets
- version is mandatory for rendered assets
- never overwrite a released master; increment version

## Tier separation

The package is organized so the fulfillment layer can select files by license tier without duplicating the canonical source assets.

`BETA`, `BASIC`, `PREMIUM`, and `EXCLUSIVE` are the canonical planned tiers in the licensing system. Exact rights text must remain governed by the approved legal license documents.

## Binary asset policy

GitHub stores the manifest, metadata, documentation, templates, and checksums. Large production audio binaries should be attached through the selected delivery/storage system rather than committed directly to this repository unless repository policy explicitly permits it.
