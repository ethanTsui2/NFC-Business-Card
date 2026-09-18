# Print Settings

These are the settings I am currently using for the final NFC business card on a Bambu Lab A1 with a 0.2 mm nozzle. I am documenting them so anyone who wants to make a similar card has a clear starting point.

These settings are optimized for a thin, face-down, multicolor card with small text, a detailed graphic, a QR code, and an embedded NFC tag. They are not universal settings for every printer or filament, so use Bambu Studio Preview and a small test coupon before committing to a full card.

## Printer and Material

- **Printer:** Bambu Lab A1
- **Nozzle:** 0.2 mm
- **Flow:** Standard
- **Material:** PLA
- **Base process:** 0.10 mm Standard @ BBL A1 0.2 nozzle
- **Front surface:** printed face-down on a holographic/effect build plate
- **Card thickness:** approximately 1.6 mm
- **Card size:** approximately 85.6 x 54 mm

## Quality

### Layer Height

| Setting | Value |
|---|---:|
| Layer height | 0.10 mm |
| Initial layer height | 0.10 mm |
| Mixed color sublayer | Off |

### Line Width

| Setting | Value |
|---|---:|
| Default | 0.22 mm |
| Initial layer | 0.20 mm |
| Outer wall | 0.22 mm |
| Inner wall | 0.22 mm |
| Top surface | 0.22 mm |
| Sparse infill | 0.22 mm |
| Internal solid infill | 0.22 mm |
| Support | 0.22 mm |

The 0.20 mm initial-layer line width gave the slicer more room to fit small Atlas and text features without leaving obvious toolpath gaps. Preview should still be checked before printing.

## Seam

| Setting | Value |
|---|---|
| Seam position | Aligned |
| Seam placement away from overhangs | Off |
| Smart scarf seam application | On |
| Scarf application angle threshold | 155° |
| Scarf around entire wall | Off |
| Scarf steps | 10 |
| Scarf joint for inner walls | On |
| Override filament scarf seam setting | Off |
| Role-based wipe speed | On |

## Precision

| Setting | Value |
|---|---:|
| Slice gap closing radius | 0.049 mm |
| Resolution | 0.008 mm |
| Arc fitting | On |
| X-Y hole compensation | 0 mm |
| X-Y contour compensation | 0 mm |
| Auto circle contour-hole compensation | Off |
| Elephant foot compensation | 0.005 mm |
| Precise Z height | Off |

## Ironing

- **Ironing Type:** No ironing

For this project, the front finish comes from the build plate rather than ironing.

## Wall Generator

| Setting | Value |
|---|---:|
| Wall generator | Arachne |
| Wall transitioning threshold angle | 10° |
| Wall transitioning filter margin | 25% |
| Wall transition length | 100% |
| Wall distribution count | 1 |
| Minimum wall width | 75% |
| Minimum feature size | 15% |

Arachne helps preserve narrow text strokes and small graphic features. Lowering the minimum wall width to 75% and minimum feature size to 15% reduced visible gaps in the sliced Atlas gripper and other narrow first-layer features.

## Advanced Wall Settings

| Setting | Value |
|---|---|
| Order of walls | inner/outer |
| Print infill first | Off |
| Bridge flow | 1.00 |
| Thick bridges | Off |
| Bridge counterbore holes | None |
| Only one wall on top surfaces | Top surfaces |
| Only one wall on first layer | On |
| Smooth speed discontinuity area | On |
| Smooth coefficient | 80 |
| Avoid crossing wall | Off |
| Smoothing wall speed along Z | Off |

The **Only one wall on first layer** option is important for this design because it leaves more room for the face-down surface fill around the small graphics.

## Strength

### Walls

| Setting | Value |
|---|---:|
| Wall loops | 2 |
| Alternate extra wall | Off |
| Embedding wall into infill | Off |

### Top and Bottom Shells

