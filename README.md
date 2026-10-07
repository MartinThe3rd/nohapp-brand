# nohapp-brand

Brand assets for nohapp!: the "no👍app!" wordmark and app icons.

## logos/

Transparent background, cropped tightly to the artwork (lettering, thumb and wave), 832×221 units.

| File | Use |
|---|---|
| `nohapp-logo-light-color.svg` | White lettering, yellow hand and wave. Place on turquoise `#14ACBF` or another saturated color |
| `nohapp-logo-light-mono.svg` | Navy `#0B3B4A`, for light backgrounds |
| `nohapp-logo-dark-color.svg` | Teal `#2EC4D6` lettering, yellow hand and wave, for dark backgrounds |
| `nohapp-logo-dark-mono.svg` | Sand `#FFF6E0`, for dark backgrounds |

The inside of the hand in the mono logos is filled (sand in light mono, navy in dark mono) so the outlines don't overlap visually.

### With background (presentations)

1200×600, logo centered on its background color:

- `nohapp-logo-light-color-on-turquoise.svg`
- `nohapp-logo-light-mono-on-sand.svg`
- `nohapp-logo-dark-color-on-navy.svg`
- `nohapp-logo-dark-mono-on-navy.svg`

All logos are vectors with the lettering converted to outlines (font: Fredoka SemiBold, SIL Open Font License), so no font install is needed.

## icons/

App icons go here.

## characters/hand/

The hand character on its own (not the logo), 512×512, transparent:

- `hand-standard.svg` / `.png`: smiling, thumb up
- `hand-resting.svg` / `.png`: asleep, thumb folded down onto the fingers

## animations/

All animations are 30 fps, 512×512, transparent. Each comes as an animated PNG (APNG) plus numbered frames in `frames/png/` and `frames/svg/`. The hand is drawn at the same scale in every frame and matches the static poses above.

| Animation | File | Frames | Length |
|---|---|---|---|
| Wake up: resting → standard | `animations/wake/hand-wake.png` | 28 | 0.93 s, ends on standard |
| Blink once | `animations/blink/hand-blink-single.png` | 7 | 0.23 s |
| Blink twice | `animations/blink/hand-blink-double.png` | 18 | 0.6 s |
| Blink loop (pre-baked) | `animations/blink/hand-blink-loop.png` | 526 | 17.5 s, loops |

The blink clips start and end on the open-eyed standard pose, so they can be played on top of `hand-standard.png` at any moment.

### Randomized blinking in the app

For blinking that is actually random, show `hand-standard.png`, wait a random 2–4 s, then play either the single or the double blink (for example 70% single, 30% double), and repeat. `hand-blink-loop.png` is a ready-made 17.5 s loop with a fixed pattern that feels random, for places where an animated image is simpler.

### Using them on iOS

- APNG: load with ImageIO (`CGAnimateImageAtURLWithBlock`), or in SwiftUI/UIKit through any APNG-capable image view.
- Frames: `UIImage.animatedImage(with: frames, duration: Double(frames.count) / 30)` with the PNGs from `frames/png/`, with `animationRepeatCount = 1` for one-shots like wake and blink.

## Palette

- Teal `#12A0B5` · Turquoise `#14ACBF` · Bright teal (dark mode) `#2EC4D6`
- Yellow `#FFC928` · Ink `#0B3B4A` · Sand `#FFF6E0` · Navy `#0A2A33`
