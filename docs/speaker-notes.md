# Vibe Coding - Speaker Notes & Script
## 30-Minute Presentation for Adobe GDC Team

---

## TIMING OVERVIEW

| Slide | Topic | Duration | Cumulative |
|-------|-------|----------|------------|
| 1 | Title | 0:30 | 0:30 |
| 2 | Agenda | 1:00 | 1:30 |
| 3 | What is Vibe Coding | 2:30 | 4:00 |
| 4 | Origin Story | 2:00 | 6:00 |
| 5 | Traditional vs Vibe | 2:30 | 8:30 |
| 6 | The Workflow | 3:00 | 11:30 |
| 7 | Tools | 2:30 | 14:00 |
| 8 | Example Prompt | 2:30 | 16:30 |
| 9 | Benefits | 2:30 | 19:00 |
| 10 | Challenges | 3:00 | 22:00 |
| 11 | Best Practices | 2:30 | 24:30 |
| 12 | Impact at Adobe | 2:00 | 26:30 |
| 13 | Human Element | 1:30 | 28:00 |
| 14 | Getting Started | 1:30 | 29:30 |
| 15 | Key Takeaways | 0:30 | 30:00 |
| 16 | Q&A | 5-10 min | Buffer |

---

## SLIDE-BY-SLIDE SCRIPT

---

### SLIDE 1: Title (0:30)

**[PAUSE FOR AUDIENCE TO SETTLE]**

> "Good [morning/afternoon] everyone! Thank you for joining today. I'm excited to talk about something that's been transforming how developers work around the world — and increasingly here at Adobe. It's called **Vibe Coding**."

---

### SLIDE 2: Agenda (1:00)

> "Here's what we'll cover in the next 30 minutes:"

**[Read through the agenda points briefly]**

> "We'll start with understanding what vibe coding actually is, look at the tools available, discuss both the benefits AND the challenges — because it's not all sunshine and rainbows — and then talk specifically about how this impacts us as Adobe engineers. I'll leave time for Q&A at the end, but feel free to raise your hand if something urgent comes up."

---

### SLIDE 3: What is Vibe Coding? (2:30)

> "So what IS vibe coding?"

**[Read the highlighted quote]**

> "In simple terms, it's coding by conversation. Instead of writing every line of code yourself, you describe what you want in natural language — plain English — and let an AI assistant generate the code for you."

> "But here's what's important to understand:"

**[Go through each bullet]**

> "You're still in control. You're the one providing the intent — WHAT needs to be built. You bring the context — the understanding of the codebase, the business requirements, the constraints."

> "The AI handles the tedious parts — the syntax, the boilerplate, the 'how do I do X in React again?' moments."

> "Think of it like this: you've gone from being a solo developer typing every character to being a tech lead with an incredibly fast junior developer who knows every API but needs your guidance on what to build and why."

---

### SLIDE 4: Origin Story (2:00)

> "The term 'Vibe Coding' was actually coined by Andrej Karpathy — and if that name doesn't ring a bell, he's kind of a legend in AI. Former AI Director at Tesla, founding member of OpenAI, deep learning pioneer."

**[Read the quote]**

> "He posted this on X in February 2025, and it absolutely blew up. Developers everywhere started sharing their experiences, tools started marketing around this concept, and suddenly we had a name for something many of us were already experimenting with."

> "Why did it resonate? Because it captured this feeling that many developers had — that the relationship with code was fundamentally changing."

---

### SLIDE 5: Traditional vs Vibe Coding (2:30)

> "Let me paint a picture of the contrast."

**[Left column - Traditional]**

> "In traditional coding, you write every line. You memorize syntax or constantly look it up. You spend time on Stack Overflow, copy-paste snippets, debug line by line. A lot of time goes into boilerplate — code that's necessary but not really adding unique value."

**[Right column - Vibe]**

> "With vibe coding, you describe what you need. The AI already knows the syntax. Need to fetch data with proper error handling in React? Just ask. Need to write a regex that validates email addresses? Just describe it."

> "But I want to be clear — this isn't about being lazy. It's about working at a higher level of abstraction. You're still thinking, planning, designing. You're just spending less time on the mechanical parts."

---

### SLIDE 6: The Workflow (3:00)

> "Let's break down how this actually works in practice."

**[Walk through each step]**

> "**Step 1: Describe.** You explain what you want in plain English. The more specific and contextual, the better."

> "**Step 2: Generate.** The AI produces code based on your description and any context it has about your codebase."

> "**Step 3: Review.** This is CRITICAL. You don't just blindly accept. You read it, understand it, verify it makes sense."

> "**Step 4: Iterate.** First try not quite right? Refine with follow-up prompts. 'Make it handle null values.' 'Add error logging.' 'Use our existing utility function instead.'"

**[Read the highlight box]**

> "This is the key insight I want you to remember: You are still the architect. The AI is your highly capable assistant. It can write code incredibly fast, but it needs YOUR judgment, YOUR domain knowledge, YOUR understanding of Adobe's products and customers."

---

### SLIDE 7: Tools of the Trade (2:30)

> "Let's quickly tour the tools available today."

**[Point to each tool card]**