| Setting | Value |
|---|---|
| Top surface pattern | Monotonic |
| Top surface density | 100% |
| Top shell layers | 4 |
| Top shell thickness | 0.4 mm |
| Top paint penetration layers | 7 |
| Bottom surface pattern | Rectilinear |
| Bottom surface density | 100% |
| Bottom shell layers | 4 |
| Bottom shell thickness | 0.4 mm |
| Bottom paint penetration layers | 5 |
| Internal solid infill pattern | Rectilinear |

The current version uses a Monotonic top surface for the QR side and a Rectilinear bottom surface for the face-down front. The infill direction is set to 0° so the visible first-layer lines run horizontally across the long edge of the card instead of diagonally.

### Sparse Infill

| Setting | Value |
|---|---:|
| Sparse infill density | 100% |
| Fill multiline | 1 |
| Sparse infill pattern | Rectilinear |
| Length of sparse infill anchor | 400% |
| Maximum length of sparse infill anchor | 20 |
| Infill/Wall overlap | 15% |
| Infill direction | 0° |

At 100% infill, the card prints essentially solid.

## Speed

### Initial Layer

| Setting | Value |
|---|---:|
| Initial layer | 10 mm/s |
| Initial layer infill | 15 mm/s |

These are intentionally slow because the first layer contains the visible text and graphics.

### Other Layers

| Setting | Value |
|---|---:|
| Outer wall | 60 mm/s |
| Inner wall | 80 mm/s |
| Small perimeters | 50% |
| Small perimeter threshold | 6 mm |
| Sparse infill | 100 mm/s |
| Internal solid infill | 100 mm/s |
| Vertical shell speed | 80% |
| Top surface | 60 mm/s |
| Slow down for overhangs | On |

### Overhang and Bridge Speeds

| Setting | Value |
|---|---:|
| 10% overhang | 0 mm/s |
| 25% overhang | 50 mm/s |
| 50% overhang | 30 mm/s |
| 75% overhang | 10 mm/s |
| 100% overhang | 10 mm/s |
| Slow down by height | Off |
| Bridge | 30 mm/s |
| Gap infill | 40 mm/s |
| Support | 150 mm/s |
| Support interface | 80 mm/s |

The slower bridge speed is useful for the layer that closes over the embedded NFC tag.

## Travel Speed

- **Travel:** 700 mm/s

## Acceleration

| Setting | Value |
|---|---:|
| Normal printing | 4000 mm/s² |
| Travel | 10000 mm/s² |
| Initial layer travel | 3000 mm/s² |
| Initial layer | 500 mm/s² |
| Outer wall | 2500 mm/s² |
| Inner wall | 4000 mm/s² |
| Top surface | 1500 mm/s² |
| Sparse infill | 100% |

## First-Layer Graphics

The front is printed face-down, so the first layer is the presentation surface.

For the current version, the first-layer toolpath is intentionally horizontal. The earlier 45° infill direction left diagonal lines that were visible in the finished card even though the surface itself was smooth.

Before printing, use **Preview** and confirm:

1. The white front graphics appear exactly where expected.
2. The black body fills cleanly around them.
3. The graphics do not extend through more layers than needed.
4. Later layers return to the body color until the back graphics begin.

Keeping the front graphics shallow reduces filament changes and purge waste.

## NFC Pause

The NFC tag should be inserted at the last layer where the cavity is still open.

Before starting the final print:

1. Program and test the NFC tag.
2. Confirm the pause is at the correct layer in Preview.
3. Insert the tag flat inside the cavity.
4. Resume the print.
5. Confirm the following layer closes over the tag without interference.

## Recommended Test Before a Full Card

Instead of printing the full card every time, make a small first-layer calibration coupon containing:

- part of the Atlas graphic
- your smallest text
- part of the QR code
- black and white boundaries

This makes it much faster to check stringing, blobs, first-layer fill, and graphic clarity.

## Notes

The settings above are the actual profile used during development of this card. Filament behavior, build plates, and printer calibration can still change the result, so use them as a strong starting point rather than assuming every printer will behave identically.
