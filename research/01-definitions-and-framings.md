# Context Engineering: Definitions and Framings

## Overview — Where the Term Came From

The phrase "context engineering" went from niche developer slang to industry consensus terminology over a roughly three-month window in **mid-2025**. Practitioners (especially agent builders at LangChain) had been doing the work for "a year or two" before it got a clean name. The naming cascade:

- **June 19, 2025** — **Tobi Lütke** (Shopify CEO) tweets his endorsement of the term, framing it as a "core skill."
- **June 23, 2025** — **Harrison Chase** (LangChain co-founder/CEO) publishes "The rise of context engineering" on the LangChain blog, offering the now-canonical "dynamic systems" definition. Lance Martin publishes the influential four-strategy framework ("write, select, compress, isolate") the same week.
- **June 25, 2025** — **Andrej Karpathy** (ex-OpenAI/Tesla) co-signs the term on X, supplying the most-quoted single line: "the delicate art and science of filling the context window with just the right information for the next step."
- **June 27–29, 2025** — **Simon Willison** writes "Context engineering" on his weblog, arguing the rename is healthy because "prompt engineering" had been redefined in the popular mind as typing tricks into a chatbot. **Drew Breunig** publishes "How Long Contexts Fail," cataloging failure modes (context poisoning, distraction, confusion, clash).
- **September 2025** — **Anthropic** publishes "Effective context engineering for AI agents" on its engineering blog, giving the framing institutional weight and contributing the "attention budget" / "finite resource" metaphors plus the Goldilocks/altitude framing for system prompts.

## Canonical Definitions (Quoted, with Attribution)

**1. Andrej Karpathy (X, June 25, 2025)**
> "+1 for 'context engineering' over 'prompt engineering'. People associate prompts with short task descriptions you'd give an LLM in your day-to-day use. When in every industrial-strength LLM app, context engineering is the delicate art and science of filling the context window with just the right information for the next step."

He extends in the same thread:
> "Science because doing this right involves task descriptions and explanations, few shot examples, RAG, related (possibly multimodal) data, tools, state and history, compacting… Too little or of the wrong form and the LLM doesn't have the right context for optimal performance. Too much or too irrelevant and the LLM costs might go up and performance might come down."

Source: https://x.com/karpathy/status/1937902205765607626

**2. Tobi Lütke (X, June 19, 2025)**
> "I really like the term 'context engineering' over prompt engineering. It describes the core skill better: the art of providing all the context for the task to be plausibly solvable by the LLM."

Source: https://x.com/tobi/status/1935533422589399127

**3. Harrison Chase / LangChain ("The rise of context engineering," June 23, 2025)**
> "Context engineering is building dynamic systems to provide the right information and tools in the right format such that the LLM can plausibly accomplish the task."

> "Most of the time when an agent is not performing reliably the underlying cause is that the appropriate context, instructions and tools have not been communicated to the model."

Source: https://blog.langchain.com/the-rise-of-context-engineering/

**4. Anthropic Engineering ("Effective context engineering for AI agents," Sept 2025)**
> "Context engineering refers to the set of strategies for curating and maintaining the optimal set of tokens (information) during LLM inference, including all the other information that may land there outside of the prompts."

> "Like humans, who have limited working memory capacity, LLMs have an 'attention budget' that they draw on when parsing large volumes of context."

> "Given that LLMs are constrained by a finite attention budget, good context engineering means finding the smallest possible set of high-signal tokens that maximize the likelihood of some desired outcome."

Source: https://www.anthropic.com/engineering/effective-context-engineering-for-ai-agents

**5. Philipp Schmid ("The New Skill in AI is Not Prompting, It's Context Engineering")**
> "Context Engineering is the discipline of designing and building dynamic systems that provides the right information and tools, in the right format, at the right time, to give a LLM everything it needs to accomplish a task."

> "Agent failures aren't only model failures; they are context failures."

Source: https://www.philschmid.de/context-engineering

## The Component View — What's "In" Context Engineering

Broad consensus: context engineering encompasses everything the model sees at inference time. The recurring component list:

- **System prompt / instructions** — role, behavior, rules.
- **User prompt** — the immediate task.
- **Few-shot examples** — demonstrations of desired behavior.
- **Retrieved knowledge (RAG)** — domain docs, embeddings results.
- **Tool definitions / schemas** — what the agent can call.
- **Tool call outputs** — observations from the environment.
- **Conversation/message history** — short-term memory.
- **Long-term memory** — persistent state across sessions.
- **State / scratchpads** — agent's own notes and intermediate reasoning.
- **Structured output schemas** — format constraints.

**Lance Martin's four-strategy framework** (the most-adopted teaching frame):
1. **Write** context (save it outside the window — scratchpads, memory)
2. **Select** context (pull it in — retrieval, tool selection)
3. **Compress** context (summarize, truncate; Anthropic calls this "compaction")
4. **Isolate** context (split across sub-agents with clean windows)

