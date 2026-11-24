# Print Settings

This is the final process profile extracted from the active project settings in the November 24, 2026 Bambu Studio 3MF (version 02.09.01.70) for the NFC business card on a Bambu Lab A1 with a 0.2 mm nozzle. I am documenting them so anyone who wants to make a similar card has a clear starting point.

These settings are optimized for a thin, face-down, multicolor card with small text, a detailed graphic, a QR code, and an embedded NFC tag. They are not universal settings for every printer or filament, so use Bambu Studio Preview and a small test coupon before committing to a full card.

## Printer and Material

- **Printer:** Bambu Lab A1
- **Nozzle:** 0.2 mm
- **Flow:** Standard
- **Material:** PLA
- **Base process:** 0.10 mm Standard @ BBL A1 0.2 nozzle
- **Front surface:** printed face-down on a holographic/effect build plate
- **Card thickness:** 0.8 mm
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
| Initial layer infill | 0.25 mm |
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
| Top surface pattern | Hilbert Curve |
| Top surface density | 100% |
| Top shell layers | 4 |
| Top shell thickness | 0.4 mm |
| Top paint penetration layers | 7 |
| Bottom surface pattern | Zig-zag (`zig-zag`) |
| Bottom surface density | 100% |
| Bottom shell layers | 4 |
| Bottom shell thickness | 0.4 mm |
| Bottom paint penetration layers | 5 |
| Internal solid infill pattern | Zig-zag (`zig-zag`) |

The saved project uses a Hilbert Curve top surface and the stored pattern identifier `zig-zag` for the bottom and internal solid infill. The saved infill direction is 45°. The earlier horizontal 0° toolpath was a development revision.

### Sparse Infill

| Setting | Value |
|---|---:|
| Sparse infill density | 100% |
| Fill multiline | 1 |
| Sparse infill pattern | Zig-zag (`zig-zag`) |
| Length of sparse infill anchor | 400% |
| Maximum length of sparse infill anchor | 20 |
| Infill/Wall overlap | 15% |
| Infill direction | 45° |

At 100% infill, the card prints essentially solid except for the modeled NFC cavity. At 0.8 mm thickness and 0.10 mm layer height, there are eight nominal layers; the four top and four bottom shell layers can occupy the entire thickness. Preview the cavity, shell paths, and color transitions rather than assuming a separate sparse-infill region exists.

## Speed

### Initial Layer

| Setting | Value |
|---|---:|
| Initial layer | 12 mm/s |
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
| Top surface | 40 mm/s |
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

## Filament and Retraction

| Setting | Saved value |
|---|---|
| Nozzle temperature, first and later layers | 220°C |
| Selected bed type | High Temp Plate |
| High Temp Plate temperature, first and later layers | 65°C |
| Filament flow ratio | 0.98 (all four slots) |
| Machine retraction length | 0.8 mm |
| Retraction / deretraction speed | 30 / 30 mm/s |
| Machine minimum retraction travel | 1 mm |
| Machine wipe distance | 2 mm |
| Machine retract before wipe | 0% |
| Z hop | 0.4 mm (Auto Lift) |
| White Generic PLA minimum retraction travel | 0.2 mm |
| White Generic PLA retract before wipe | 70% |
| White Generic PLA wipe distance | 0.5 mm |
| White Generic PLA max volumetric speed | 1.6 mm³/s |
| Other Bambu PLA Basic slots max volumetric speed | 2.0 mm³/s |
| Prime tower | Enabled |
| Supports | Disabled |

The white Generic PLA slot explicitly overrides retraction and wipe settings; the other slots inherit the machine defaults for those fields. The configured 0.98 flow ratio is a saved value, not a measured calibration result.

## First-Layer Graphics

The front is printed face-down, so the first layer is the presentation surface.

During development, horizontal first-layer passes were tested to reduce visible diagonal lines. The final saved project has a 45° infill-direction setting; inspect the actual first-layer paths in Preview rather than assuming their orientation.

Before printing, use **Preview** and confirm:

1. The white front graphics appear exactly where expected.
2. The black body fills cleanly around them.
3. The graphics do not extend through more layers than needed.
4. Later layers return to the body color until the back graphics begin.

Keeping the front graphics shallow reduces filament changes and purge waste.

## NFC Pause

The NFC tag should be inserted at the last layer where the cavity is still open. The pause must be checked again for the final 0.8 mm geometry; the thicker 1.6 mm version is superseded. The saved cavity negative volumes are 0.10 or 0.12 mm deep, centered at Z ≈ 0.40 mm. The saved custom pause M400 U1 is at Z = 0.50 mm for plate ID 3 only. The two listed plates (IDs 1 and 2) have no recorded pause. Inspect the closure sequence and set the pause before the first bridging/closing layer on the intended plate.

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

The active `Metadata/project_settings.config` is the source for the final values. The embedded process preset retains older values (0.14 mm initial layer height, 20 mm/s initial infill speed, 60 mm/s top speed); these are not the active project values. The source project contains multiple designs and is not published. No sliced G-code or print-time/material estimates were present. Filament behavior, build plates, and printer calibration can still change the result. Verify a test print before batching.
