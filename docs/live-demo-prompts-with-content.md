# Live demo script: how *this* deck was built with vibe coding

Use this when you tell the story: **you already created `presentation.html` (this talk) using vibe coding.** The live session **re-enacts that process** in iterations. The file you generate live does **not** need to match the repo pixel-for-pixel—the goal is to show **what you contributed in prompts**, that **the application (HTML/CSS/JS/layout) came from the AI**, and that **iteration + constraints** are the best practices. The audience should see an end result **in the same family**: dark keynote, single file, keyboard deck, similar slide *types*.

---

## One sentence for the room

> “Everything you’re about to see me **type** is the **content and structure** I cared about; the **markup, styles, and behavior** were vibe-coded in **passes**—same way I built the deck you’re looking at now.”

---

## What was yours vs what was vibe-coded

| You (human) | Vibe coding (AI) |
|-------------|------------------|
| Talk goal, audience, length | File shape, `<div class="slide">` pattern |
| Slide order, titles, bullets, quotes | CSS for layout grids, cards, typography |
| Exact wording (definitions, Karpathy quote, tool facts) | Keyboard navigation, slide show/hide |
| Which diagrams to show + filenames under `assets/` | `<img>` placement, sizing, alt text patterns |
| “Make it look like a dark Adobe-style keynote” | Concrete colors, fonts, spacing, components |

**Best practice to say out loud:** *I didn’t one-shot 24 slides. I constrained the stack, got behavior working, then layered design, then fed **my** copy in batches.*

---

## Best practices to highlight during the demo

1. **Constraints first** — Single file, no React/build, inline CSS+JS, must work with arrow keys / Space. Stops the model from over-engineering.
2. **Behavior before pixels** — Slides show/hide, index uses `slides.length`, wraparound. *Then* make it pretty.
3. **Iterate, don’t monologue** — Short prompts per step; easier to correct and easier for the audience to follow.
4. **You own the words** — Paste bullets, quotes, agenda. Don’t ask the model to invent your talk’s substance.
5. **Reuse patterns** — Ask for `.two-column`, `.highlight-box`, `.workflow-steps` once; duplicate slide *shapes* later.
6. **Review like code** — Open in browser, click through, fix one thing per follow-up prompt.
7. **Assets** — Images live in `assets/`; serve with `python3 -m http.server` from repo root so paths work ([plan.md](../plan.md)).

---

## Iteration 1 — “I need a slide deck app”

**What you say:** *First I only asked for the shell—so I knew navigation and state were right.*

**Example prompt (paste or paraphrase live):**

```text
Create a single HTML file (presentation.html) with inline CSS and JavaScript—no frameworks, no build step.

I want a fullscreen slide deck:
- Wrapper fills the viewport; each slide is a div with class "slide"
- Only one slide visible at a time (use an "active" class)
- Keyboard: arrow keys and Space to change slides (optional: omit on-screen buttons for a cleaner deck)
- JavaScript must discover the number of slides from the DOM—never hardcode the total
- Keyboard: right arrow and space = next, left = previous, home/end = first/last

Start with just two slides: a title slide placeholder and an empty second slide. Keep styling minimal until I ask for design.
```

**Point:** *This is how I started—app first, keynote skin later.*

---

## Iteration 2 — “Make it feel like the real talk”

**What you say:** *Once it worked, I described the visual system so every later slide stayed consistent.*

**Example prompt:**

```text
Upgrade the CSS to a dark keynote style: deep blue/purple gradients, white text, strong headline hierarchy.
Use Google Fonts: something clean for body (e.g. Source Sans Pro) and monospace for code blocks.

Add reusable layout classes I'll reuse across slides:
- .slide-header for h2 (optional subtitle)
- .slide-content for main body
- .highlight-box for pull quotes
- .quote and .quote-author
- .two-column with .column and h3 per side
- .code-block with simple classes for keywords/strings/comments (no external highlighter)
- .workflow-steps for a horizontal row of steps with numbers
- .pros-cons with .pros and .cons for risks vs mitigations
- Title slide variant: centered, logo text top-left, big h1 with one word in an accent class (e.g. .vibe)

Keep one file. Don't change the JS behavior except if you need a class name for the active slide.
```

**Point:** *I invested one prompt in design tokens so I wasn’t renegotiating fonts on slide 19.*

---

## Iteration 3 — “Here is *my* opening and agenda”

**What you say:** *This is where the talk became mine—the model arranged it; I supplied every line.*

**Example prompt:**

```text
Fill in the first two slides with this exact copy (keep your CSS classes):

Slide 1 — title slide:
- Top left: Adobe
- Main title: "Vibe" as accent + "Coding"
- Subtitle: "& The Tech Behind It"
- Line: TechX Live - AI & Agentic AI Tech Talk Series
- Presenters: Himanshu Phulara — Technical Architect | Mohit Malik — Technical Architect

Slide 2 — Agenda, h2 "Agenda", bullets:
- What is Vibe Coding?
- The Origin Story & Workflow
- Tools of the Trade
- The Tech Stack (LLMs, RAG, Embeddings) — emphasize visually
- Under the Hood: How Cursor Works — emphasize
- Agentic AI & The ReAct Pattern — emphasize, distinct color if you have a utility
- MCP: Model Context Protocol — emphasize, distinct accent
- Benefits, Challenges & Best Practices
- Q&A Discussion
```