> "**Cursor** — probably the most popular right now. It's a VS Code fork built from the ground up for AI. Has inline suggestions, chat, and a 'composer' that can make multi-file changes."

> "**GitHub Copilot** — the OG. Tight VS Code integration, inline suggestions, now has chat too."

> "**Claude and ChatGPT** — the foundation models. You can use them in browser or through APIs. Great for complex reasoning tasks."

> "**Windsurf** — newer player with 'agentic' capabilities, meaning it can perform sequences of actions autonomously."

> "And there are many others — Replit Agent, v0 for UI components, Bolt.new for full-stack apps."

> "The landscape is evolving rapidly. What matters is finding what works for your workflow."

---

### SLIDE 8: Example Prompt (2:30)

> "Let me show you what a typical vibe coding interaction looks like."

**[Read the prompt]**

> "Create a React component that displays a list of users fetched from an API. Include loading and error states, use TypeScript, and add a search filter. Make it accessible with proper ARIA labels."

> "That's it. One prompt. From this, a good AI will generate a complete component — maybe 80-100 lines of production-quality code."

**[Go through what you get]**

> "TypeScript interfaces, properly typed. React hooks configured correctly. Loading spinner, error handling, search with debouncing, accessibility labels."

> "What would have taken 20-30 minutes to write from scratch? Generated in seconds. Your job then is to review it, tweak it to fit your specific needs, and integrate it."

---

### SLIDE 9: Benefits (2:30)

> "The benefits are compelling."

**[Point to stats]**

> "GitHub's research showed a 55% productivity increase with Copilot. For prototyping, I've personally seen 10x speedups on getting an initial version working."

> "But beyond the numbers..."

**[Go through bullets]**

> "Learning new frameworks becomes faster — the AI can show you idiomatic patterns."

> "Boilerplate that used to take hours? Minutes."

> "You can experiment more freely — try an approach, if it doesn't work, try another."

> "And it democratizes coding — product managers can sketch out prototypes, designers can implement their ideas."

---

### SLIDE 10: Challenges (3:00)

> "Now let's talk honestly about the challenges. This is important."

**[Left column - Watch Out For]**

> "**Hallucinations.** The AI can be confidently wrong. It might call an API that doesn't exist or use deprecated syntax."

> "**Security vulnerabilities.** Generated code might have issues that aren't obvious at first glance."

> "**Over-reliance.** If you always let AI write the code, your own skills can atrophy."

> "**Context limits.** These models can only see so much. Large codebases can be challenging."

> "**IP concerns.** Be mindful of what code you're sharing with external services."

**[Right column - Mitigations]**

> "The mitigations are straightforward but require discipline:"

> "Always review. Always. If you don't understand something the AI wrote, don't use it until you do."

> "Run security scans, write tests. The usual hygiene applies even more."

> "Keep your fundamentals sharp. You need to be able to catch when the AI is wrong."

> "Use enterprise-approved tools that have proper data handling."

---

### SLIDE 11: Best Practices (2:30)

> "Here are best practices I'd recommend for our teams."

**[Go through each point]**

> "**Be specific.** 'Create a React hook for debounced search' is much better than 'make search work.'"

> "**Provide context.** Share the relevant code, types, and constraints."

> "**Iterate incrementally.** Don't try to build everything in one prompt. Break it down."

> "**Verify everything.** Test the generated code, check edge cases."

> "**Learn from output.** When AI does something clever, understand why. When it does something wrong, understand that too."

> "**Know when NOT to use it.** Security-critical code, proprietary algorithms — maybe write those yourself or review extra carefully."

**[Read highlight box]**

> "Golden rule: AI is a power tool, not autopilot. You're responsible for what ships."

---

### SLIDE 12: Impact at Adobe (2:00)

> "How does this apply to us specifically?"

**[Left column - Current]**

> "Right now, there are immediate wins: faster feature development, better documentation — AI is great at writing docs. More efficient code reviews when you have AI explain unfamiliar code. Quick prototypes for PM demos."

**[Right column - Future]**

> "Looking ahead, our role shifts. Less time typing syntax, more time on architecture and design. Higher-level problem solving. More time for actual innovation."

> "This will also affect hiring and interviews. The skills that matter are evolving."

---

### SLIDE 13: Human Element (1:30)

**[Read the quote]**

> "'AI won't replace developers. Developers who use AI will replace developers who don't.'"

> "This is important to internalize. The human element remains absolutely critical."

> "System design, architecture decisions — AI can suggest, but YOU decide."

> "Domain knowledge — understanding Adobe's products, our customers' needs — AI doesn't have that."

> "Code review — catching subtle bugs, security issues."

> "Creativity — novel solutions to unique problems."

> "And ultimately, accountability. YOU own the code that ships."

---

### SLIDE 14: Getting Started (1:30)

> "So how do you get started?"

**[Walk through steps]**

> "**One:** Pick a tool. Cursor if you want the full AI-native experience, Copilot if you're comfortable with VS Code, or just start with Claude or ChatGPT in a browser."

> "**Two:** Start small. Unit tests are great — describe the function, ask for tests. Documentation. Simple utilities."

