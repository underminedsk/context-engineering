# Ideas & Brainstorm

Parking lot for workshop ideas. Each section is a candidate concept; decisions get pulled into the main design later.

---

## Skill Builder (interactive demo / take-home)

**Core idea.** A guided tool that walks users through crafting a targeted "skill" (reusable context block) for a goal they want to complete. Output: a downloadable skill file. Optional MCP server for the user to retrieve their own skills later.

**SE precedent.** The meta-skill / skill-creator pattern. Anthropic's `skill-creator` is the canonical example. Skills are the building blocks of purpose-built agents, so having a meta-tool to author them is standard practice in serious agent stacks.

**Why it fits this workshop.**
- Recursive pedagogy: using a context-engineering tool to make context-engineering artifacts. Audience watches context being assembled in real time to produce a focused output.
- Strong take-home value: attendees leave with something usable, not just slides.
- Differentiator. Per `research/03-similar-workshops.md`, almost every existing workshop ships a static spec/PRP template — an interactive builder is unclaimed territory.

**Tensions / open questions.**
- "Skills" is a Claude-ecosystem term. Mixed audience also uses ChatGPT, Gemini, etc. They have analogous primitives (Custom GPTs, Gems, Projects) but not the same file format. Options:
  - (a) Teach the concept generically ("reusable context blocks" / "context recipes") and let users adapt to their LLM of choice. Use Claude skills as the worked example.
  - (b) Target Claude specifically, accept some audience leakage.
  - (c) Multi-target output (Claude skill, Custom GPT system prompt, plain markdown). More work, more value.
- Live demo during the webinar vs. take-home only? Live is high engagement / high risk.
- What's the depth of guidance? A form generator is underwhelming. The valuable part is the LLM-driven interview — asking the right questions to extract what the skill actually needs.

**Staged build path.**
- **v1 (workshop centerpiece):** A prompt-based meta-skill — single prompt users paste into Claude/ChatGPT/Gemini that interviews them and generates a skill file. Zero infrastructure, ships today, *demonstrates the concept while teaching it*.
- **v2 (post-workshop):** Hosted web UI wrapping the v1 prompt. Clean form, download button, optional public gallery of community-built skills.
- **v3:** MCP server for the user to retrieve and reuse their own skills across sessions / clients.

**Cost reality.**
- Hosting: pennies/month on Vercel / Cloudflare / Netlify with a serverless LLM call.
- API: trivial for low traffic — a skill-build session is ~5K–20K tokens.
- Maintenance: minimal if scoped right (no auth, no persistent storage until v3).
- Real cost is initial design / prompt-engineering / testing, not infra.

**Next decisions before building.**
- Multi-LLM output, or Claude-first?
- Live vs. take-home (or both)?
- Is the website on the critical path for the webinar, or strictly post-event?

---

## Software Factory Frameworks → Other Domains

**Core idea.** Look at the software-factory frameworks emerging in 2024–2026 (Garry Tan's GStack, Cognition/Devin's research→plan→implement loop, Factory.ai, 12-Factor Agents, Anthropic's skills+sub-agents pattern, Cole Medin's PRP workflow) and ask: *which of these productize for non-engineering domains?*

This might be the **spine of the workshop**, not just a topic. The user's original framing — "SE has gone further on context engineering than most fields; let's translate" — is exactly this. Naming concrete frameworks gives it teeth.

**Candidates to study and translate.**
- **GStack (Garry Tan, YC CEO):** the headline example. Open-sourced personal Claude Code configuration. 23 opinionated skills that play roles — CEO, Designer, Eng Manager, Release Manager, Doc Engineer, QA — plus workflow skills for plan review, code review, one-command shipping, browser automation, QA testing, retrospectives. 89.7K GitHub stars in under two months. Tan averaged 10K LOC and 100 PRs/week, claims ~810× his 2013 pace. Design philosophy: *opinionated prompts, not custom tooling, are the right abstraction layer for AI-assisted development*. Each step inherits context from the previous — review gates, QA, release checks. Repo: https://github.com/garrytan/gstack.
- **12-Factor Agents (Dex Horthy):** already a manifesto. Several factors translate directly to non-SE knowledge work (own your prompts, own your context, evals, observability).
- **Research → Plan → Implement loop:** universally applicable. Any structured knowledge task — legal memo, market analysis, policy brief, lesson plan — benefits from this scaffolding.
- **PRP / spec-driven workflow (Cole Medin):** writing the spec *before* the work. Already standard in design and law; framing it as context engineering connects the dots.
- **Meta-skills / skill libraries (Anthropic):** see the Skill Builder section above.
- **Sub-agents / orchestration:** the practice of decomposing a hard problem into specialized roles. Translates to consulting, research synthesis, editorial workflows.

