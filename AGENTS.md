# AGENTS.md

How work happens in this repository. Read [docs/000-charter.md](docs/000-charter.md) first.

## Who does what

- **A person** proposes work, answers questions, and merges pull requests. The person
  may not know the answer — that is expected. Questions are welcome.
- **An agent** reads, researches, experiments, and writes. The agent decides *how* to
  pursue a question; it does not decide *whether* a question is worth pursuing when
  the person has already asked for it.

## The loop

```
issue (a question)  →  research / experiment  →  result  →  pull request  →  review  →  merge
```

1. **A question arrives** as an issue. If it is vague, the agent asks for the missing
   specifics in the issue before starting work.
2. **The agent researches first.** Read prior art before designing anything. Cite what
   was read. Do not reinvent a wheel without saying which wheel it is.
3. **The agent states its plan in the issue** before doing the work: what it will try,
   and what result would count as success or failure. One or two sentences.
4. **The agent does the work** in its own branch. Small, reproducible steps.
5. **The agent records the outcome** and opens a pull request.

## Where things go

| Path | Holds |
| --- | --- |
| `docs/` | Numbered design documents. Read in order; each builds on the ones before. |
| `experiments/YYYYMMDD-HHMMSS-slug/` | One experiment per directory: the setup, the data, the result. |
| `src/` | Code. Prototypes live here only once they have something to measure. |
| `notes/` | Reading notes on prior art. One file per source or topic. |

## What a result must contain

A pull request that reports a result must include:

- **The question** it answers, quoted from the issue.
- **The setup** — enough to rerun it: commands, data, model, versions.
- **The outcome** — the number, the output, or the refutation. Not a summary of effort.
- **The context cost** — if the work says anything about retrieval, state what it costs.
- **What is still unknown** — including anything the result does not settle.
- **Speculation, clearly labelled** — as speculation, never as a finding.

A negative result is a valid, complete result. "This approach fails, here is the
evidence" closes an issue correctly.

## Standards

- **Never claim a measurement you did not make.** If it was not run, say it was not run.
- **Never present a guess as a finding.** Label it.
- **Cite prior art** with a link, in the text where it is used.
- **Keep the main branch working.** Prototypes that fail belong in a branch or in
  `experiments/`, not broken in `src/`.
- **Prefer deleting a wrong idea over defending it.** Changing your mind with evidence
  is the expected behaviour here.
- **Small commits, honest messages.** The commit message says what changed and why.

## When stuck

Say so in the issue, with the specific obstacle. Do not pad the time with unrelated
work, and do not silently lower the bar. A clear "this is blocked on X" is more
useful than a finished-looking document that answers nothing.
