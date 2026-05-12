# Research Synthesis: Designing a Context Engineering Webinar

**Date:** May 2026
**Context:** Foundation research before designing a 60–90 min webinar on context engineering for a mixed-experience audience (general curious + intermediate LLM users).

This document synthesizes findings from four parallel research streams. Full detail in:
- [01 — Definitions and framings](01-definitions-and-framings.md)
- [02 — Resources bibliography](02-resources-bibliography.md)
- [03 — Similar workshops](03-similar-workshops.md)
- [04 — Context vs prompt engineering](04-context-vs-prompt-engineering.md)

---

## TL;DR

1. **"Context engineering" is a real, ~11-month-old term-of-art** with a clear origin story (Lütke → Chase → Karpathy → Anthropic, June–Sept 2025) and broad consensus on its meaning: *the practice of curating everything the model sees at inference time, not just the prompt string.*

2. **The teaching landscape splits cleanly in two:** consumer-tier (Andrew Ng, Wharton, IBM/Coursera) that stops at prompt patterns, and engineer-tier (Maven cohorts, AI Engineer Summit, LangChain webinars) that assumes Python and agents. **There is no good 60–90 min webinar serving curious generalists + intermediate users with real context engineering content.** This is the opening.

3. **Two teaching frameworks have won.** Use them as the workshop's structural backbone:
   - **Lance Martin's four strategies:** Write / Select / Compress / Isolate
   - **Drew Breunig's four failure modes:** Poisoning / Distraction / Confusion / Clash

4. **The non-engineer angle is undersupplied.** Almost everything published assumes you're building an agent. Almost nothing teaches the *same mental model* applied to everyday ChatGPT/Claude workflows (research, writing, analysis, document Q&A). That's our differentiation.

---

## What is context engineering (the workable definition)

The cleanest definition for a mixed audience, combining Tobi Lütke and Phil Schmid:

> Context engineering is the practice of providing **the right information and tools, in the right format, at the right time**, so the LLM has everything it needs to solve the task — and nothing that gets in the way.

Karpathy's OS metaphor (via Lance Martin) is the most teachable visual:

> The LLM is like a CPU. The context window is like RAM. Context engineering is loading the right things into RAM at each step — and clearing out what's no longer useful.

Anthropic's "attention budget" frame is the best one-liner for *why it matters*: context is a finite resource with diminishing returns. More context isn't better; **better-curated** context is better.

## Why this is more than prompt engineering

The shift the field made between 2023 and 2025:

| | Prompt engineering (2022–2023) | Context engineering (2024–2026) |
|---|---|---|
| Unit of work | The prompt | The trajectory |
| Window | 4K–8K tokens | 200K–1M+ tokens |
| Authored | Once, by hand | Dynamically, every turn |
| Ingredients | Instructions + a clever trick | Instructions + examples + retrieved knowledge + tools + memory + state |
| Failures | Bad wording | Poisoning, distraction, confusion, clash |
| Goal | Coax a chatbot | Engineer a system |

Travel-agent illustration (the canonical side-by-side):
- **2023:** "You're an expert travel agent. Don't exceed €200/night. Book Paris hotel."
- **2026:** System dynamically assembles: user profile from memory + the relevant clauses from the corporate travel policy via RAG + conference dates from calendar tool + live hotel availability from search tool. System prompt is small (~20%); the bulk is *just-in-time context*.

## The competitive landscape (and the gap)

29 mapped offerings across Maven, DeepLearning.AI, Coursera, Anthropic Skilljar, AI Engineer Summit, YouTube, Wharton, Stanford.

**Universal patterns:**
- Open with prompt-vs-context contrast
- Teach the write/select/compress/isolate quartet
- Include a hands-on "spec / PRP / plan document" exercise
- Use "vibe coding fails" as the cold-open hook

**The gaps (where we play):**
1. **Mixed-audience.** Almost every offering picks a side (consumer or engineer).
2. **Mental model, not toolkit.** The frameworks above are usable without Python — but no one teaches them that way.
3. **Beyond agents.** Apply context engineering to research, writing, analysis, document Q&A — workflows everyone has.
4. **Debugging context.** "Look at this failing prompt, diagnose the context problem." Nearly absent.
5. **A fresh hook.** The "vibe coding" opener is exhausted. Open with a real-world non-coding failure case.
6. **Stand-alone, not a course funnel.** Most free webinars are loss leaders for paid cohorts. Ours can just be the thing.

## Open questions for the design phase

The research surfaces design choices we'll need to make explicitly:

1. **How agent-y do we go?** Stay in chat-UI workflows (ChatGPT, Claude, Cursor used as chat) or go up to "and here's what happens when you build an agent?" Affects audience fit.
2. **How software-engineering-flavored do we make the framing?** The user's original insight — "SE has discovered techniques that translate" (specs, sub-agents, skills) — is a strong angle. But the audience won't all share that vocabulary. Translate or assume?
3. **One framework or two?** Use just Lance Martin's four strategies (write/select/compress/isolate) — cleaner — or also bring in Breunig's failure modes? The failure modes are arguably more teachable because they're concrete and diagnostic.
4. **Live demo or pre-recorded examples?** Live demo on a real Claude/ChatGPT instance is high-engagement but high-risk. Pre-recorded with live commentary is safer.
5. **Take-home artifact?** Spec template (à la Cole Medin's PRP), a context-engineering checklist, or just the slides + reading list?

## Sources to drop in the deck

If we end up linking outward, the smallest set that covers the territory:
1. Anthropic's "Effective Context Engineering" blog — institutional definition
2. Lance Martin's essay — four strategies framework
3. Drew Breunig's "Prompts vs. Context" — best non-technical explainer
4. Phil Schmid's "The New Skill" — best single-link to send attendees afterward
5. Karpathy's June 2025 tweet — origin moment

---

**Next step:** Take this synthesis into the design phase — decide the 5 open questions above, then draft the curriculum/outline.