**Point:** *Vibe coding didn’t write my agenda—I pasted it. It wired layout and emphasis.*

---

## Iteration 4 — “Add the next chunk of *my* narrative”

**What you say:** *I kept going in batches: definition, origin, comparison—same pattern as when I built the real deck.*

**Example prompt:**

```text
Add three new slides after the agenda:

1) "What is Vibe Coding?"
   - h2 as usual
   - highlight-box with this quote exactly: "Vibe Coding is a style of programming where you fully embrace AI assistance — describing what you want in natural language and letting the AI generate code, while you guide, iterate, and refine."
   - Two columns: left = bullets: conversational approach; human intent/context/direction; AI syntax/boilerplate; focus shifts from how to write to what to build
   - Right = image assets/whatisvibecoding.png alt "Vibe Coding concept", max-height ~280px, rounded corners

2) "The Origin Story"
   - Blockquote: "There's a new kind of coding I call 'vibe coding', where you fully give in to the vibes, embrace exponentials, and forget that the code even exists."
   - Attribution: — Andrej Karpathy, February 2025
   - Bullets: coined by…; sparked industry conversation; paradigm shift in developer workflow

3) "Traditional vs Vibe Coding"
   - two-column: Traditional = write manually; memorize APIs; Stack Overflow; copy-paste; debug line by line; hours on boilerplate
   - Vibe Coding = describe need; AI knows syntax; built-in context; custom code; AI helps debug; minutes on boilerplate
```

**Point:** *I gave structure + exact strings; the model produced grids, spacing, and image markup.*

---

## Iteration 5 — “Dense slides: tools, architecture, diagram”

**What you say:** *For complex slides I described the **shape** (2×2 cards, flow diagram, full-bleed image) and dropped **my** facts—the AI handled the HTML tedium.*

**Short example prompt (tools grid — abbreviate live if needed):**

```text
Add a slide "Tools of the Trade" with subtitle about AI tools and shifting from coding to guiding agents.

2×2 card grid. Each card: tool name, tagline, use cases, IDE surfaces, one differentiator. Order:
1) GitHub Copilot — …
2) Cursor — …
3) ChatGPT + Codex — …
4) Google Gemini — …

Footer one-liner: Vibe Coding = Developer intent + AI agent execution across the codebase.

Use my facts from the existing presentation or summarize from: [paste your bullet notes if you prefer].

Then add a slide "Under the Hood: How Cursor Works" with a horizontal flow: Your Code + Prompt → Context Engine (RAG + Embeddings) → LLM API → Generated Code + Diff View, plus three columns for context gathering, prompt construction, response handling.

Then add "The Request Journey" with subtitle "What happens when you type in Cursor" and centered image assets/requestFlowArchitecture.png max-height ~600px.
```

**Point:** *Complex layout is exactly where vibe coding saves time—if you give clear structure.*

---

## Iteration 6 — “Agents, MCP, prompt-engineering proof”

**What you say:** *I used the same pattern: section titles + bullets + optional image paths. The password prompt/code slide is intentional—it teaches prompt quality while demoing vibe coding.*

You can prompt for slides on: Agentic AI, ReAct, MCP + `assets/CursorArchitecture.png`, “Example: From Prompt to Code” (good vs better prompt + generated TS snippets), Advanced Prompt Engineering grid, Benefits grid, Challenges pros/cons, limits, best practices, evolving role, human element, getting started, takeaways, thank you/Q&A—**feeding your real bullets each time**, or one batched prompt for several slides if time is short.

---

## Iteration 7 — “Polish pass”

**Example prompt:**

```text
Review the whole file: exactly one .slide.active on load; navigation still works if slides are added; improve contrast for projectors. List what you changed.
```

---

## If the audience asks: “Why doesn’t the live file match presentation.html?”

**Answer:** *“Same workflow and similar constraints—the model isn’t deterministic, and I might abbreviate a prompt live. The deck you have is the full iteration history in the repo. Tonight is about **how** I used prompts, not a checksum.”*

---

## Optional: using the repo as context (not for cloning live)

When **editing** the real deck in Cursor, attaching **`@presentation.html`**, **`@plan.md`**, or **`.cursor/rules/presentation.mdc`** is how you keep follow-up changes consistent—that’s vibe coding with **project context**. You can mention that separately from the live-from-scratch demo.

---

## Assets (same as the real deck)

| File | Role |
|------|------|
| `assets/whatisvibecoding.png` | Concept slide |
| `assets/requestFlowArchitecture.png` | Request journey |
| `assets/CursorArchitecture.png` | MCP / Cursor architecture |

Serve from repo root: `python3 -m http.server 8080` → open your HTML path.

---

## Related

- **[presentation.html](../presentation.html)** — The finished artifact from your actual vibe-coding iterations.  
- **[plan.md](../plan.md)** — DOM and JS invariants (slide count, keyboard).  
- **[.cursor/rules/presentation.mdc](../.cursor/rules/presentation.mdc)** — Conventions for AI-assisted edits to this repo.  
