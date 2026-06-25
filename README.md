# Math Quiz Game (Kids)

A single-file, offline, **no-framework** math quiz game for children, with a cartoon **jungle / platformer** theme. Every UI element is built from **image assets** (mobile-game style), following the project design rules.

## Play
Open `index.html` in any modern browser (just double-click it). No install, no build step, works offline.

## Features
- **Operations:** Add, Subtract, Multiply, Divide, **Mixed**, and multi-term **Expression** (e.g. `3 + 2 − 9 × 2 = ?`, with × evaluated before + / −).
- **Levels:** Easy / Medium / Hard. 10 questions per round, 4 choices each.
- Instant feedback, live **score + progress gauge**, and a pause / quit popup.
- **Sound effects** (Web Audio API) and **confetti** on a winning score.
- **Result screen** with a tiered background and reward badge (win / medium / try again).
- Responsive **9:16 portrait**; fills the screen on mobile, no scrolling.

## Tech
- HTML5 + Vanilla CSS + JavaScript — all inside `index.html`.
- No dependencies. Google Font **Baloo 2**, Web Audio API, and Canvas (confetti).

## Project structure
```
index.html              all code (HTML + CSS + JS)
assets/                 image assets (PNG)
PLAN.md                 plan & design
README.md               this file
rule-design_km.txt      mobile-game UI/UX rules
rule-UI-Assets_km.txt   image-asset rules
```

## Active assets
All UI is image-based. Text (questions, numbers, labels) is layered on top of these assets with a web font.

| File | Role | Screen | Size (px) |
|------|------|--------|-----------|
| `jungle-background.png` | Full-screen background (Start + Quiz) | Start / Quiz | 941×1672 |
| `bg_jungle_win.png` | Result background — win | Result | 1536×1024 |
| `bg_jungle_mid.png` | Result background — medium | Result | 1536×1024 |
| `bg_jungle_lose.png` | Result background — try again | Result | 1536×1024 |
| `panel.png` | Window / HUD / question frame | all | 1444×676 |
| `btn_wood.png` | Wooden button (operation, level, start, replay, resume, quit) | Start / Quiz / Result | 1382×531 |
| `btn_pause.png` | Pause button | Quiz | 735×753 |
| `answer_platform.png` | Answer "grass mound" platform | Quiz | 1311×664 |
| `num_btn.png` | Wooden number tile (sits on the platform) | Quiz | 851×857 |
| `mascot_turtle.png` | Turtle mascot (decoration) | Quiz | 915×778 |
| `gauge_frame.png` | Progress gauge frame (wood) | Quiz | 1441×279 |
| `gauge_fill.png` | Progress gauge fill (glossy) | Quiz | 1477×154 |
| `badge_correct.png` | Correct feedback / medium reward | Quiz / Result | 938×949 |
| `badge_wrong.png` | Wrong feedback | Quiz | 916×935 |
| `trophy.png` | Win reward | Result | 846×913 |
| `badge_try.png` | "Try again" reward | Result | 987×978 |

> Every file in `assets/` is used by the game; unused placeholder art has been removed.

## Design rules
This project intentionally follows two rule files:
- `rule-design_km.txt` — mobile-game UI/UX (9:16 portrait, one screen one purpose, no scrolling, full-screen game feel).
- `rule-UI-Assets_km.txt` — all UI parts must be image assets (no CSS-drawn shapes, no SVG/icon fonts, no emoji).
