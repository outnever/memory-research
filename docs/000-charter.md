# 000 — Charter

## Why this exists

A separate effort (`thinkAboutMemory`, not public) is already pursuing one line of
design for DSH memory. **This repository is not that effort and must not copy it.**

The purpose here is the opposite: to explore the space *outside* that line. Assume
the existing approach may be wrong, incomplete, or solving the wrong problem. Find
alternatives, including ones nobody has tried.

Disagreement is the point. If everything explored here happens to confirm the other
effort, that is a result — but it should be an *earned* result, not an assumption.

## The two constraints

### 1. Recall accuracy must be high

Precision matters more than recall. Missing a memory is a small cost; serving a
wrong one is a large one, because the agent will act on it.

Concretely, a design fails this constraint if it can:

- **Invent** — return something that was never stored, or was stored as speculation
  but recalled as fact.
- **Conflate** — return a fact about X when asked about Y, because X and Y look similar.
- **Serve stale facts** — return a value that a later write corrected or superseded.
- **Lose provenance** — return a claim with no way to check where it came from or
  whether it is still true.

Note "high accuracy" is not "never wrong". It is: *when it is wrong, the system
notices, or the design makes the error survivable.* Say which one your design does.

### 2. Recall must not consume context

This is the binding constraint and the reason existing memory systems do not
transfer directly. Every design must state its **context cost per recall** honestly.

- Stuffing retrieved documents into the prompt is the default failure mode.
  If your design does this, say so explicitly and justify why it is unavoidable.
- Cost is not only tokens. It is also latency, and the attention the agent must
  spend deciding what to retrieve.
- A design that requires the agent to formulate a good query has moved the cost,
  not removed it. That may still be a valid trade — but say so.

## What counts as progress

Not "a working system". Progress here is:

- **A sharper question.** Decomposing "memory" into sub-problems that can be tested
  separately is real progress, even with no code.
- **A measured experiment.** A claim with a number attached, and the setup that
  produced it, even if the number is bad.
- **A refuted hypothesis.** Showing that an obvious approach fails, with evidence,
  saves the next attempt. Negative results are first-class here.
- **A working prototype.** Only valuable if it also reports its context cost and its
  measured accuracy. A prototype without those two numbers is a demo, not a result.

## Rules

- **Every claim carries evidence.** No "this should work" without a test, a citation,
  or an explicit label that it is speculation.
- **Label speculation.** Mark it so it is never recalled later as if it were a finding.
- **Keep experiments reproducible.** Record the exact setup: data, model, settings.
  An experiment nobody can rerun is an anecdote.
- **Prefer small and testable.** A question answerable this week beats a design doc
  for next year.
- **Report what failed.** Especially when it was your own idea.
