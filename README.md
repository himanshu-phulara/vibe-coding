# Vibe Coding Presentation

An interactive presentation on **Vibe Coding** — the AI-assisted development paradigm — for **TechX Live - AI & Agentic AI Tech Talk Series**.

## Repository layout

```
.
├── presentation.html      # Main slide deck (open in browser)
├── assets/                # Images used by the deck
├── docs/
│   ├── README.md          # Index of doc files
│   ├── speaker-notes.md   # Speaker script & Q&A prep
│   └── preparation-guide.md
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
4. Use **→** / **←** / **Space** to navigate slides.

## Export to PowerPoint (preserves visual design)

Screenshots each slide at **1920×1080** and writes **`exports/VibeCoding_Presentation.pptx`** (16:9).

```bash
pip install playwright python-pptx
playwright install chromium
python3 scripts/export_html_to_pptx.py
```

- Temp PNGs go to **`exports/.ppt_screenshots/`** (gitignored) and are deleted after the build unless you pass **`--keep-screenshots`**.
- Slide count follows the number of `.slide` elements in `presentation.html`.

**If slides look all black in PowerPoint:** the script prefers system **Google Chrome** (`channel=chrome`). Try **`--bundled-chromium-only`** if needed. With **`--keep-screenshots`**, inspect `exports/.ppt_screenshots/slide_01.png`.

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
