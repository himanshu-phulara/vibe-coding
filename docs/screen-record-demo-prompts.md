# Screen-record demo: vibe-code the slide deck from scratch (Cursor)

Use this in a **new empty folder** in Cursor while you **screen record**. Each block is one prompt—paste, let the model run, **save**, **open in browser** (or refresh), then continue. You can narrate the **best-practice line** in italics out loud.

**Matches the spirit of this repo’s deck:** single `presentation.html`, **white Adobe-style** slide (left red bar), **keyboard-only** navigation (no progress bar, footer, or on-screen buttons).

---

## Before you hit Record

1. Create a folder, e.g. `deck-demo/`, open it as the **only** Cursor workspace (clean tree).
2. Optional: add `.cursor/rules` with one line: *“Single-file HTML deck only; no frameworks.”* (shows “rules + vibe coding”.)
3. Keep **Chrome** and **Terminal** ready: `python3 -m http.server 8080` from that folder to test.
4. Plan **8–15 minutes** of recording for a **short** deck (below), or cut prompts 5–6 and say *“same pattern for the rest.”*

**Opening line (example):**  
*“I’m going to rebuild a browser slide deck the same way I built our talk—short prompts, tight constraints, and I own the words.”*

---

## Best practices (say one per phase)

| Practice | When |
|----------|------|
| **Constraints first** | Prompt 1 — no React, no build, one file |
| **Behavior before beauty** | Prompt 1 works before Prompt 2 |
| **Small steps** | One prompt = one layer |
| **You own the copy** | Prompt 3+ — paste your titles/bullets |
| **Verify in browser** | After every prompt |
| **Iterate, don’t one-shot** | If something’s wrong, one follow-up: *“Fix X only”* |

---

## Prompt 1 — Shell + keyboard behavior

*Say:* “First I only care that slides advance and the slide count isn’t hardcoded.”

```text
Create presentation.html: one file only, inline CSS and JavaScript, no frameworks and no build step.

Requirements:
- Full viewport: a wrapper fills 100vw x 100vh
- Each slide is a div with class "slide"; exactly one slide has class "active" on load
- Only the active slide is visible
- JavaScript: get all .slide elements, derive count from length — never hardcode slide total in JS
- showSlide(index) with wraparound; toggle .active correctly
- Keyboard: ArrowRight and Space = next, ArrowLeft = previous, Home = first slide, End = last slide; preventDefault for Space
- No on-screen buttons, no slide counter, no progress bar, no footer

Start with TWO slides only: (1) title slide placeholder with h1 + subtitle, (2) a second slide with just h2 "Agenda" and an empty ul. Use minimal gray/white styling so I can confirm behavior—I'll ask for real design next.
```

**Check:** Serve folder → open `http://localhost:8080/presentation.html` → keys work.

---

## Prompt 2 — White “Adobe corporate” look + reusable components

*Say:* “Once behavior works, I lock in typography and layout patterns.”

```text
Redesign the CSS only (keep the same HTML structure and JS unless a small class name tweak helps).

Visual direction:
- White slide background (#fff), black body text, clean sans-serif: use Google Font "Source Sans Pro" for UI text and "Source Code Pro" for any code
- Each .slide: full area, flex column; left edge accent = solid red vertical bar (e.g. border-left ~14px #e60000), comfortable padding
- .slide-header: large bold h2 with a short red underline bar under the title (::after is fine)
- .slide-content: flex growth for main area
- Reusable: .highlight-box (light gray bg, red left border) for quotes; .quote + .quote-author; .two-column with .column and h3 per column; .code-block (light gray box, monospace, simple .code-keyword / .code-string / .code-comment colors)

Optional: set html { font-size: 125%; } for projector readability.

Do not add nav buttons, footer, or progress bar.
```

**Check:** Refresh browser — white theme, red stripe, title + agenda visible.

---

## Prompt 3 — Your real title + agenda (you own the words)

*Say (plain):* “Put my real opening on slide 1 and my real agenda on slide 2.”  
*Say (technical):* “The model arranges markup; I paste the exact strings from my deck.”

### 3A — Plain-language version (read this first on video)

```text
Put my real opening on slide 1 and my real agenda on slide 2. Use this exact wording:

Slide 1 (title):
- Main title: Vibe (highlighted in red) + Coding (black)
- Next line: & The Tech Behind It
- Next line: TechX Live - AI & Agentic AI Tech Talk Series
- Presenters side by side:
  - Himanshu Phulara — Technical Architect
  - Mohit Malik — Technical Architect

Slide 2:
- Title: Agenda
- Bullets in this order, exact text:
  - What is Vibe Coding?
  - The Origin Story & Workflow
  - Tools of the Trade
  - The Tech Stack (LLMs, RAG, Embeddings)  [visually emphasize this line]
  - Under the Hood: How Cursor Works  [visually emphasize this line]
  - Agentic AI & The ReAct Pattern  [visually emphasize, distinct accent color]
  - MCP: Model Context Protocol  [visually emphasize, gold/warning accent]
  - Benefits, Challenges & Best Practices
  - Q&A Discussion
```

