# Eyad Zein — Portfolio

An interactive single-page portfolio that switches its whole identity between three modes: **Video Editing**, **Content Creation** and **Software Engineering**. Each mode has its own color system, typography and an animated way of visualizing skills.

Built with plain **HTML, CSS and JavaScript**: no framework, no build step, no dependencies.

## Features

- **Three modes in one page.** A segmented switcher swaps theme tokens, content and layout, with a full-screen wipe transition between modes.
- **Deep links per mode.** Hash-based routing (`#video`, `#content`, `#dev`) means each audience can be sent straight to the right mode, and the browser back button works.
- **Animated skill visualizations, one per mode:**
  - **Video:** skills laid out as clips on an NLE-style timeline, with a looping playhead driven by `requestAnimationFrame`, a live SMPTE-style timecode (`HH:MM:SS:FF` at 25 fps) and a readout panel for the clips under the playhead.
  - **Content:** Instagram-style story rings drawn in SVG (`stroke-dashoffset` progress), plus an auto-advancing story viewer with segmented progress bars and tap-to-navigate.
  - **Code:** a typewriter terminal intro and `skills --list` output rendered as text progress bars with eased count-up.
- **Before/after slider** using `clip-path` and a native range input, so it works with mouse, touch and keyboard.
- **Pointer-tracked glow** on project cards using CSS custom properties.
- **Responsive** from 320px phones up to wide desktops, with safe-area insets for notched devices.
- **Accessible:** ARIA tab roles on the mode switcher, visible focus states, and full support for `prefers-reduced-motion`.

## Tech

| Area | Approach |
|---|---|
| Markup | Semantic HTML5 |
| Styling | CSS custom properties as design tokens, Grid/Flexbox, `color-mix()`, `clip-path`, keyframe animations |
| Behavior | Vanilla JavaScript (ES2020), `requestAnimationFrame` loops, hash routing |
| Graphics | Inline SVG with gradients |
| Fonts | Google Fonts (Big Shoulders Display, Bricolage Grotesque, Instrument Sans, JetBrains Mono) |
| Hosting | Vercel (static) |

## Project structure

```
eyad-portfolio/
├── index.html   # markup, styles and scripts for all three modes
├── README.md
└── LICENSE
```

Skill data lives in plain arrays near the bottom of `index.html` (`VIDEO_SKILLS`, `CONTENT_SKILLS`, `DEV_SKILLS`, `STACK`). The timeline, rings and terminal bars are all generated from them, so updating a skill is a one-line change.

## Run locally

No install needed. Open `index.html` in a browser, or serve the folder:

```bash
npx serve .
```

## Deployment

The site is deployed on Vercel as a static project. Every push to `main` triggers a new production deployment.

## License

MIT © Eyad Zein
