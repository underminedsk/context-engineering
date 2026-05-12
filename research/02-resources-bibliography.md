# Context Engineering Resources: Annotated Bibliography

Inventory of existing instructional and reference material on context engineering. Quality ratings reflect depth, originality, and audience fit for a mixed (non-engineer + intermediate) webinar audience.

---

## 1. Foundational / Origin Posts

- **Andrej Karpathy, X/Twitter post (June 2025)** — https://x.com/karpathy/status/1937902205765607626 — Widely-cited origin of the term in its current form. "Context engineering is the delicate art and science of filling the context window." **Quality: High**.
- **Simon Willison, "Context engineering" (June 27, 2025)** — https://simonwillison.net/2025/jun/27/context-engineering/ — Short, accessible explainer arguing the term has a clearer self-evident meaning than "prompt engineering." **High** (good non-technical framing).
- **Tobi Lütke endorsement / HN reactions** — https://news.ycombinator.com/item?id=44427757 — Useful for the "why this term is sticking" narrative. **Medium**.

## 2. Long-form Blog Posts & Essays

- **Anthropic Engineering, "Effective Context Engineering for AI Agents"** — https://www.anthropic.com/engineering/effective-context-engineering-for-ai-agents — Definitive practitioner essay; system prompts, tools, examples, history; introduces "tight context" framing. **High**.
- **LangChain, "Context Engineering for Agents"** — https://blog.langchain.com/context-engineering-for-agents/ — Four-bucket taxonomy (write / select / compress / isolate). **High** (use this as the webinar's structural backbone).
- **Lance Martin, "Context Engineering for Agents" (June 23, 2025)** — https://rlancemartin.github.io/2025/06/23/context_engineering/ — Personal essay version with more nuance. **High**.
- **Drew Breunig, "How Contexts Fail and How to Fix Them"** — https://www.dbreunig.com/2025/06/26/how-to-fix-your-context.html — Names four failure modes (poisoning, distraction, confusion, clash) + fixes. **High** (extremely teachable taxonomy).
- **Drew Breunig, "Prompts vs. Context"** — https://www.dbreunig.com/2025/06/25/prompts-vs-context.html — Crisp distinction for non-technical audiences. **High**.
- **Drew Breunig, "Why 'Context Engineering' Matters"** — https://www.dbreunig.com/2025/07/24/why-the-term-context-engineering-matters.html — Sociological framing with search-volume evidence. **Medium**.
- **Phil Schmid, "The New Skill in AI is Not Prompting"** — https://www.philschmid.de/context-engineering — Widely shared executive-summary explainer. **High** (good single-link to send attendees).
- **Phil Schmid, Part 2** — https://www.philschmid.de/context-engineering-part-2 — Deeper on context rot and harness architecture. **Medium-High**.
- **Cognition AI, "Don't Build Multi-Agents" (Walden Yan)** — https://news.ycombinator.com/item?id=45096962, https://news.smol.ai/issues/25-06-13-cognition-vs-anthropic — Influential counterpoint: single-agent context sharing > multi-agent. **High** (great debate framing).
- **Simon Willison, "Agentic Engineering Patterns"** — https://simonw.substack.com/p/agentic-engineering-patterns — Adjacent material on context offloading and durable state. **Medium**.
- **LlamaIndex, "Context Engineering: What It Is and Techniques"** — https://www.llamaindex.ai/blog/context-engineering-what-it-is-and-techniques-to-consider — Vendor-neutral techniques rundown. **Medium**.
- **Weaviate, "Context Engineering – LLM Memory and Retrieval for AI Agents"** — https://weaviate.io/blog/context-engineering — Retrieval-focused angle. **Medium**.
- **Redis, "Context engineering: Best practices"** — https://redis.io/blog/context-engineering-best-practices-for-an-emerging-discipline/ — Memory-system angle. **Medium**.
- **Elastic Search Labs, "What is context engineering?"** — https://www.elastic.co/search-labs/blog/context-engineering-overview — Vendor-flavored but well-organized. **Medium**.

