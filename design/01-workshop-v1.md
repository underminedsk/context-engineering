# Workshop v1 — Design Notes

## Spine Decision

**The worked example: building a reusable email marketing campaign builder.**

Not running one campaign — building the system that runs every future campaign. This is the SE-translation pattern in its purest form: don't do the work, build the factory that does the work.

### Why email campaign builder over the alternatives

| Criterion | Email Builder | Blog Builder | CRM Outreach Builder |
|---|---|---|---|
| Discrete, named sub-skills | High (Audience, Hook, Copy, Subject, CTA, Brand, Compliance) | Medium (mostly linear) | Medium |
| Reusable across many runs | Weekly cycles — reuse felt immediately | Less frequent | Per-contact, very frequent |
| Demoable without connectors | Yes — paste customer data | Yes | No — depends on real CRM |
| Knowledge-worker audience breadth | Broadest | Broad but "AI writes blog posts" feels old | Narrower (sales-flavored) |
| GStack parallel | Clean — role names map directly | Weaker | Medium |
| One-shot failure is visible | Yes | Yes, but writing is subjective | Yes but harder to demo |

Email campaign builder wins on every pedagogical axis except connector-essentialness (where CRM wins). We make up for that by adding connectors in the back half of the workshop as the "now elevate it" moment.

### Why this works as a spine

- The sub-skills are *named specialist roles* — direct parallel to GStack's CEO / Designer / Eng Manager / QA. Audience sees the pattern without us labelling it.
- The four context-engineering strategies (Write / Select / Compress / Isolate) show up *as we build it*, not as theory.
- The four failure modes (Poisoning / Distraction / Confusion / Clash) appear as natural mistakes during the build — we name them when they happen.
- Connectors aren't a bolt-on lesson — they're the "now 10x this" moment.
- The take-home is each attendee's own builder, scoped to *their* domain, not just email.

### The audience generalization moment

By ~minute 30 the audience should no longer be thinking "this is about email." They should be thinking:

*"I could build one of these for proposals / quarterly reviews / lesson plans / case briefs / grant applications / discovery memos / press releases / RFP responses."*

That's when the workshop has done its job.

---

## Workshop Arc — v1 Sketch (~65 min)

| # | Section | Time | Beat |
|---|---|---|---|
| 1 | **Open** | 10 min | Show someone running campaign #5 in ChatGPT — pasting in brand voice, audience, product, last campaign's results every single time. *"What if you only had to tell it once?"* |
| 2 | **The shift** | 5 min | Prompt vs. context engineering: the difference between writing the email and building the email machine. One slide. |
| 3 | **Build the builder, live** | 30 min | Start with one prompt. Layer in: Brand Voice skill → Audience Researcher → Copywriter → Subject Line Optimizer → Compliance Checker. Each addition demonstrates one of Lance Martin's four strategies (Write/Select/Compress/Isolate). Failure modes show up naturally — we name them when they appear. |
| 4 | **GStack moment** | 10 min | Step back. Show GStack's roles directory side-by-side with what we just built. *"This is the same pattern. We just translated it to marketing."* The SE-to-other-domains thesis lands here. |
| 5 | **Connectors** | 5 min | Add a connector to their CRM/Drive. Watch the campaign get dramatically more specific. Don't say "MCP." |
| 6 | **Take-home** | 5 min | Skill Builder meta-prompt. Each attendee picks *their* domain (not email) and walks out with a starter builder. |
| 7 | **Q&A** | 10 min | |

Total: ~75 min, fits a 60–90 min slot with room to breathe.

---

## Open Design Questions

Before we can detail this further:

1. **Live audience or pre-recorded with live commentary?** Live is high-engagement / high-risk for the 30-min build. Pre-recorded with live narration is safer and lets us cherry-pick the failures we want to demo.
2. **Specific brand/product for the demo.** A real one (more credible) or a fictional clean one (no legal risk, no audience distraction)? Probably fictional — a small fictional company with a clear product so we can invent the constraints.
3. **What does the take-home "Skill Builder" actually look like at v1?** A paste-into-Claude meta-prompt (zero infra, ships today) or wait to build the hosted version? Leaning meta-prompt for v1 per earlier discussion in `/ideas.md`.
4. **Audience interaction during the build?** Polls? Chat questions at named beats? Or single-direction with Q&A at the end?
5. **Do we ship the email builder itself as a downloadable artifact**, alongside the meta-prompt? Yes seems obviously right — audience leaves with both *the example builder* and *the tool to build their own*.
6. **What's the cold-open hook?** The "campaign #5 with all the paste-ins" scenario is decent but can be sharper. A specific painful quote ("I spent 90 minutes prepping ChatGPT before I got the first usable draft") would land harder.

---

## What's Next

- Resolve the 6 open questions above.
- Draft the v0 of the email campaign builder itself (the actual skills + how they compose). This becomes the live-demo artifact.
- Draft the meta-prompt skill builder (the take-home).
- Outline slide structure for sections 1–7.
