# Vibe Coding deck — full content & images (for sharing)

**Event:** TechX Live — AI & Agentic AI Tech Talk Series  
**Title:** *Vibe Coding & The Tech Behind It*  
**Presenters:** Himanshu Phulara · Mohit Malik (Technical Architects)  
**Source:** `presentation.html` in this repo (25 slides in show order)

Share this file **plus** the image files listed below (from the repo’s `assets/` folder) with Fluffy Jaws or anyone who needs the narrative without opening the HTML/PPTX.

---

## Images to attach (3 files)

| # | File (repo path) | Used on slide(s) | Role |
|---|------------------|------------------|------|
| 1 | `assets/whatisvibecoding.png` | What is Vibe Coding? | Concept / illustration next to definition bullets |
| 2 | `assets/requestFlowArchitecture.png` | The Request Journey | Full-width diagram — what happens when you type in Cursor |
| 3 | `assets/CursorArchitecture.png` | MCP: Model Context Protocol | Architecture diagram (gold-accent border in deck) |

*No other raster images are embedded in the deck; everything else is HTML/CSS text, emoji, and code blocks.*

---

## Slides 1–25 (show order)

### Slide 1 — Title
- **Vibe** Coding  
- *& The Tech Behind It*  
- TechX Live - AI & Agentic AI Tech Talk Series  
- **Himanshu Phulara** — Technical Architect  
- **Mohit Malik** — Technical Architect  

### Slide 2 — Agenda
- What is Vibe Coding?  
- The Origin Story & Workflow  
- Tools of the Trade  
- **The Tech Stack (LLMs, RAG, Embeddings)**  
- **Under the Hood: How Cursor Works**  
- **Agentic AI & The ReAct Pattern**  
- **MCP: Model Context Protocol**  
- Benefits, Challenges & Best Practices  
- Q&A Discussion  

### Slide 3 — What is Vibe Coding?
**Pull quote:**  
> "Vibe Coding is a style of programming where you fully embrace AI assistance — describing what you want in natural language and letting the AI generate code, while you guide, iterate, and refine."

**Bullets:**
- Conversational approach to software development  
- Human provides intent, context, and direction  
- AI handles syntax, boilerplate, and implementation details  
- Focus shifts from "how to write" to "what to build"  

**Image:** `assets/whatisvibecoding.png` (alt: Vibe Coding Concept)

### Slide 4 — The Origin Story
**Quote:**  
> "There's a new kind of coding I call 'vibe coding', where you fully give in to the vibes, embrace exponentials, and forget that the code even exists."  
> — **Andrej Karpathy, February 2025**

**Bullets:**
- Coined by former Tesla AI Director & OpenAI founding member  
- Sparked massive industry conversation  
- Represents paradigm shift in developer workflow  

### Slide 5 — Traditional vs Vibe Coding

| Traditional Coding | Vibe Coding |
|--------------------|-------------|
| Write every line manually | Describe what you need |
| Memorize syntax & APIs | AI knows the syntax |
| Search Stack Overflow | AI has context built-in |
| Copy-paste snippets | Generate custom code |
| Debug line by line | AI helps debug & explain |
| Hours on boilerplate | Minutes on boilerplate |

### Slide 6 — Tools of the Trade
**Subtitle:** AI tools enabling the shift from coding to guiding intelligent agents  

**GitHub Copilot** — AI coding assistant evolving toward agent workflows  
- Use cases: Boilerplate, bug fixes, test generation, PR reviews  
- IDE: VS Code, JetBrains, Visual Studio, CLI, GitHub  
- Note: Real-time suggestions + Copilot Chat + emerging repo-wide agents  

**Cursor** — AI-native IDE built for vibe coding  
- Use cases: Large refactors, multi-file edits, codebase Q&A  
- IDE: Standalone (VS Code-based)  
- Full repo awareness + autonomous agent workflows  

**ChatGPT (OpenAI) + Codex** — AI reasoning + execution agents  
- Use cases: Debugging, architecture design, documentation, complex tasks  
- IDE: Web, API, VS Code plugins, Cursor integration, Codex desktop app  
- Codex: plan → write → test → iterate (agent loop)  