> "**Three:** Build intuition. Learn what types of prompts work, what doesn't, when to use it, when not to."

> "**Four:** Share with the team. Good prompts are reusable. Share what you learn."

**[Read highlight box - the challenge]**

> "Here's my challenge to you: On your next task, try vibe coding it. Generate some tests, write some docs, scaffold a component. Compare the time spent. Form your own opinion."

---

### SLIDE 15: Key Takeaways (0:30)

**[Go through each quickly]**

> "Vibe coding is a paradigm shift — not just a tool."

> "AI amplifies your capabilities — you still drive."

> "Review, understand, verify everything."

> "Start small, build intuition, share with the team."

> "The future belongs to AI-augmented engineers."

---

### SLIDE 16: Q&A

> "Thank you! I'd love to hear your thoughts, questions, concerns. What's on your mind?"

**[See Q&A Preparation section below for common questions]**

---

## PRESENTATION TIPS

### Before the Presentation
- [ ] Test the HTML presentation in your browser (Chrome recommended)
- [ ] Practice navigation: Arrow keys, Space to advance
- [ ] Connect to projector/screen share and test
- [ ] Have backup (PDF export) ready
- [ ] Close unnecessary browser tabs
- [ ] Put phone on silent

### During the Presentation
- **Pace yourself** — check the time at slides 6, 10, and 14
- **Make eye contact** — look at the audience, not the screen
- **Pause after important points** — let them sink in
- **Check for understanding** — "Does this make sense?" at key moments
- **Be authentic** — share your own experiences with vibe coding

### Engagement Techniques
- Ask for a show of hands: "How many have tried Copilot or Cursor?"
- Acknowledge skeptics: "I know some of you might be skeptical..."
- Use real examples from your own work if possible

---

## Q&A PREPARATION

### Likely Questions & Answers

**Q: "Isn't this just fancy autocomplete?"**
> A: "It started there, but it's evolved significantly. Modern tools understand context across your entire codebase, can make multi-file changes, and can reason about architecture. It's less 'autocomplete' and more 'having a senior developer pair programming with you.'"

**Q: "What about code quality? AI-generated code seems generic."**
> A: "Valid concern. The quality depends heavily on how you prompt and how you review. You can specify style guidelines, point to existing patterns in your codebase. And ultimately, you're reviewing everything — so you catch quality issues before they ship."

**Q: "Does this mean we'll need fewer developers?"**
> A: "I think it means we'll need developers who work differently. Instead of writing every line, you're architecting, reviewing, and directing. If anything, being able to build faster means we can build MORE — more features, more experiments, more innovation."

**Q: "What about proprietary code? Are we sending it to external servers?"**
> A: "Great security question. Yes, some tools send code externally. That's why we need to use approved tools and be mindful of what we share. Some organizations run local models. Check with our security team on approved tools."

**Q: "I tried Copilot and it gave me wrong code."**
> A: "That happens! And that's exactly why the review step is critical. Think of it like delegating to a junior developer — they're fast and usually helpful, but you always check their work. The skill is learning when to trust and when to verify closely."

**Q: "How do I get better at prompting?"**
> A: "Practice, mainly. Be specific, provide context, iterate. Think of it like becoming a good manager — you learn how to give clear instructions. There are also great resources online about prompt engineering."

**Q: "What's Adobe's official stance on using these tools?"**
> A: "Check with your manager and legal/security teams for official guidance. The technology is evolving quickly and policies may be updating. What I can say is the industry is moving this direction rapidly."

**Q: "Will this make coding skills irrelevant?"**
> A: "Absolutely not. You need to understand code to review it, debug it, and know when the AI is wrong. If anything, you need broader knowledge — not just one language deeply, but understanding patterns across technologies. The fundamentals matter MORE because you need to evaluate what the AI produces."

---

## BACKUP MATERIALS

### If Asked for a Live Demo
If the audience asks for a live demo and you're comfortable:
1. Open Cursor or your preferred tool
2. Show a simple example: "Write a function that validates an email address"
3. Show iteration: "Now make it also validate that it's not a disposable email domain"
4. Emphasize the review process

### If Time Runs Short
Priority slides if you need to speed up:
- Slides 3, 4 (What & Origin): Combine, 2 min total
- Slide 7 (Tools): Just mention 2-3, 1 min
- Skip slide 8 (Example) if needed
- Slides 11-13: Combine into 3 min

### If Time Runs Long (Ahead of Schedule)
- Add personal anecdotes
- Ask audience questions
- Go deeper on tools slide
- Spend more time on Q&A

---

## ADDITIONAL TALKING POINTS

### For Skeptics
- "I was skeptical too. Try it for a week on low-stakes tasks."
- "It's not about replacing your skills — it's augmenting them."
- "The best developers I know are embracing this AND staying sharp."

### For Enthusiasts
- "Remember the review step. Don't let excitement bypass quality."
- "Share your learnings with the team."

### Adobe-Specific Angles
- "Think about how this could help with our large codebases"
- "Documentation is always behind — AI can help"
- "Onboarding new team members could be faster"
- "We can prototype and validate ideas more quickly"

---

*Good luck with your presentation! You've got this.* 🎯

