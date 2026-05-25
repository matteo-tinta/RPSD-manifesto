---
name: research-methodology
description: 'Use for discovery snapshots, implementation research, historical patch analysis, and evidence-backed recommendations. Answers questions like "How is this implemented now?" or "What are the current patterns and flows?", etc. This skill defines the unbreakable foundation of research methodology for AI agents. More instructions may be added in the project.'
argument-hint: 'Research question, scope, and mode (Feature or Discovery)'
user-invocable: false
---

# Research Methodology Skill

## Goals
- *Evidence-backed outputs*: current state with always source references (file path, doc link, commit hash).
- *Scoped & verifiable*: one focused question per research phase; refuse broad scope.
- *Factual only*: no assumptions, opinions, proposals, TODOs, or future-state plans.
- *Sources inline*: link evidence at point of use; do not hide research process.
- *Concise*: target under 200 lines; no binaries or generated artifacts.
- *Unknowns are explicit*: no hidden assumptions; document blockers and unknowns clearly.

## Use Cases
- Answer: "How is this implemented now?"
- Need evidence from docs, code, git history.
- Produce `features/<feature>/research.md` or `discovery/<topic>.md`.

## Inputs
- *Research question*: single, focused, narrow scope.
- *Mode*:
  - *Discovery Research*: patterns, flows, snippets; no research.md required.
  - *Feature Research*: full findings, blockers, unknowns, recommendations; may include discovery snapshot.

## Output
> templates in `resources/templates`

| Mode | File | Content | Used When |
|------|------|---------|---------|
| Discovery | `discovery/<topic>.md` | Patterns, flows, snippets, evidence links. | "We need to discover", "Learn about" |
| Feature | `features/<feature>/research.md` | Findings, blockers, unknowns, recommendations, commit hashes. | "We need a feature search", "Research for implementation" |

## Search Order
1. *Discovery docs*: inspect local discovery and known patterns.
2. *Git history*: commits, messages, patches.
3. *Code & files*: structures, flows, code, docs.

## Procedure
1. *Define scope*: set mode (Discovery/Feature), one focused question; refuse if too broad.
2. *Execute search order*: follow 1→2→3 above.
3. *Iterate if needed*: insufficient evidence → run focused round; scope expands → stop, dump findings, and request new phase.
4. *Document findings*: patterns, flows, snippets only; exclude proposals, TODOs.
5. *Compile report*: include findings, file/doc refs, commit hashes, blockers, unknowns, recommendations; summarize patches.
6. *Summarize*: short user-facing summary; let user decide next steps.
7. *Output*: save to correct path based on mode.

## Validation
- [ ] Question answered with evidence.
- [ ] Every major claim has source reference.
- [ ] Unknowns explicit, no hidden assumptions.
- [ ] Output within mode and file scope.
