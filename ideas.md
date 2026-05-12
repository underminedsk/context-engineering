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
