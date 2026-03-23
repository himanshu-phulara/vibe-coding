# Vibe Coding Presentation

An interactive presentation on **Vibe Coding** — the AI-assisted development paradigm — for **TechX Live - AI & Agentic AI Tech Talk Series**.

## Repository layout

```
.
├── presentation.html      # Main slide deck (open in browser)
├── plan.md                # How the deck is structured & maintained
├── .cursor/rules/         # Cursor project rules for this repo
├── assets/                # Images used by the deck
├── docs/
│   ├── README.md          # Index of doc files
│   ├── speaker-notes.md   # Speaker script & Q&A prep
│   ├── preparation-guide.md
│   └── live-demo-prompts-with-content.md  # Live demo: how this deck was built (iterations + prompts)
├── scripts/
│   └── export_html_to_pptx.py   # Build PowerPoint from HTML
└── exports/
    ├── README.md
    └── VibeCoding_Presentation.pptx   # Generated; re-run script to refresh
```

## What is Vibe Coding?

Vibe Coding is a term popularized by Andrej Karpathy: developers describe intent in natural language and AI generates code — “seeing things, saying things, running things, and copy-pasting things” rather than writing every line by hand.

## Quick start

1. Open **`presentation.html`** in your browser (Chrome recommended).
2. From the repo root, you can also serve locally:  
   `python3 -m http.server 8080` → open `http://localhost:8080/presentation.html`
3. Press **F11** or **Cmd+Shift+F** for fullscreen.
4. Use **→** / **←** / **Space** to navigate slides (keyboard only; no slide number or on-screen buttons).

## Maintaining the deck (plan & Cursor rules)

- **[plan.md](plan.md)** — Short maintenance guide: slide DOM pattern, JS invariants (`showSlide`, keyboard nav, slide count from DOM), assets under `assets/`, and how this ties to `docs/`, `scripts/`, and `exports/`.
- **Cursor rules:** [`.cursor/rules/presentation.mdc`](.cursor/rules/presentation.mdc) — Project conventions for AI-assisted edits (single-file deck, don’t break navigation, reuse layouts, keep export docs in sync). Useful for demos of “rules + vibe coding” best practices.

## Export to PowerPoint (preserves visual design)

Screenshots each slide at **1920×1080** and writes **`exports/VibeCoding_Presentation.pptx`** (16:9).

```bash
pip install playwright python-pptx
playwright install chromium
python3 scripts/export_html_to_pptx.py
```

- Temp PNGs go to **`exports/.ppt_screenshots/`** (gitignored) and are deleted after the build unless you pass **`--keep-screenshots`**.
- Slide count follows the number of `.slide` elements in `presentation.html`.

**Export matches the browser:** captures the **full 1920×1080 viewport** (slide content only; no fixed chrome)—not a cropped `.slide` box. The script no longer injects the old dark-theme CSS (that used to override the white Adobe template).

**If slides look wrong or all black:** the script prefers system **Google Chrome** (`channel=chrome`). Try **`--bundled-chromium-only`** if needed. With **`--keep-screenshots`**, inspect `exports/.ppt_screenshots/slide_01.png`.

## Presentation topics (deck)

- What is Vibe Coding? · Origin story · Traditional vs vibe workflow  
- Tools of the trade · Cursor under the hood · Tech stack (LLM, RAG, embeddings)  
- Request journey · Agentic AI · ReAct · MCP  
- Example prompts · Advanced prompt engineering · Benefits & challenges  
- Best practices · Evolving role · Takeaways · Q&A  

## Tools covered

- [Cursor](https://cursor.com) — AI-first editor  
- [GitHub Copilot](https://github.com/features/copilot)  
- [Claude](https://claude.ai) / [ChatGPT](https://chat.openai.com)  
- [Bolt.new](https://bolt.new) — full-stack AI builder  

## License

Internal / org use as appropriate for your event.
