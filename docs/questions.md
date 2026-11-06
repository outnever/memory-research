# Open questions

Not a roadmap. A pool of questions worth attacking, in no order. Any of these can be
picked up, and anyone may add more — including questions that assume all of these are
wrong.

Each question should be answerable well enough to say "yes", "no", or "partly" with
evidence attached.

## On the context constraint

- Is "zero context cost" actually achievable, or only "bounded and small"?
- Can memory be consulted *without* the model choosing to consult it — and if so,
  who decides when?
- What is the real cost of a recall that returns nothing useful? Is a wasted lookup
  cheaper or dearer than a missed one?
- Does recall belong in the prompt at all, or could it live somewhere the model
  reaches only when it asks?

## On accuracy

- How do you detect a stale memory? Is superseding, versioning, or expiry the better
  mechanism — and does the answer depend on the fact type?
- What catches a conflated recall (X served for Y)? Is it structure, a check at read
  time, or something else?
- Is confidence calibratable for memories, or is that a trap?
- What should happen when two memories disagree? Who arbitrates?
- Can a memory system be *adversarially* tested — deliberately seeded with traps —
  and what would that test look like?

## On representation

- Does the representation need to be human-readable? What breaks if it is not?
- Is a graph worth its traversal cost, or is flat storage plus good indexing enough?
- Are vectors necessary, or a habit inherited from RAG?
- Can structure *reduce* context cost rather than increase it — e.g. by answering
  narrow questions directly?

## On measurement

- What is the benchmark? Does one exist, or must one be built?
- How is "precision of recall" defined so that two designs can be compared?
- What is the smallest experiment that would refute the most popular approach?

## On scope

- Should memory be per-agent, per-project, per-person, or shared? Who owns a memory?
- What must never be remembered, and how is that enforced?
- Does the system need to forget at all, or is storage cheap enough to keep everything?