**Google Gemini** — Multimodal AI for cloud and application development  
- Use cases: API integration, mobile apps, cloud workflows  
- IDE: Android Studio (strong), VS Code (extensions), limited JetBrains  
- Deep integration with Google Cloud & ecosystem  

**Footer line:** *Vibe Coding = Developer intent + AI agent execution across the codebase*

### Slide 7 — Under the Hood: How Cursor Works
**Subtitle:** The architecture behind AI-assisted coding  

**Flow (left → right):** Your Code + Prompt → Context Engine (RAG + Embeddings) → LLM API (GPT-4 / Claude) → Generated Code + Diff View  

**1. Context Gathering** — Current file + cursor; open tabs & recent files; codebase index (embeddings); Git history & diff context  

**2. Prompt Construction** — System prompt (rules, format); retrieved code snippets; user’s natural language query; token optimization (~128K limit)  

**3. Response Handling** — Stream tokens in real-time; parse code blocks & diffs; apply changes to editor; run linting & validation  

### Slide 8 — The Tech Stack Behind Vibe Coding
**Large Language Models** — GPT-4, Claude, Gemini; next-token prediction; example snippet: `function add(a, b) { return` → `a + b; }`  

**Embeddings & Vector Search** — Semantic vectors; example: "parseJSON" vs "decodeJSON" similar vectors  

**RAG** — Retrieves from YOUR codebase; example query "Add error handling" → finds e.g. `ErrorBoundary.tsx`  

**Streaming & Token Windows** — GPT-4 ~128K tokens; Claude ~200K tokens (approx. word equivalents on slide)  

### Slide 9 — The Vibe Coding Workflow
1. **Describe** — Explain what you want in plain English  
2. **Generate** — AI produces code based on context  
3. **Review** — Evaluate, understand, verify  
4. **Iterate** — Refine with follow-up prompts  

**Key insight:** *You're still the architect. AI is your highly capable assistant who can write code fast but needs your judgment and domain expertise.*

### Slide 10 — The Request Journey
**Subtitle:** What happens when you type in Cursor  

**Image:** `assets/requestFlowArchitecture.png` (Request Flow Architecture)

### Slide 11 — Agentic AI: The Next Level
**Subtitle:** From autocomplete to autonomous coding  

**What is Agentic AI?**  
- Autonomously plan, execute, and iterate on multi-step tasks — not just single prompts  
- Goal-oriented; multi-step; tool use; self-correcting  

**Cursor Agent Mode (numbered):**  
1. Reads codebase & understands structure  
2. Creates a plan for multi-file changes  
3. Edits files, creates new ones as needed  
4. Runs terminal commands (npm, git, tests)  
5. Sees errors → iterates until it works  

**Example:** *"Add authentication to my Express app"* → reads routes, middleware, auth files, packages, tests  

### Slide 12 — How Agents Work: The ReAct Pattern
**Subtitle:** Reasoning + Acting in a loop  

**Loop:** Goal → Think → Act → Observe → (repeat)  
Example goal label: "Add user auth"  

**Tools:** Read File · Edit File · Run Command · Search Code  

**Key insight:** Agents understand context, make decisions, and iterate like a junior developer would.  

### Slide 13 — MCP: Model Context Protocol
**Subtitle:** How Cursor connects to external tools & services  

**Image:** `assets/CursorArchitecture.png` (MCP architecture)  

**Steps:** 1. User Prompt ("Add pagination to API") → 2. MCP Request (stdio/HTTP) → 3. Server Response (structured data) → 4. Final Output (multi-file patch/edit)  

**Takeaway:** MCP enables GitHub, databases, APIs — bridge between AI and infrastructure.  

### Slide 14 — Example: From Prompt to Code
**Theme:** Good Prompt → Better Prompt  

**Good prompt (summary):** TypeScript password strength checker, weak/medium/strong, length ≥8, character classes, unit tests.  

**Generated (good):** Score-based `checkPasswordStrength` example — **caveat on slide:** works but lacks validation and clear strength rules.  

