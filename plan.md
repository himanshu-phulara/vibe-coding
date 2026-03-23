# Plan: HTML slide deck maintenance

Short reference for how this talk deck is structured and how to change it safely.

## Purpose

- **Single-file deck:** `presentation.html` — self-contained HTML, CSS, and JS (no build step).
- **Use case:** Tech talk / keynote-style slides in the browser.

## DOM structure

| Piece | Role |
|--------|------|
| `.presentation` | Viewport-sized wrapper (`100vw` / `100vh`). |
| `.slide` | One slide; default hidden. |
| `.slide.active` | Exactly one visible slide; uses flex column for layout. |
| `.slide.title-slide` | Title / opening variant (centered, different gradient). |
| `.slide-header` | `h2` (+ optional subtitle `p`) for content slides. |
| `.slide-content` | Body: bullets, grids, cards, images, code blocks. |

New slides are new `.slide` `<div>`s inside `.presentation`, following existing patterns.

## Behavior (do not break)

- **Slides:** `document.querySelectorAll('.slide')` drives everything.
- **`showSlide(n)`** — updates index with wraparound, toggles `.active`.
- **Keyboard:** `ArrowRight` / `Space` → next; `ArrowLeft` → prev; `Home` / `End` → first / last. (No on-screen counter or nav buttons.)

## Assets

- Static images live under **`assets/`** (e.g. `assets/diagram.png`).
- In `<img src="...">` use paths relative to the HTML file: `assets/filename.png`.
- **Local dev:** serve from repo root so paths resolve:  
  `python3 -m http.server 8080` → open `http://localhost:8080/presentation.html`  
  (`file://` can be flaky for fonts or paths.)

## Related repo areas

| Path | Purpose |
|------|---------|
| `docs/` | Speaker notes, preparation guide (not part of runtime deck). |
| `scripts/export_html_to_pptx.py` | Screenshots each `.slide` → `exports/VibeCoding_Presentation.pptx`. |
| `exports/` | Generated PPTX + `exports/README.md`. |

Details for export and onboarding: see **README.md**.

## Editing workflow (summary)

1. Duplicate a nearby slide block that matches the layout you need.
2. Keep one `.active` on load (usually first slide + `title-slide` if applicable).
3. Reuse existing CSS utilities (grids, cards, `.code-block`) before adding new layout systems.
4. After structural changes, spot-check keyboard nav.

Project-specific AI/editor conventions: **`.cursor/rules/presentation.mdc`**.
