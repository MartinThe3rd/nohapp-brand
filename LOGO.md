# nohapp! logo: parts and animation

The logo exists in two states that the app can switch between:

- **withHand**: "no", "h", "app!" and the wavy underline, with the smiling hand placed in front of the h. The hand hides the h completely, and the letters are spaced wider so the hand sits clear of the "o" and "a".
- **textOnly**: the plain word "nohapp!" with normal, even letter spacing and a slightly shorter underline. No hand.

The h is always a real, typed letter. In the withHand state it is simply covered by the hand. This means the app can fade, scale or move the hand away and the h is already there underneath.

## Files

```
logos/
  nohapp-logo-<variant>.svg              complete logo, withHand state, transparent, tight crop
  nohapp-logo-<variant>-on-<bg>.svg      same on its background color, 1200×600 (presentations)
  wordmark/nohapp-wordmark-<variant>.svg complete logo, textOnly state, transparent, tight crop
  wordmark/...-on-<bg>.svg               same on its background, 1200×600
  parts/layout.json                      positions of every part in both states
  parts/<variant>/no.svg                 "no"
  parts/<variant>/h.svg                  "h"
  parts/<variant>/app.svg                "app!"
  parts/<variant>/hand.svg               the smiling hand
  parts/<variant>/underline.svg          wavy underline, withHand width
  parts/<variant>/underline-text.svg     wavy underline, textOnly width
```

`<variant>` is one of:

| Variant | Letters | Underline | Hand | Use on |
|---|---|---|---|---|
| `light-color` | white `#FFFFFF` | yellow `#FFC928` | yellow, full color | turquoise `#14ACBF` |
| `light-mono` | navy `#0B3B4A` | navy | solid navy, details cut out in sand | sand `#FFF6E0` / light backgrounds |
| `dark-color` | teal `#2EC4D6` | yellow `#FFC928` | yellow, full color | navy `#0A2A33` / dark backgrounds |
| `dark-mono` | sand `#FFF6E0` | sand | solid sand, details cut out in navy | navy `#0A2A33` / dark backgrounds |

The monochrome logos (`nohapp-logo-light-mono.svg`, `nohapp-logo-dark-mono.svg`) are text only: the hand is a separate character now, so in one color the logo is just the wordmark. The mono hand part is still provided, in a solid style that matches the weight of the letters, in case the app animates the hand onto a monochrome logo.

In the monochrome variants the letters and the underline are the same color, so the underline has small gaps where the two "p" tails cross it; this keeps the letters reading as in front of the line. The gaps are built into the mono `underline.svg` and `underline-text.svg` (each matches the letter positions of its own state). The color variants don't need them.

The geometry is identical in every variant; only the colors change. So `parts/layout.json` is shared by all four.

## parts/layout.json

All numbers are in points. 1 point = 1 px when the letters are set at 220 px. To draw the logo at any size, multiply every value by the same factor, for example `scale = desiredWidth / canvas.width`.

Both states use **one shared coordinate space**:

- the origin (0, 0) is the top-left of the withHand logo, and `canvas` is its size;
- the letters sit on the same baseline in both states, so their `y` never changes;
- the textOnly word is centered on the same vertical center line as the withHand logo.

So every part has a frame `{x, y, width, height}` in each state, and going from one state to the other is just animating each part's frame and opacity. Nothing jumps.

`contentBounds` in each state is the tight box around what is visible in that state, for when the logo is shown statically and should be cropped.

Each part SVG's own size equals its `width`/`height` in the layout, so it can be drawn into its frame at 1:1 (times your scale), never stretched. The one exception is the underline: it has two files with different widths. Crossfade between `underline.svg` and `underline-text.svg`, or scale the underline horizontally during the move (the difference is under 10%, so the stroke does not visibly distort).

Draw order, back to front: `underline`, `no`, `h`, `app`, `hand`.

## Animating between the states

withHand → textOnly:
1. The hand animates out: fade and scale down (or drop/slide) from its withHand frame. In the textOnly state it has `visible: false`, and its frame there follows the h, so it can also move along with the h while it fades.
2. At the same time "no", "h" and "app!" move from their withHand x to their textOnly x ("no" and "app!" slide toward the h).
3. The underline shortens: crossfade or scale-x between the two underline files.

textOnly → withHand is the same in reverse; the hand pops in on top of the h as the letters make room.

A spring of about 0.4–0.6 s works well. Keep the letters' scale at 1; only move them.

## Hand character

The hand in the logo is the same drawing as `characters/hand/hand-standard.svg`, so the separate character animations (wake-up, blink) can be swapped in for the logo hand if desired. In the logo the hand is drawn at `parts/<variant>/hand.svg` size, which is 1.12× the character's 200-unit artboard.
