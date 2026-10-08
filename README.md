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

Variants: `light-color` (white letters, for turquoise `#14ACBF`), `light-mono` (navy, for light backgrounds), `dark-color` (teal `#2EC4D6` letters, for dark backgrounds), `dark-mono` (sand, for dark backgrounds). The two monochrome logos are text only, without the hand. All are vectors with the letters converted to outlines (Fredoka, SIL Open Font License), so no font install is needed.

## icons/

App icons, the smiling hand on a sky background. Each comes as SVG and as a 1024×1024 PNG.

| File | Use |
|---|---|
| `nohapp-app-icon-light-color.png` | Main app icon (daylight sky gradient) |
| `nohapp-app-icon-dark-color.png` | Dark-mode app icon (night sky with a few stars) |
| `nohapp-app-icon-light-mono.png` | Monochrome, navy line drawing on sand |
| `nohapp-app-icon-dark-mono.png` | Monochrome, sand line drawing on navy |
| `*-rounded.svg` / `*-rounded.png` | Same icons with rounded corners, for websites, mockups and presentations |

The plain (square) files are for Xcode and the App Store: square corners and no transparency, because iOS rounds the corners itself. On iOS 18 and later, the light and dark color icons can be set as the app icon's "Any" and "Dark" appearances in the asset catalog.

## characters/hand/

The hand character on its own (not the logo), 512×512, transparent:

- `hand-standard.svg` / `.png`: smiling, thumb up
- `hand-resting.svg` / `.png`: asleep, thumb folded down onto the fingers
- `hand-accept.svg` / `.png`: excited thumbs-up with star eyes, for accept / approve
- `hand-surprised.svg` / `.png`: Happy surprised: the standard thumbs-up with slightly bigger eyes, raised eyebrows and a small round "o" mouth
- `hand-happy-sad.svg` / `.png`: Happy Sad: worried eyebrows, glossy eyes and a small frown, with the thumb drooping to the right in one smooth arc (18°)
- `hand-happy-dead.svg` / `.png`: Happy Dead: the resting hand (thumb folded), pale, with X eyes and her tongue out
- `hand-deny.svg` / `.png`: the hand flipped to a thumbs-down with a disappointed "sigh" face, for deny / reject
- `hand-hello.svg` / `.png`: a waving open hand (👋) with raised brows and an open, calling-out mouth, for hello / greetings
- `hand-annoyed.svg` / `.png`: the resting hand (thumb folded) with the disappointed "sigh" face from the deny hand, for annoyed

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
| Deny / thumbs-down (loop) | `animations/deny/hand-deny-animated.png` | 24 | 0.8 s per head shake, loops seamlessly |
| Annoyed (loop) | `animations/annoyed/hand-annoyed-animated.png` | 24 | 0.8 s per head shake, loops seamlessly |
| Hello: blink once | `animations/blink-hello/hand-hello-blink-single.png` | 7 | 0.23 s |
| Hello: blink twice | `animations/blink-hello/hand-hello-blink-double.png` | 18 | 0.6 s |
| Hello: blink loop (pre-baked) | `animations/blink-hello/hand-hello-blink-loop.png` | 526 | 17.5 s, loops |
| Surprised: blink once | `animations/surprised/hand-surprised-blink-single.png` | 7 | 0.23 s |
| Surprised: blink twice | `animations/surprised/hand-surprised-blink-double.png` | 18 | 0.6 s |
| Surprised: blink loop (pre-baked) | `animations/surprised/hand-surprised-blink-loop.png` | 526 | 17.5 s, loops |
| Happy Sad (standard → sad) | `animations/happy-sad/hand-happy-sad-animated.png` | 18 | 0.6 s, plays once |
| Happy Sad reverse (sad → standard) | `animations/happy-sad/hand-happy-sad-reverse.png` | 18 | 0.6 s, plays once |
| Happy Dead (standard → dead) | `animations/happy-dead/hand-happy-dead-animated.png` | 27 | 0.9 s, plays once |
| Happy Dead reverse (dead → standard) | `animations/happy-dead/hand-happy-dead-reverse.png` | 27 | 0.9 s, plays once |
| Happy Sad → Dead | `animations/happy-sad-dead/hand-happy-sad-dead-animated.png` | 27 | 0.9 s, plays once |
| Happy Dead → Sad (reverse) | `animations/happy-sad-dead/hand-happy-sad-dead-reverse.png` | 27 | 0.9 s, plays once |
| Happy Dead → Excited (revive) | `animations/happy-dead-excited/hand-happy-dead-excited-animated.png` | 33 | 1.1 s, plays once |
| Happy Excited → Dead (reverse) | `animations/happy-dead-excited/hand-happy-dead-excited-reverse.png` | 33 | 1.1 s, plays once |

