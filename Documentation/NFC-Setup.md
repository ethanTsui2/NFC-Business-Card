# NFC Setup

## Tag

The card uses an **NTAG215** NFC sticker/tag.

The NFC record points to:

`https://ethantsui2.github.io/Project-Atlas/`

## Programming

I used NFC Tools:

1. Open **Write**.
2. Select **Add a record**.
3. Choose **URL / URI**.
4. Enter the portfolio URL.
5. Select **Write**.
6. Hold the phone over the tag until the write succeeds.
7. Close the app and test the tag normally.

Other people do not need NFC Tools to open the site.

## Before Embedding

- program the tag first
- confirm the URL opens correctly
- test through a similar amount of PLA if possible
- leave the tag writable unless there is a reason to permanently lock it

## Final 0.8 mm Card

The final body thickness is 0.8 mm. Verify the tag's actual thickness without its release liner and confirm that the modeled cavity leaves continuous PLA above and below it. In the November 24, 2026 project, the negative-volume cavities measure 26 × 26 × 0.10 mm or 26 × 25 × 0.12 mm (bounding dimensions), centered at approximately Z = 0.40 mm. The saved custom pause command is M400 U1 at Z = 0.50 mm, associated only with plate ID 3. The two listed plate configurations (IDs 1 and 2) do not have recorded pauses. This is not verification that the cavity is open at the pause: re-slice, inspect the layer immediately before closure, and add or move the pause on the intended plate. A 25 × 25 mm square tag may not fit a circular/elliptical pocket of these bounding dimensions unless its actual shape fits; check the physical tag. Do not reuse pause heights from the 1.6 mm revision.

## Print Pause

Pause at the final layer where the NFC cavity is still open.

At the pause:

1. Make sure the tag lies flat.
2. Keep the antenna from folding.
3. Make sure nothing projects above the cavity.
4. Resume the print.
5. Confirm the next layer closes over the tag cleanly.
6. After the card cools, test the NFC again and scan the QR code.
