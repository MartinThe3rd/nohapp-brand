# nohapp-brand

Brand assets for nohapp!: the "no👍app!" wordmark and app icons.

## logos/

The main logo is "no👍app!": the word "nohapp!" typed out in Fredoka SemiBold, with the smiling hand in front of the h, hiding it completely, plus the wavy underline. There is also a text-only version, and the logo is available as separate parts so the app can animate between the two. See [LOGO.md](LOGO.md) for the full guide.

| Files | What |
|---|---|
| `logos/nohapp-logo-<variant>.svg` | Logo with hand, transparent, tightly cropped |
| `logos/nohapp-logo-<variant>-on-<bg>.svg` | Logo with hand on its background, 1200×600 |
| `logos/wordmark/nohapp-wordmark-<variant>.svg` | Text-only "nohapp!", transparent, tightly cropped |
| `logos/wordmark/nohapp-wordmark-<variant>-on-<bg>.svg` | Text-only on its background, 1200×600 |
| `logos/parts/<variant>/` | `no`, `h`, `app`, `hand`, `underline`, `underline-text` as separate SVGs |
| `logos/parts/layout.json` | Where each part goes, in both states |

Variants: `light-color` (white letters, for turquoise `#14ACBF`), `light-mono` (navy, for light backgrounds), `dark-color` (teal `#2EC4D6` letters, for dark backgrounds), `dark-mono` (sand, for dark backgrounds). All are vectors with the letters converted to outlines (Fredoka, SIL Open Font License), so no font install is needed.

## icons/

App icons go here.

## characters/hand/

The hand character on its own (not the logo), 512×512, transparent:

- `hand-standard.svg` / `.png`: smiling, thumb up
- `hand-resting.svg` / `.png`: asleep, thumb folded down onto the fingers
- `hand-accept.svg` / `.png`: excited thumbs-up with star eyes, for accept / approve
- `hand-deny.svg` / `.png`: the hand flipped to a thumbs-down with a disappointed "sigh" face, for deny / reject

## animations/

All animations are 30 fps, transparent, and 512×512 unless noted. Each comes as an animated PNG (APNG) plus numbered frames in `frames/png/` and `frames/svg/`. The hand is drawn at the same scale in every frame and matches the static poses above.

| Animation | File | Frames | Length |
|---|---|---|---|
| Wake up: resting → standard | `animations/wake/hand-wake.png` | 28 | 0.93 s, ends on standard, 563×563 (see note) |
| Blink once | `animations/blink/hand-blink-single.png` | 7 | 0.23 s |
| Blink twice | `animations/blink/hand-blink-double.png` | 18 | 0.6 s |
| Blink loop (pre-baked) | `animations/blink/hand-blink-loop.png` | 526 | 17.5 s, loops |
| Accept: blink once | `animations/blink-accept/hand-accept-blink-single.png` | 7 | 0.23 s |
| Accept: blink twice | `animations/blink-accept/hand-accept-blink-double.png` | 18 | 0.6 s |
| Accept: blink loop (pre-baked) | `animations/blink-accept/hand-accept-blink-loop.png` | 526 | 17.5 s, loops |
| Deny: head shake (loop) | `animations/deny-shake/hand-deny-shake.png` | 24 | 0.8 s per shake, loops seamlessly |

The wake-up animation rotates the hand around its bottom-left corner (the wrist), so it needs a little more room: its frames are 563×563 instead of 512×512, at the same scale. Align it with the other assets by its top-left corner; its last frame then sits exactly on top of `hand-standard.png`. Its first frame is the resting pose turned around that corner, so it sits a little lower and further right than the standalone `hand-resting.png`.

The blink clips start and end on the open-eyed pose, so they can be played on top of the matching still image at any moment: `animations/blink/` on top of `hand-standard.png`, and `animations/blink-accept/` on top of `hand-accept.png`. Both use the same blink timing and the same loop pattern. The deny head shake (`animations/deny-shake/`) loops continuously on top of `hand-deny.png`: only the face turns, as if on an invisible round head, about 11° each way; the hand itself stays still.

### Randomized blinking in the app

For blinking that is actually random, show `hand-standard.png`, wait a random 2–4 s, then play either the single or the double blink (for example 70% single, 30% double), and repeat. `hand-blink-loop.png` is a ready-made 17.5 s loop with a fixed pattern that feels random, for places where an animated image is simpler.

### Using them on iOS

- APNG: load with ImageIO (`CGAnimateImageAtURLWithBlock`), or in SwiftUI/UIKit through any APNG-capable image view.
- Frames: `UIImage.animatedImage(with: frames, duration: Double(frames.count) / 30)` with the PNGs from `frames/png/`, with `animationRepeatCount = 1` for one-shots like wake and blink.

## Palette

- Teal `#12A0B5` · Turquoise `#14ACBF` · Bright teal (dark mode) `#2EC4D6`
- Yellow `#FFC928` · Ink `#0B3B4A` · Sand `#FFF6E0` · Navy `#0A2A33`