### 3B — Technical version (paste after 3A, or merge into one message)

```text
Replace placeholder text on slides 1 and 2 with this exact copy (matches presentation.html):

Slide 1 (title slide, centered):
- h1: "Vibe" wrapped in a span with color #e60000 + "Coding" in black
- p.subtitle: "& The Tech Behind It"
- p.presenter (or equivalent): "TechX Live - AI & Agentic AI Tech Talk Series"
- Two presenter blocks side by side (flex):
  - Himanshu Phulara — Technical Architect  (name strong/bold)
  - Mohit Malik — Technical Architect  (name strong/bold)

Slide 2:
- .slide-header h2: Agenda
- .slide-content ul — bullets with EXACT strings below; use <strong> with inline colors where noted to match the deck:
  - What is Vibe Coding?
  - The Origin Story & Workflow
  - Tools of the Trade
  - <strong style="color: #ff6b6b;">The Tech Stack (LLMs, RAG, Embeddings)</strong>
  - <strong style="color: #ff6b6b;">Under the Hood: How Cursor Works</strong>
  - <strong style="color: #d2a8ff;">Agentic AI & The ReAct Pattern</strong>
  - <strong style="color: #ffc107;">MCP: Model Context Protocol</strong>
  - Benefits, Challenges & Best Practices
  - Q&A Discussion

Keep exactly one .slide with .active on load (title slide). Preserve existing slide classes.
```

**Check:** Typo scan, alignment OK on your screen size.

---

## Prompt 4 — Two content slides (definition + quote)

*Say:* “I add content in batches—same patterns as the full deck.”

```text
After the Agenda slide, add two new slides:

Slide 3 — "What is Vibe Coding?"
- .slide-header with that h2
- .highlight-box with this quote exactly:
  "Vibe Coding is a style of programming where you fully embrace AI assistance — describing what you want in natural language and letting the AI generate code, while you guide, iterate, and refine."
- Below: ul with bullets:
  - Conversational approach to software development
  - Human provides intent, context, and direction
  - AI handles syntax, boilerplate, and implementation details
  - Focus shifts from "how to write" to "what to build"

Slide 4 — "The Origin Story"
- .slide-header with that h2
- .quote with Karpathy quote exactly:
  "There's a new kind of coding I call 'vibe coding', where you fully give in to the vibes, embrace exponentials, and forget that the code even exists."
- .quote-author: "— Andrej Karpathy, February 2025"
- ul below:
  - Coined by former Tesla AI Director & OpenAI founding member
  - Sparked massive industry conversation
  - Represents paradigm shift in developer workflow

Ensure showSlide / keyboard still work with the new slide count.
```

**Check:** Arrow through all slides.

---

## Prompt 5 — Comparison slide (shows layout reuse)

```text
Add slide 5: "Traditional vs Vibe Coding"
- Use .two-column with two .column sections
- Left h3: Traditional Coding — ul: write every line manually; memorize syntax & APIs; search Stack Overflow; copy-paste snippets; debug line by line; hours on boilerplate
- Right h3: Vibe Coding — ul: describe what you need; AI knows syntax; AI has built-in context; generate custom code; AI helps debug & explain; minutes on boilerplate
```

---

## Prompt 6 (optional) — Image slide + assets folder

*Say:* “Real decks use diagrams—I put files in assets/ and describe paths.”

```text
Add slide 6: "The Request Journey"
- Subtitle under h2 (smaller, muted): "What happens when you type in Cursor"
- Centered img: src="assets/diagram.png" alt="Request flow" with max-height ~55vh, rounded corners, light shadow
- I'll place a PNG at assets/diagram.png — use that path

If the img is missing, still show the slide layout without breaking JS.
```

**Check:** Add any placeholder PNG as `assets/diagram.png` or skip image for the recording.

---

## Prompt 7 (optional) — Closing + blank slide

```text
Add second-to-last slide: thank-you style — h2 "Questions & Discussion", short line "Let's explore this together", subtle thank-you note.
Add final slide: completely blank same template (empty .slide with same classes as others) for Q&A overflow or PPT handoff.
```

---

## If something breaks (short follow-ups)

```text
Only the active slide should have .active. Fix showSlide so exactly one slide is visible.
```

```text
Space bar scrolls the page—preventDefault on keydown for Space when using it for next slide.
```

```text
Reduce padding on .slide slightly so dense slides don't clip at 1080p height.
```

---

## After recording — drop clip into PowerPoint

Your exported talk uses **screenshot-to-PPTX** in this repo (`scripts/export_html_to_pptx.py`). For the **demo** recording:

- **Option A:** Insert the **video** on a slide (Insert → Media) in PowerPoint.  
- **Option B:** Keep the demo separate and link from the deck.

---

## Related

- [live-demo-prompts-with-content.md](live-demo-prompts-with-content.md) — deeper talk-specific walkthrough  
- [plan.md](../plan.md) — slide DOM + keyboard invariants for this repo  