Anthropic's parallel framing of long-horizon techniques: **compaction, structured note-taking, sub-agent architectures.**

A common decomposition (Lance Martin, echoed widely): context falls into three types — **instructions, knowledge, and tools** (guidance, what it knows, what it can do).

## Tensions and Disagreements

1. **Rebrand vs. genuine discipline.** Critics argue context engineering is just prompt engineering rebranded — or already obsolete in favor of "automated workflow architecture." Defenders argue the prompt-engineering label had been "redefined to mean typing prompts full of stupid hacks into a chatbot," and a new term was needed.

2. **Superset vs. successor.** Some framings treat context engineering as a **superset** containing prompt engineering and RAG. Others treat it as a **successor** — "Prompt engineering is dead." Anthropic threads the needle: "context engineering is the natural progression of prompt engineering."

3. **Static prompt vs. dynamic system.** Chase, Schmid, and LangChain insist the *dynamic, runtime-assembled* nature is the load-bearing distinction — context isn't a string you author once, it's the output of a system that runs every turn.

4. **The "more context is better" fallacy.** Anthropic and Drew Breunig push back hard on the long-context-window era of "just stuff it all in." Breunig catalogs four failure modes:
   - **Context poisoning** — a hallucination gets referenced repeatedly
   - **Context distraction** — model over-fixates on the window vs. its training
   - **Context confusion** — irrelevant info degrades output
   - **Context clash** — contradictory information

   Chroma Research's "context rot" study showed accuracy decays well before the advertised token limit.

5. **The Goldilocks problem for system prompts.** Anthropic frames an explicit tension: hardcoding brittle if-else logic in prompts vs. vague high-level guidance that gives no signal. The right "altitude" is specific enough to guide, flexible enough to let the model think.

## Mental Models and Metaphors

- **Karpathy's "LLM as operating system, context window as RAM":** the engineer's job is OS-like — load working memory with the right code and data.
- **Anthropic's "attention budget" / "finite resource":** context is scarce, has diminishing marginal returns, must be spent on high-signal tokens.
- **Schmid's "right info, right tools, right format, right time":** the four "rights" mnemonic.
- **Karpathy's "delicate art and science":** explicitly hybrid — judgment plus measurement.
- **"Context as the new moat"** (Harrison Chase, Sequoia podcast): differentiator for production agents is no longer model choice but context plumbing.
- **The agent's "trajectory":** Lance Martin frames context engineering as filling the window correctly *at each step* of a multi-turn trajectory, not just at the start.

## Source URLs

1. Anthropic Engineering — Effective context engineering for AI agents: https://www.anthropic.com/engineering/effective-context-engineering-for-ai-agents
2. Andrej Karpathy on X (June 25, 2025): https://x.com/karpathy/status/1937902205765607626
3. Tobi Lütke on X (June 19, 2025): https://x.com/tobi/status/1935533422589399127
4. Harrison Chase / LangChain — The rise of context engineering: https://blog.langchain.com/the-rise-of-context-engineering/
5. Lance Martin — Context Engineering for Agents: https://rlancemartin.github.io/2025/06/23/context_engineering/ (mirror: https://blog.langchain.com/context-engineering-for-agents/)
6. Simon Willison — Context engineering (June 27, 2025): https://simonwillison.net/2025/jun/27/context-engineering/
7. Drew Breunig — How Long Contexts Fail: https://www.dbreunig.com/2025/06/22/how-contexts-fail-and-how-to-fix-them.html
8. Drew Breunig — How to Fix Your Context: https://www.dbreunig.com/2025/06/26/how-to-fix-your-context.html
9. Philipp Schmid — The New Skill in AI is Not Prompting: https://www.philschmid.de/context-engineering
10. Prompting Guide — Context Engineering Guide: https://www.promptingguide.ai/guides/context-engineering-guide
11. Addy Osmani — Context Engineering: Bringing Engineering Discipline to Prompts: https://addyo.substack.com/p/context-engineering-bringing-engineering
12. Sequoia Capital podcast with Harrison Chase: https://sequoiacap.com/podcast/context-engineering-our-way-to-long-horizon-agents-langchains-harrison-chase/

## Notes

- WebFetch was 403-blocked across primary sources (anthropic.com, simonwillison.net, blog.langchain.com, x.com); all quotes assembled from WebSearch's extracted text. Quotes match multiple corroborating secondary sources but for verbatim slide-quoting, re-verify Anthropic and LangChain originals from a logged-in browser.
- The two cleanest, most non-technical-audience-friendly definitions are Tobi Lütke's ("providing all the context for the task to be plausibly solvable") and Schmid's "four rights" formulation — both avoid jargon like "tokens" and "inference."
