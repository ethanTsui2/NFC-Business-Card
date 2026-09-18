# NFC Business Card

A custom 3D printed business card that combines multicolor FDM printing, an embedded NFC tag, a QR code backup, and a web portfolio.

I built this because I wanted something more memorable than a normal paper card for career fairs. The goal was to make the card feel like a small engineering project on its own while still being clean enough to use professionally.

## Final Concept

- Standard business-card footprint: **85.6 x 54 mm**
- Target thickness: **1.6 mm**
- Printer: **Bambu Lab A1**
- Nozzle: **0.2 mm**
- Material: PLA
- Front: black body with white graphics printed face-down on a holographic/effect plate
- NFC: embedded **NTAG215** tag
- Backup: functional QR code
- Link target: [Project Atlas portfolio](https://ethantsui2.github.io/Project-Atlas/)

The NFC tag has been programmed and tested successfully. A phone can open the site directly without needing the NFC Tools app.

## Front Design

The front uses my Project Atlas robotic arm and keeps the information minimal:

- Atlas arm graphic
- `TAP TO CONNECT`
- `ETHAN TSUI`
- `MECHANICAL ENGINEERING`
- `DESIGN • BUILD • SOLVE`
- NFC symbol

The front graphics print against the build plate so the visible surface picks up the holographic finish.

## Back Design

The back uses a QR code as a fallback and is intentionally simple:

- QR code
- `SCAN TO CONNECT`

## Why I Used a 0.2 mm Nozzle

The first prototypes were printed with a 0.4 mm nozzle. The concept worked, but the smallest text and white-to-black boundaries were rough.

Moving to the 0.2 mm nozzle gave me better control over:

- small lettering
- thin Atlas geometry
- QR-code edges
- first-layer multicolor detail
- cleaner graphic boundaries

## NFC Integration

The NFC tag is embedded inside the card rather than attached to the outside.

Basic process:

1. Model a shallow internal cavity.
2. Print until the cavity is still open.
3. Pause the print.
4. Insert the programmed NFC tag.
5. Resume the print so the remaining layers close the cavity.

See [NFC Setup](Documentation/NFC-Setup.md).

## Print Development

Main problems I worked through:

- stringing between small letters
- strings pulling on previously printed letters
- tiny blobs at the end of letter fills
- excessive filament changes when white graphics extended through multiple layers
- small-text limits with the 0.4 mm nozzle
- front/back graphics showing through on early 0.8 mm prototypes

See [Print Settings](Documentation/Print-Settings.md) and [Build Notes](Documentation/Build-Notes.md).

## Repository Guide

| Folder | What it contains |
|---|---|
| [`CAD/`](CAD/) | Final card CAD and NFC cavity notes |
| [`Print-Files/`](Print-Files/) | Slicer/project files and export notes |
| [`Documentation/`](Documentation/) | NFC setup, print settings, and build notes |
| [`Images/`](Images/) | Final card photos and prototype images |

## Project Status

The NFC workflow has been tested successfully and the card design has gone through multiple print iterations. The current version uses the 0.2 mm nozzle and embedded NFC approach developed from those tests.

## Related Project

The card links directly to my main engineering portfolio for [Project Atlas](https://ethantsui2.github.io/Project-Atlas/).

## License

This project is released under the [MIT License](LICENSE).
