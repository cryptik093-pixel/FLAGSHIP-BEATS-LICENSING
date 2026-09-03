# Flagship Beat Delivery QA

## Audio

- [ ] Master WAV rendered and auditioned end-to-end
- [ ] Preview render matches approved master
- [ ] Key confirmed
- [ ] BPM confirmed
- [ ] Sample rate confirmed
- [ ] Bit depth confirmed
- [ ] No clipping, unwanted silence, clicks, pops, or truncated tails
- [ ] Stems begin at the same absolute start point
- [ ] Stems have matching sample rate/bit depth
- [ ] MIDI opens correctly and contains intended musical data

## Metadata

- [ ] Product ID assigned
- [ ] Title/slug finalized
- [ ] Audio metadata matches rendered files
- [ ] Shopify handle mapped
- [ ] License tier/version references approved legal source
- [ ] No secrets or customer PII included

## Packaging

- [ ] Artwork supplied at approved production dimensions
- [ ] License documents supplied only for the purchased tier
- [ ] README included
- [ ] SHA-256 checksums generated
- [ ] ZIP/package tested by extracting to a clean directory
- [ ] All links/paths in manifest resolve

## Shopify release gate

- [ ] Digital product/variant is correctly mapped
- [ ] Price and license tier are correct
- [ ] Fulfillment automation points to the correct package
- [ ] Test purchase completed
- [ ] Download/access verified from customer perspective
- [ ] License issuance is idempotent

## Release status

`DRAFT -> QA -> READY -> PUBLISHED -> ARCHIVED`
