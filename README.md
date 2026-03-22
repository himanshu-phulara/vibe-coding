# Vibe Coding Presentation

An interactive presentation on **Vibe Coding** — the AI-assisted development paradigm — created for Adobe GDC.

## What is Vibe Coding?

Vibe Coding is a term coined by Andrej Karpathy describing a new way of programming where developers describe their intent in natural language and AI generates the code. It's about "seeing things, saying things, running things, and copy-pasting things" rather than writing every line by hand.

## Quick Start

1. Open `presentation.html` in your browser (Chrome recommended)
2. Press `F11` or `Cmd+Shift+F` for fullscreen
3. Use `→` / `←` / `Space` to navigate slides

## Export to PowerPoint (preserves visual design)

Screenshots each slide at **1920×1080** in headless Chromium and builds **`VibeCoding_Presentation.pptx`** (16:9).

```bash
pip install playwright python-pptx
playwright install chromium
python3 export_html_to_pptx.py
```

- Keeps screenshots only temporarily (deleted after the PPTX is built). Use `--keep-screenshots` to retain `ppt_export_screenshots/`.
- Slide count matches the number of `.slide` elements in `presentation.html` (currently auto-detected).

**If slides look all black in PowerPoint:** the script uses system **Google Chrome** when available (`channel=chrome`) for reliable gradient/CSS capture. If that fails, run with `--bundled-chromium-only`. Re-run after `playwright install chromium`. Open a saved `ppt_export_screenshots/slide_01.png` — if the PNG looks correct but PPT does not, try re-inserting images in Keynote/PowerPoint.

## Files

| File | Description |
|------|-------------|
| `presentation.html` | Interactive slide deck (open in browser) |
| `export_html_to_pptx.py` | Script: HTML → PPTX via Playwright screenshots |
| `speaker-notes.md` | Detailed speaker notes and Q&A preparation |
| `preparation-guide.md` | Checklists and tips for presenting |

## Presentation Topics

- What is Vibe Coding?
- The Spectrum: Copilot → Cursor → Autonomous Agents
- Best Use Cases (and when to avoid it)
- Live Demo Ideas
- Limitations & Risks
- The Future of Development

## Tools Covered

- [Cursor](https://cursor.com) — AI-first code editor
- [GitHub Copilot](https://github.com/features/copilot) — AI pair programmer
- [Claude](https://claude.ai) / [ChatGPT](https://chat.openai.com) — Foundation models
- [Bolt.new](https://bolt.new) — Full-stack AI builder

## License

Internal presentation for Adobe GDC.