## 3. GitHub Repos

- **davidkimai/Context-Engineering** — https://github.com/davidkimai/Context-Engineering — 8.9k stars. Most prominent "handbook" repo: first-principles curriculum, templates, references to 1,400+ papers. **High** (gold mine for slide content).
- **Meirtz/Awesome-Context-Engineering** — https://github.com/Meirtz/Awesome-Context-Engineering — Comprehensive survey-style awesome list. **High**.
- **yzfly/awesome-context-engineering** — https://github.com/yzfly/awesome-context-engineering — Curated papers / tools / best-practices. **Medium**.
- **coleam00/context-engineering-intro** — https://github.com/coleam00/context-engineering-intro — Hands-on template for AI coding assistants (Claude Code-centric). **Medium-High**.
- **bonigarcia/context-engineering** — https://github.com/bonigarcia/context-engineering — Companion repo for forthcoming Manning book. **Medium** (WIP).
- **danielrosehill/Context-Engineering-Resources** — https://github.com/danielrosehill/Context-Engineering-Resources — Resource index. **Low-Medium**.
- **muratcankoylan/Agent-Skills-for-Context-Engineering** — https://github.com/muratcankoylan/Agent-Skills-for-Context-Engineering — Practical "skills" collection. **Low-Medium**.
- **GitHub topic page** — https://github.com/topics/context-engineering — Discovery for newer entrants. **Medium**.

## 4. Books & Book Chapters