**Why GStack is the right primary anchor.**
- Credible non-hyperbolic source (YC's CEO).
- Concrete and copyable (it's a repo, not a philosophy).
- The 23-skills-as-roles structure is a near-perfect template for translation — every non-SE domain has a parallel set of roles.
- The performance number is workshop-grade hook material: *"Garry Tan, the CEO of Y Combinator, is shipping ~10K lines of code per week using a system he calls GStack. He's not writing the code — he's engineering the context. That's what we're going to learn today."*
- Visual: showing the actual roles directory in the repo (CEO, Designer, Eng Manager, QA…) makes the abstraction concrete in five seconds.

**Cross-domain examples to develop.**
- Lawyer: research → memo → opposition prep, each as a "skill" with its own context recipe.
- Consultant: discovery → analysis → deliverable, with reusable skills per industry.
- Educator: lesson planning → materials → assessment, each templated.
- Researcher: lit review → synthesis → write-up, with sub-agent-style decomposition.

**Pedagogical move.** Don't just list the frameworks — show one being applied to a non-SE problem live. This is where "we already do this in SE" becomes "and here's what it looks like for you."

**Open questions.**
- Lead with GStack and reference others briefly, or sample across? Leaning GStack-first now that we have the details.
- How much do we name the SE origin vs. just teach the practice? Naming it gives credibility; over-naming alienates the non-SE audience.
- Do we show the GStack repo on screen, or recreate a simplified version for the demo? Real repo is more credible; recreation is more on-message for non-engineers.

---

## Connectors as a Core Workshop Topic

**Core idea.** Teach connectors (Claude Connectors, ChatGPT Connectors, Custom GPT Actions, Notion AI integrations, Gemini extensions) as a first-class context engineering technique. The user doesn't need to know "MCP" as a protocol — they need to know that connectors are how you (a) get the right context into the model and (b) give the model tools to operate on external systems.

**Why it belongs in the workshop.**
- Connectors map directly to Lance Martin's **Select** strategy: pulling in external context (calendar, docs, email) and tools.
- For non-engineers, this is the single highest-leverage context-engineering move they can make today without code. Connecting Claude to Google Drive or ChatGPT to GitHub *immediately* transforms what the model can do for them.
- Bridges the gap between "I type into a chatbot" and "I have a system that does work for me" — the conceptual leap the workshop is trying to teach.

**How to frame it (non-technical).**
- "Your LLM doesn't have to be limited to what's in its training. You can plug it into your calendar, your documents, your email, your bug tracker — and it can both read from and act on them."
- Don't introduce MCP by name unless someone asks. Frame as "connectors" or "tools" depending on the LLM.
- Acknowledge the standard exists ("there's a protocol called MCP that makes this work across different AI tools") for the curious, then move on.

**Concrete demos / examples to choose from.**
- Claude + Google Drive: ask about your own docs.
- Claude + Gmail: triage email by your own criteria.
- ChatGPT + GitHub connector for the coding-curious.
- Custom GPT with an Action calling a real API.
- Notion AI summarizing across a workspace.

**Risks.**
- Connector availability differs across LLMs and changes monthly. Pick examples that have been stable.
- Privacy / data-handling questions will come up. Have a clear answer ready.
- Don't get sucked into a debugging demo if a connector fails live — have a recorded backup.

**Open questions.**
- Live connector demo vs. screen-recorded walkthrough?
- One deep example (Drive + Calendar) vs. a montage of five?
- Where in the arc — early (as motivation) or late (as the "now go further" capstone)?
