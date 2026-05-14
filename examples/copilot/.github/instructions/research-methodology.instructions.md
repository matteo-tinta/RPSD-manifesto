---
description: "Use when conducting research or investigation in this project: answering implementation questions, gathering evidence from code/docs/git history, writing discovery snapshots or research reports. This is the main instruction for research methodology that all agents must follow when conducting research or investigation in this project."
name: Research Methodology
applyTo: '**'
---

# Research Methodology

> This instruction file defines the research methodology for AI agents in this codebase, and must be followed by all agents. 
> Refer to [research-methodology skill](../skills/research-methodology/SKILL.md) for general procedure, search order, decision logic, and completion checklist.

## Delegation
- **Discovery agents**: discovery search
- **Git Researcher agents**: git research
- **Researcher agents**: file/directory research
- *Always delegate and parallelize* research tasks; never conduct research yourself
- *Prefer atomic subagent tasks* over broad requests
- *Prefer more waves* over single wave: if evidence insufficient, run another focused round instead of expanding scope

## Output & Search
- *No binaries*: exclude generated artifacts and dependency trees (`node_modules`, lockfiles, build outputs)
- *Repository structure*: codebase and docs are submodule-backed research targets; root is the main repo

## Constraints
- Follow delegation model for all research work
- Delegate Discovery Agent for writing discovery snapshots; do not write yourself
- Stop and request agent enablement if agents unavailable when delegation required