The wake-up animation rotates the hand around its bottom-left corner (the wrist), so it needs a little more room: its frames are 563×563 instead of 512×512, at the same scale. Align it with the other assets by its top-left corner; its last frame then sits exactly on top of `hand-standard.png`. Its first frame is the resting pose turned around that corner, so it sits a little lower and further right than the standalone `hand-resting.png`.

The blink clips start and end on the open-eyed pose, so they can be played on top of the matching still image at any moment: `animations/blink/` on top of `hand-standard.png`, `animations/blink-accept/` on top of `hand-accept.png`, `animations/blink-hello/` on top of `hand-hello.png` (its eyes close into happy curved lids while the eyebrows lift), and `animations/surprised/` on top of `hand-surprised.png` (the eyebrows stay raised while she blinks). All four use the same blink timing and the same loop pattern. The deny / thumbs-down animation (`animations/deny/`) is a head shake that loops continuously on top of `hand-deny.png`: only the face turns, as if on an invisible round head, about 11° each way; the hand itself stays still. The annoyed animation (`animations/annoyed/`) is the same head shake on the resting hand, played on top of `hand-annoyed.png`. The Happy Sad animation (`animations/happy-sad/`) is a one-shot transition: its first frame is identical to `hand-standard.png` and its last frame to `hand-happy-sad.png`, so swap in the matching still when it ends; the reverse file goes back from sad to standard. Happy Dead (`animations/happy-dead/`) works the same way: it starts on `hand-standard.png` and ends on `hand-happy-dead.png` (the thumb folds down into the resting fist, the color drains to pale, the eyes close and turn into X marks, and the tongue pops out). `animations/happy-sad-dead/` goes from `hand-happy-sad.png` to `hand-happy-dead.png` the same way (and back with the reverse file), so the three states chain: standard → sad → dead. `animations/happy-dead-excited/` brings her back: it starts on `hand-happy-dead.png` and ends on `hand-accept.png` (the excited star-eyes face), with the thumb springing up, the color returning, the X eyes turning into closed lids and then popping open as stars.

### Randomized blinking in the app

For blinking that is actually random, show `hand-standard.png`, wait a random 2–4 s, then play either the single or the double blink (for example 70% single, 30% double), and repeat. `hand-blink-loop.png` is a ready-made 17.5 s loop with a fixed pattern that feels random, for places where an animated image is simpler.

### Using them on iOS

- APNG: load with ImageIO (`CGAnimateImageAtURLWithBlock`), or in SwiftUI/UIKit through any APNG-capable image view.
- Frames: `UIImage.animatedImage(with: frames, duration: Double(frames.count) / 30)` with the PNGs from `frames/png/`, with `animationRepeatCount = 1` for one-shots like wake and blink.

## Palette

- Teal `#12A0B5` · Turquoise `#14ACBF` · Bright teal (dark mode) `#2EC4D6`
- Yellow `#FFC928` · Ink `#0B3B4A` · Sand `#FFF6E0` · Navy `#0A2A33`
