# memory-research

An open exploration: **a memory system for DeepSeek Harness that recalls precisely without spending context.**

This repository is a research sandbox. It deliberately starts empty of conclusions.
Nothing here is the "right" approach yet — the point is to find out what is.

## The goal

DSH agents forget. Sessions end, context windows fill, and everything learned in one
session is gone in the next. A memory system should fix that without turning every
prompt into a pile of retrieved text.

Two constraints define the problem, and they pull against each other:

1. **Recall must be accurate.** A memory that is confidently wrong is worse than no
   memory at all. The system must not invent, not conflate two similar things, and
   not serve a fact that has since been corrected.
2. **Recall must not consume context.** The value of remembering is lost if the
   remembering eats the window the agent needs to think. "Not consuming context"
   is the hard part — every obvious design (stuff retrieved text into the prompt)
   fails it.

## What is open

Everything below is a question, not a decision:

- **Representation.** Text? A graph? Vectors? Something structured? Symbols? A hybrid?
- **Write path.** What deserves to be remembered, and who decides — the agent, a rule,
  a model, or a person?
- **Retrieval.** Search? Traversal? Inference? Nothing at all, until asked?
- **Accuracy mechanism.** How do you *know* a recall was right? What catches a
  confident-but-wrong memory before it reaches the agent?
- **Context budget.** What is the actual cost of a recall, and how is it bounded?
- **Forgetting.** Does the system delete, decay, supersede, or keep everything forever?
- **Evaluation.** How is any of this measured? What is the benchmark for "precise recall"?

## How to work here

This repository is driven by an agent, with a person reviewing. See
[AGENTS.md](AGENTS.md) for how work is proposed, done and recorded, and
[docs/000-charter.md](docs/000-charter.md) for the charter in full.

## Prior art

Worth reading before proposing anything:

- Retrieval-augmented generation, and its known failure modes (hallucinated citations,
  lost-in-the-middle, chunk boundary errors)
- Knowledge graphs and semantic networks
- Memory-augmented neural networks, neural Turing machines
- Episodic vs semantic memory in cognitive science
- Vector databases, hybrid search, re-ranking
- MemGPT / Letta, Mem0, Zep, and similar agent-memory systems
- GraphRAG and community summarisation
- Human note-taking systems (Zettelkasten, spaced repetition) as prior art for *use*
- Caching and invalidation theory, which is what "stale memory" really is

Read them, then feel free to disagree with all of them.

## Licence

MIT
