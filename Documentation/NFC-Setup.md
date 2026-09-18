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

## Print Pause

Pause at the final layer where the NFC cavity is still open.

At the pause:

1. Make sure the tag lies flat.
2. Keep the antenna from folding.
3. Make sure nothing projects above the cavity.
4. Resume the print.
5. Confirm the next layer closes over the tag cleanly.
