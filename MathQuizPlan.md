# Math Quiz Game (Kids) — Plan & Design

## 1. Goal
- A single-file web game (one `index.html`): **no framework, no MVC, no build step**.
- Runs by opening the file — works fully offline.
- Fun arithmetic practice for kids with a polished, mobile-game look.

## 2. Target & Style
- Children (ages ~5–10). Big image buttons, big numbers, bright cartoon **jungle / platformer** theme.
- Feels like a **mobile game, not a website**: fixed **9:16 portrait**, no scrolling, one screen = one purpose.
- English UI, rounded playful font (**Baloo 2**).

## 3. Screens (show/hide, no routing)
- **Start** — title, choose Operation, choose Level, Start button.
- **Quiz** — question (e.g. `7 + 5 = ?`), 4 answer choices, score + progress gauge, pause/exit.
- **Result** — final score, reward badge, message, Play Again button.

## 4. Operations & Levels
- **Operations:** Add (+), Subtract (−), Multiply (×), Divide (÷), **Mixed** (random of the four), **Expression** (multi-term, e.g. `3 + 2 − 9 × 2 = ?`).
- **Levels:** Easy (0–10), Medium (0–20), Hard (0–50, larger × / ÷).
- 10 questions per round (`TOTAL_QUESTIONS`), 4 options each (`OPTION_COUNT`).

## 5. Game Logic
- Generate random numbers from the chosen level range.
- Subtraction: swap so the result is **never negative**.
- Division: build from divisible pairs so answers stay whole numbers.
- Expression: evaluate **× before + / −**, then left-to-right; answers may be negative.
- Build 4 options = 1 correct + 3 unique distractors near the answer, then shuffle.

## 6. State & Flow
- Single `state` object: `{ score, current, total, operation, difficulty, questions, paused, ... }`.
- `showScreen()` toggles the active screen. Answer → instant feedback badge → auto-advance to next question or result.

## 7. Feel & Feedback
- **Web Audio** sounds: tap, confirm, correct, wrong, end-of-round fanfare (no audio files).
- **Canvas confetti** on a winning score.
- Result background **and** badge change by score tier: win / medium / try-again.

## 8. UI = Image Assets (strict)
- Per `rule-UI-Assets_km.txt`: **every UI part is a raster image** — buttons, frames/windows, progress gauge, badges, backgrounds, mascot.
- **No** CSS-drawn shapes, **no** SVG / icon fonts, **no** emoji.
- Dynamic text (questions, numbers, labels) is overlaid on the image assets with a web font.

## 9. File Structure
```
c:\maths\
  index.html            all HTML + CSS + JS
  PLAN.md               this file
  README.md             project overview + asset list
  rule-design_km.txt    mobile-game UI/UX rules
  rule-UI-Assets_km.txt image-asset rules
  assets/               PNG game art
```

## 10. Tech Notes
- Pure vanilla JS, `Math.random()` for numbers.
- Responsive via `dvh` / `dvw` + container query units; the stage is capped to a 9:16 portrait and fills the screen on mobile.
- Keep all tunable constants (`TOTAL_QUESTIONS`, ranges) at the top of the script.

## 11. Stretch Goals (later)
- Save high score with `localStorage`.
- Choose number of questions; optional per-question timer.
- More animations and a sound on/off toggle.
