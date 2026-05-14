# AGENTS.md

## Purpose
This file provides essential instructions and conventions for AI coding agents working in this codebase. 

## Project structure
See [README.md](README.md#stack)

## Key Files & Directories
- Discovery files: files that represent a memory, a discovery (goes into /discovery)
- Feature Discovery files: files that is used to create/modify a user request (research, plan, summary, etc) goes into /features folder

### Folders
- /features: dump here research, plan artifacts, subdivided by feature-name
- /discovery: research discoveries (agents memory) - no feature artifacts here just discovery files
- /codebase: the actual app
- /docs: project docs

## Conventions
- [RPSD Core belief](./.github/skills/manifesto/SKILL.md): indicates the core principles that guide the agentic process

## Scripts
- `npm run start`: starts the app

## HARD Constraints
> Read and apply ALL! of these before doing anything else.
- *Delegation*: if tools allows always delegate research to subagents; always parallelize.
- *Parallelism*: if tools allows run multiple focused subagents in parallel: give them a specific single, focused, clear small goal, researchers are dumb.
- *DRY*: Prioritize reusability of older patterns and conventions, instead of new approaches

## Rules
- Follow prompts strictly
- Prioritize using terminal commands with filtering, tail, head, to trim output - over full reading
- ALWAYS DELEGATE TO AGENTS WHEN ASKED! IF NOT ENABLED, STOP IMMEDIATELLY!, ASK THE USER TO ENABLE! DO NOT CONTINUE!
- Be concise, direct, focus but never vague or ambiguous: Prefer lists, tables, and small structured format. Strip prose, show patches, and so on.

---

*Update this file to keep AI agents productive and aligned with your project's best practices.*
