# Build Notes

## Goal

I wanted a business card that was still professional but showed some of the way I work as an engineering student.

The card combines:

- 3D printing
- CAD
- multicolor first-layer graphics
- NFC
- QR
- Project Atlas branding
- a web portfolio

## Prototype 1

The first prototype was about 0.8 mm thick and printed with a 0.4 mm nozzle. The color order was wrong, but it proved the Atlas graphic and layout were printable.

## Prototype 2

The next version used a black card with white graphics. The QR code worked, but small text was rough and the card was still too thin.

## 0.2 mm Nozzle

I switched to the official Bambu 0.2 mm A1 hotend for the final detail work. This helped most with:

- text
- Atlas graphic
- NFC symbol
- QR edges

## First-Layer Problems

The biggest issue was stringing between nearby letters. A string could catch a previous feature and pull it out of place.

I also saw tiny blobs at the final fill of some letters, so I treated that as a toolpath/flow problem instead of just making the letters larger.

## White Graphic Depth

When the white graphics extended into multiple layers, the print created too many filament changes and a lot of purge waste.

The final approach was to keep the visible front graphics as shallow as practical and verify the result in Preview.

## NFC

The NFC tag was programmed and tested before being embedded.

The URL opens:

`https://ethantsui2.github.io/Project-Atlas/`

A user does not need the NFC Tools app to open it.


## Current Design Revision

The front layout was refined without changing the overall concept:

- Project Atlas graphic kept as the main visual
- `ETHAN TSUI` and `MECHANICAL ENGINEERING` kept as the main identity block
- `TAP TO CONNECT` kept compact instead of making it wider
- NFC/contactless icon reduced slightly so it does not overpower the text
- `DESIGN • BUILD • SOLVE` kept centered at the bottom

The back was simplified around one centered QR code and `SCAN TO CONNECT`.

The QR code is approximately **33 mm square**. I kept it large enough to scan reliably without letting it dominate the full back of the card.

The QR code points to my **LinkedIn**, while the embedded NFC tag points to the **Project Atlas portfolio website**. This gives two different connection paths:

- NFC tap -> project portfolio
- QR scan -> LinkedIn

## Toolpath Revision

A 45° first-layer infill direction looked smooth physically, but the diagonal extrusion lines were still visible under the holographic finish.

The current version uses:

- Rectilinear bottom surface pattern
- 0° infill direction
- horizontal first-layer passes across the long edge of the card
- 0.20 mm initial-layer line width
- Arachne minimum wall width at 75%
- Arachne minimum feature size at 15%

This reduced the large sliced gaps that appeared in narrow Atlas features while keeping the first-layer detail readable.