- **Chip Huyen, *AI Engineering* (O'Reilly, 2025)** — https://www.oreilly.com/library/view/ai-engineering/9781098166298/ — Chapter on "Enhance Context"; treats context construction as feature engineering for foundation models. Repo: https://github.com/chiphuyen/aie-book. **High**.
- **Boni Garcia, *Context Engineering* (Manning, forthcoming 2026)** — https://github.com/bonigarcia/context-engineering — First dedicated trade book. **Medium**.
- **O'Reilly, *Context Engineering with DSPy*** — https://www.oreilly.com/library/view/context-engineering-with/0642572261603/ — DSPy-focused. **Medium**.
- **O'Reilly, *Context Engineering for Multi-Agent Systems*** — https://www.oreilly.com/library/view/context-engineering-for/9781806690053/ — Niche. **Medium**.

## 5. Academic / arXiv

- **Mei et al., "A Survey of Context Engineering for LLMs" (arXiv:2507.13334, July 2025)** — https://arxiv.org/abs/2507.13334 — Formal taxonomy; 1,400+ papers analyzed. **High** (cite for academic credibility).
- **"Agentic Context Engineering: Evolving Contexts for Self-Improving LMs" (arXiv:2510.04618)** — https://arxiv.org/abs/2510.04618 — ACE framework: contexts as evolving playbooks. **Medium-High** (frontier).
- **HuggingFace paper page** — https://huggingface.co/papers/2507.13334 — Discussion. **Low-Medium**.

## 6. Cheatsheets, Infographics, Vendor Frameworks

- **Faros AI, "Context Engineering for Developers"** — https://www.faros.ai/blog/context-engineering-for-developers — Architecture infographic, 5-strategy framework. **Medium-High**.
- **Vellum, "Context Is King"** — https://www.vellum.ai/blog/context-is-king-why-context-engineering-is-the-new-frontier-for-ai-agents — Instructions/knowledge/tool-feedback framework. **Medium**.
- **Vellum, "Multi-Agent Systems"** — https://www.vellum.ai/blog/multi-agent-systems-building-with-context-engineering — Practitioner walkthrough. **Medium**.
- **Weaviate ebook** — https://weaviate.io/ebooks/the-context-engineering-guide — Sales-gated but useful structure. **Medium**.
- **DataCamp, "Context Engineering: A Guide With Examples"** — https://www.datacamp.com/blog/context-engineering — Beginner-friendly with code examples. **Medium** (good for non-engineer audience).
- **Memgraph, "Context Engineering for Beginners"** — https://memgraph.com/blog/context-engineering-for-beginners — Beginner-level. **Medium**.
- **Prompt Engineering Guide, "Context Engineering Guide"** — https://www.promptingguide.ai/guides/context-engineering-guide — DAIR.AI guide. **Medium-High**.
- **VS Code Docs, "Set up a context engineering flow"** — https://code.visualstudio.com/docs/copilot/guides/context-engineering-guide — Microsoft doc. **Medium**.
- **ByteByteGo, "A Guide to Context Engineering for LLMs"** — https://blog.bytebytego.com/p/a-guide-to-context-engineering-for — Strong visual explainers. **Medium-High** (most "webinar-shaped" content).

## 7. Video / Conference Talks

- **Dex Horthy, "12-Factor Agents"** — https://home.mlops.community/public/videos/12-factor-agents-patterns-of-reliable-llm-applications-dexter-horthy-agents-in-production-2025-2025-08-06 — Widely credited as first deep practitioner dive that crystallized "context engineering"; the 40-60% "dumb zone." **High**.
- **Lance Martin on Latent Space podcast** — https://www.latent.space/p/context-engineering-for-agents-lance — Long-form discussion. **High**.
- **Lance Martin, "Context Engineering for Agents" (YouTube)** — https://www.youtube.com/watch?v=_IlTcWciEC4 — Standalone talk. **High**.
- **Andrej Karpathy, "From Vibe Coding to Agentic Engineering"** — https://www.youtube.com/watch?v=96jN2OCOfLs — Broader keynote that touches context engineering. **High**.
- **"LLM Context Engineering Bootcamp – Lecture 1"** — https://www.youtube.com/watch?v=xlUIiTSaFKI — Free YouTube bootcamp. **Medium**.
- **AI Engineer Summit talks index** — https://www.ai.engineer/, https://www.youtube.com/@aiDotEngineer — Multiple 2025 talks tagged "context engineering". **Medium-High**.
- **O'Reilly Radar podcast w/ Drew Breunig** — https://www.oreilly.com/radar/podcast/generative-ai-in-the-real-world-context-engineering-with-drew-breunig/ — Good 30-min listen. **Medium-High**.

## 8. Newsletters Covering It Regularly

- **Latent Space (swyx & Alessio)** — https://www.latent.space/ — Podcast + "2025 AI Engineering Reading List" https://www.latent.space/p/2025-papers. **High**.
- **Simon Willison's Weblog** — https://simonwillison.net/ — Tag pages for "context-engineering" surface new entries. **High**.
- **Aurimas Griciūnas, SwirlAI — "State of Context Engineering in 2026"** — https://www.newsletter.swirlai.com/p/state-of-context-engineering-in-2026 — Annual summary. **High**.
- **Hugo Bowne-Anderson, High Signal** — https://hugobowne.substack.com/p/ai-agent-harness-3-principles-for — Lance Martin episode on "3 principles for context engineering." **Medium**.
- **ByteByteGo Newsletter** — https://blog.bytebytego.com/ — Periodic visual explainers. **Medium-High**.
- **Department of Product** — https://departmentofproduct.substack.com/p/context-engineering-for-ai-agents — Written for PMs / non-engineers. **Medium-High** (excellent fit for our non-engineer attendees).
- **Hamel Husain** — https://hamelhusain.substack.com/ — Doesn't lead with the term but his evals content is the natural companion. **Medium**.

---

## Notable Gaps for Workshop Design

- The space is dominated by **engineering-audience** material; non-engineer-friendly pieces are Breunig's "Prompts vs. Context," Phil Schmid's intro, the Department of Product post, and DataCamp's guide. A non-engineer-focused webinar is **not duplicative**.
- The four-bucket framework (write/select/compress/isolate) from LangChain and the four-failure-mode taxonomy (poisoning/distraction/confusion/clash) from Breunig are the two most teachable mental models — nothing replaces a webinar that explains them with concrete examples and live demos.
- David Kimai's repo and the arXiv survey are the canonical "go deeper" references to link at the end.