**Better prompt (summary):** Named `passwordStrength`, explicit weak/medium/strong rules, `TypeError` for non-string, Jest tests + `package.json` script, edge cases called out.  

**Generated (better):** Stricter `passwordStrength` implementation + note that Jest + package.json included.  

**Footer:** *Better prompts = Better code.* Be specific about types, validation, edge cases, and tests.  

### Slide 15 — Advanced Prompt Engineering
**Subtitle:** Level up your AI collaboration  

- **Codebase context** — e.g. `@src/utils/api.ts` + refactor instructions  
- **Chain-of-thought** — Stepwise: analyze → bottleneck → solution  
- **Cursor Rules / .cursorrules** — e.g. TypeScript strict, functional components, error boundary pattern  
- **Multi-turn refinement** — Turn 1 base hook → Turn 2 errors → Turn 3 re-render optimization  

### Slide 16 — Benefits of Vibe Coding
**Six cards (each with 3 bullets on slide):**  
⚡ Speed · 🧠 Reduced Cognitive Load · 🔁 Rapid Iteration · 🤖 Automation · 📈 Productivity Boost · 📚 Faster Learning Curve  

**Footer:** From **writing code** → to **steering outcomes**  

### Slide 17 — Challenges & Considerations
**Watch out for:** Hallucinations; security in generated code; over-reliance; context limits; IP; inconsistent style  

**Mitigations:** Review & understand; security scans & tests; sharp fundamentals; focused context; enterprise tools; team conventions  

### Slide 18 — Where Vibe Coding Falls Short
**Subtitle:** Know the limits to use it effectively  

- Complex state machines  
- Performance-critical code (complexity, caching, memory)  
- Deep proprietary domain context  
- Multi-file architecture / large refactors  

**Takeaway:** Use AI for acceleration, not abdication — harder problems need more human judgment.  

### Slide 19 — Best Practices for Engineers
- Be Specific (concrete example: React hook for debounced search vs "make search work")  
- Provide Context  
- Iterate Incrementally  
- Verify Everything  
- Learn From Output  
- Know When NOT to Use (security-critical, proprietary algorithms)  
- Document Your Prompts  

**Golden Rule:** *AI is a power tool, not autopilot. You're responsible for what ships.*  

### Slide 20 — The Evolving Developer Role
**Current opportunities:** Faster features; documentation; reviews; PM demos; tests; legacy understanding  

**Future implications:** Coder → architect; higher-level problems; more innovation time; interviews; collaboration; AI-augmented reviews  

### Slide 21 — The Human Element Remains Critical
**Quote:** *"AI won't replace developers. Developers who use AI will replace developers who don't."*  

- System Design · Domain Knowledge (Adobe products & customers) · Code Review · Creativity · Communication · Accountability  

### Slide 22 — Getting Started Tomorrow
1. Pick a Tool (Cursor, Copilot, Claude)  
2. Start Small (tests, docs, utilities)  
3. Build Intuition  
4. Share Learnings  

**Challenge:** Try vibe coding on the next task; compare time vs traditional approach.  

### Slide 23 — Key Takeaways
- Vibe coding is a paradigm shift, not just a tool  
- AI amplifies you — you still drive  
- Review, understand, verify everything  
- Start small, build intuition, share with team  
- Future belongs to AI-augmented engineers  

### Slide 24 — Questions & Discussion
- Let's explore this together  
- Thank you for your time!  

### Slide 25 — Blank
- Intentionally empty slide (same template: white + left red stripe) for notes or hand-off in PPT  

---

## Handing off to Fluffy Jaws

1. **This markdown** — narrative + structure  
2. **Zip or folder:** `assets/whatisvibecoding.png`, `assets/requestFlowArchitecture.png`, `assets/CursorArchitecture.png`  
3. **Optional:** `exports/VibeCoding_Presentation.pptx` — pixel match to the live deck (screenshot export)  
4. **Optional:** Open `presentation.html` in a browser (serve from repo root) for the interactive version; use **arrow keys / Space** to advance  

---

*Generated from `presentation.html` in the vibe-coding-presentation repo.*
