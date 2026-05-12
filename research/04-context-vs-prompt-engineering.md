# Context Engineering vs. Prompt Engineering: Discourse Map

## 1. The received view

The dominant framing across mid-2025 to early-2026 commentary: **context engineering is a superset / natural successor of prompt engineering**. Prompt engineering is what you do when you type something into a chatbot; context engineering is what you do when you build an LLM-powered system. Anthropic's official line crystallized this: "context engineering is the natural progression of prompt engineering." Most thought leaders treat the new term as a course-correction against the way "prompt engineering" got colonized in 2023 by SEO blog posts about "act as an expert" tricks and jailbreak hacks.

The term was popularized in a roughly two-week span in June 2025: **Tobi Lütke** floated it (June 19), **Karpathy** endorsed and elaborated (June 25), **Lance Martin** (LangChain) and **Simon Willison** wrote it up (June 23/27), and **Anthropic** formalized it (Sept 29, 2025).

## 2. Direct quotes from named thought leaders

**Tobi Lütke (CEO, Shopify), June 19, 2025:**
> "I really like the term 'context engineering' over prompt engineering. It describes the core skill better: the art of providing all the context for the task to be plausibly solvable by the LLM."
> (https://x.com/tobi/status/1935533422589399127)

Follow-on: "DSPy is my context engineering tool of choice." (https://x.com/tobi/status/1937967281599898005)

**Andrej Karpathy, June 25, 2025:**
> "+1 for 'context engineering' over 'prompt engineering'. People associate prompts with short task descriptions you'd give an LLM in your day-to-day use. When in every industrial-strength LLM app, context engineering is the delicate art and science of filling the context window with just the right information for the next step."
> (https://x.com/karpathy/status/1937902205765607626)

Karpathy lists what fills the window: "task descriptions, few-shot examples, RAG outputs, multimodal data, tools, state, history."

**Simon Willison, June 27, 2025:**
> "I think 'context engineering' is going to stick - unlike 'prompt engineering' it has an inferred definition that's much closer to the intended meaning, which is to carefully and skillfully construct the right context to get great results from LLMs."
> (https://simonwillison.net/2025/Jun/27/context-engineering/)

He adds that prompt engineering had suffered because "many people's inferred definition is that it's a laughably pretentious term for typing things into a chatbot."

**Anthropic engineering blog, September 29, 2025:**
> "At Anthropic, we view context engineering as the natural progression of prompt engineering."
> "Building with language models is becoming less about finding the right words and phrases for your prompts, and more about answering the broader question of 'what configuration of context is most likely to generate our model's desired behavior?'"
> "Good context engineering means finding the smallest possible set of high-signal tokens that maximize the likelihood of some desired outcome."
> (https://www.anthropic.com/engineering/effective-context-engineering-for-ai-agents)

Anthropic's X promo: "Most developers have heard of prompt engineering. But to get the most out of AI agents, you need context engineering." (https://x.com/AnthropicAI/status/1973098580060631341)

**Lance Martin (LangChain), June 23, 2025:**
> "Context engineering is the art and science of filling the context window with just the right information at each step of an agent's trajectory."

The canonical OS analogy: **"LLMs are like a new kind of operating system. The LLM is like the CPU and its context window is like the RAM, serving as the model's working memory."**

Organizes the discipline into four buckets: **Write, Select, Compress, Isolate.**
(https://rlancemartin.github.io/2025/06/23/context_engineering/)

**Walden Yan (Cognition / Devin):**
> "Prompt engineering was coined as a term for the effort needing to write your task in the ideal format for an LLM chatbot. Context engineering is the next level of this. It is about doing this automatically in a dynamic system."
> "At the core of reliability is context engineering."
> (https://cognition.ai/blog/dont-build-multi-agents)

**Drew Breunig:** Catalogued specific failure modes that only show up at the systems level: **context poisoning, context distraction, context confusion, context clash.** (https://www.dbreunig.com/2025/07/24/why-the-term-context-engineering-matters.html)

**Hamel Husain** has not blessed the term itself but argues substantively the same. His "LLM bullshit knife" tweet cuts through buzzwords:
> "RAG → Provide relevant context; Agentic → Function calls that work; CoT → Prompt model to think/plan; FewShot → Add examples; PromptEng → Someone w/good written comm skills."
> (https://x.com/HamelHusain/status/1798757828100047063)

## 3. Successor, superset, subset, or parallel?

Three views coexist:

- **Successor view (Anthropic, Lütke, Karpathy):** "natural progression" / "next level." Prompt engineering = 2023 chatbots; context engineering = 2025-26 agents.
- **Superset view (HN consensus, Drew Breunig):** Best HN comment Breunig amplifies: *"Context engineering isn't a rebranding. It's a widening of scope. Like how all squares are rectangles but not all rectangles are squares — prompt engineering is context engineering, but context engineering also includes other optimisations that are not prompt engineering."* (https://news.ycombinator.com/item?id=44462128)
- **"Always was" view (Hamel-adjacent, Willison's softer position):** The serious people were always doing context work; the term just got hijacked.

## 4. Concrete side-by-side example

Most widely-circulated illustration is the **travel-booking agent**:

- **Prompt-engineered approach (2023 style):** Long system prompt — *"You are an Expert Travel Agent. Be helpful. Follow company policy. Don't exceed €200/night for hotels. Prefer Marriott and Hilton. Be concise."* — plus user message *"Book me a hotel in Paris for the DevOps conference."* Tweaks: CoT triggers, role-play framing, few-shot baked into the system prompt.
- **Context-engineered approach (2026 style):** *Dynamic assembly* at request time. System fetches: (a) user profile and travel history from memory, (b) *specific* relevant clauses from the corporate travel policy via RAG (not the whole 50-page PDF — "just-in-time context"), (c) conference dates and venue from a calendar tool, (d) live hotel availability from a search tool. System prompt is small (~20%); bulk (~80%) is dynamic context selected for *this* turn. State compacted between turns; old tool outputs cleared.
  (https://www.elastic.co/search-labs/blog/context-engineering-vs-prompt-engineering, https://www.regal.ai/blog/context-engineering-for-ai-agents)

Second illustration from Lance Martin: **Anthropic's multi-agent researcher** has the LeadResearcher *write its plan to external memory* before its 200K context window fills up — pure context engineering, no prompt re-wording could solve it.

## 5. Historical arc: what changed in the tech

- **2022–2023 prompt engineering:** Single-turn, single-call. GPT-3.5 / early GPT-4. Zero-shot, few-shot (Brown 2020), CoT (Wei 2022), "Let's think step by step" (Kojima 2022), ReAct, Tree-of-Thought (Yao 2023), role-play personas. Context windows: 4K–8K tokens. Unit of work: *the prompt*.
- **2024–2026 context engineering:** Multi-turn agents, 200K–1M+ token windows, native tool use, MCP, RAG-as-default, long-running tasks (Devin, Claude Code, Cursor). Unit of work: *the trajectory*. New problems that prompt engineering literally cannot address: window overflow, context poisoning across 50+ tool calls (Manus AI's typical figure), state handoff between sub-agents, memory persistence. Drivers: long-context models, function-calling APIs, retrieval as table stakes, agent loop replacing chatbot turn.

## 6. The skeptic view

Pushback clusters on three lines:

- **"It's rebranding."** OpenAI Developer Community thread *"Prompt Engineering Is Dead, and Context Engineering Is Already Obsolete"* argues both terms paper over what is really workflow architecture (https://community.openai.com/t/prompt-engineering-is-dead-and-context-engineering-is-already-obsolete/1314011). HN: *"Another marketing term"*; *"context is something most practitioners already knew the importance of and used for years."*
- **"It's not engineering."** From HN: *"abusing the term 'engineering' in a desperate attempt to stroke egos."* The work is *"mostly a list of barely disguised tips, tricks and heuristics."* (https://news.ycombinator.com/item?id=44432596, https://news.ycombinator.com/item?id=44508068)
- **"It's just RAG with a haircut."** *The New Stack* and Latent Space's Jeff Huber episode engage the *"RAG is dead, context engineering is king"* framing — half-mockingly. (https://thenewstack.io/rag-isnt-dead-but-context-engineering-is-the-new-hotness/)

Hamel Husain's "bullshit knife" tweet implicitly aligns: every term is just a label for an existing concrete practice; the labels keep changing, the practice doesn't.

## Source URLs

- https://x.com/karpathy/status/1937902205765607626 — Karpathy's anchor tweet
- https://x.com/tobi/status/1935533422589399127 — Lütke's anchor tweet
- https://simonwillison.net/2025/Jun/27/context-engineering/ — Willison's writeup
- https://www.anthropic.com/engineering/effective-context-engineering-for-ai-agents — Anthropic
- https://rlancemartin.github.io/2025/06/23/context_engineering/ — Lance Martin
- https://www.langchain.com/blog/context-engineering-for-agents — LangChain version
- https://cognition.ai/blog/dont-build-multi-agents — Walden Yan / Cognition
- https://www.dbreunig.com/2025/07/24/why-the-term-context-engineering-matters.html — Breunig's defense
- https://news.ycombinator.com/item?id=44379538 — HN debate on Karpathy
- https://news.ycombinator.com/item?id=44462128 — "widening of scope"
- https://community.openai.com/t/prompt-engineering-is-dead-and-context-engineering-is-already-obsolete/1314011 — skeptic thread
- https://thenewstack.io/rag-isnt-dead-but-context-engineering-is-the-new-hotness/ — skeptical-leaning
- https://x.com/HamelHusain/status/1798757828100047063 — Hamel's "bullshit knife"
- https://the-decoder.com/shopify-ceo-and-ex-openai-researcher-agree-that-context-engineering-beats-prompt-engineering/ — Lütke + Karpathy coverage

## Pedagogical note for the workshop opening

Cleanest anchor for a mixed-experience audience:
1. **Karpathy + Lütke pair** — one-tweet definition + CEO co-sign
2. **Anthropic "natural progression"** — institutional weight
3. **Lance Martin's OS / RAM analogy** — intuition
4. **Travel-agent side-by-side example** — concrete difference
5. **Brief skeptic acknowledgment** — inoculates the experienced attendees against feeling pandered to
