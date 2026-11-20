# UPFOREX — Image Motion V2 (Standalone HTML/CSS/JS)

This is the existing standalone UPFOREX premium homepage with a new layer of premium **image-specific** animations. It is not a redesign and requires no npm/Angular installation.

## Run on Windows
1. Extract `UPFOREX_IMAGE_MOTION_HOMEPAGE.zip` fully.
2. Open the extracted `UPFOREX_IMAGE_MOTION_HOMEPAGE` folder.
3. Double-click `index.html` in Chrome/Edge. Keep `style.css`, `script.js` and the complete `assets` folder together.
4. For a local development server (optional), run `python -m http.server 8000` from that folder and visit `http://localhost:8000/`.

## New visual motions
- **Blue globe hero:** slow atmospheric blue image drift behind the existing rotating canvas Earth.
- **Welcome image:** a one-time photo focus/zoom-in with gentle sweep; soft pointer parallax on desktop.
- **Confidence photo:** separate restrained cinematic reveal and hover depth.
- **Six market images:** individual staggered image focus/zoom on reveal; slightly deeper picture zoom and card tilt on hover.
- **ECN trading video:** a cinematic entry and light reflection on the preview, preserving functional play/pause and mute controls; no continuous zoom while playing.
- **MT5 device images:** a tiny periodic vertical drift while on-screen, with smooth transitions between three original images; pointer depth on desktop.
- **Final CTA photograph:** a slow, small photographic zoom/reveal with hover refinement.

## What stayed identical to the previous HTML homepage
- `index.html` is **byte-for-byte unchanged** (all 8 homepage sections, all text, all buttons, and all link destinations).
- Original local images, font and video files are unchanged.
- Original background, blue globe accents, and green `#3cff19` brand colour are unchanged.
- No third-party libraries or remote resources were added.

## Source files
- `index.html` — original standalone homepage, unchanged.
- `style.css` — adds the section marked `IMAGERY MOTION V2` at the end.
- `script.js` — adds `initImageMotion()` and video-playing state class.
- `assets/` — original local photos, MT5 imagery, fonts, globe assets and video.

## Accessibility and performance
- Animation is progressively enhanced: images remain visible if JS is unavailable.
- `prefers-reduced-motion: reduce` removes the new motion effects.
- `IntersectionObserver` limits reveal and MT5 movement to visible content.
- Pointer-based parallax runs only for a fine pointer and is throttled with `requestAnimationFrame`.
- Motion is designed to be gentle, not continuous flashing.

## Tests carried out
- `node --check script.js` passed.
- Browser-rendering interaction tests passed in a browser-compatible, **inlined-assets** preview (direct local-server/file navigation was blocked in the test runner): 8 sections, 6 markets, working photo hover, playing video, MT5 slide switching, mobile menu, no script errors, 390px mobile width without horizontal overflow, reduced-motion check.
- Deploying the website publicly and cross-browser production hosting were **not** tested.

## Integration note
This is a **standalone homepage**, not an Angular component. If moving it into the Angular UPFOREX project, port its styles and logic into the existing Angular component instead of replacing Angular routing with `index.html`.
