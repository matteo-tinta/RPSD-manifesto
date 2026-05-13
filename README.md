# RPSD Manifesto

**Research. Plan. Spike. Develop.**

RPSD is a human-gated agentic development pattern that front-loads reasoning before code is written.

We do not ask an agent to discover, decide, validate, and implement in one continuous flow.

Instead, we split work into isolated phases, each producing durable artifacts that can be reviewed, corrected, reused, or discarded.

## Core Beliefs

- **The chat is disposable. The artifact is durable.**
- **Reasoning should happen before implementation.**
- **Implementation should be plan-bound, not exploratory.**
- **Research produces findings, not ready-made plans.**
- **Plans convert research into executable change.**
- **Spikes answer technical insecurity with code.**
- **If a spike does not need a POC, it is not a spike.**
- **Humans remain the gatekeepers between phases.**
- **Reviewed artifacts are temporary sources of truth.**
- **Agents may propose, but humans approve.**

## The Flow

### 1. Research

Research investigates the codebase, docs, git history, APIs, and existing patterns.

Research has two modes:

#### Feature Research

Feature research supports a possible change.

It produces findings, constraints, risks, relevant files, prior art, and possible approaches.

Output:

`features/<feature>/research.md`

Feature research informs planning, but it is not itself an implementation plan.

#### Discovery Research

Discovery research captures reusable knowledge about the codebase.

It documents stable patterns, conventions, architecture, and implementation rules.

Output:

`discovery/<topic>.md`

Discovery research does not require a plan. Its purpose is learning and future reuse.

### 2. Plan

Planning turns reviewed research, discovery knowledge, and user intent into an implementation plan.

The planner is allowed to challenge the research.

Research is input, not authority.

The plan must define:

- tasks;
- dependencies;
- blockers;
- files to change;
- tests;
- DODs;
- risks;
- open questions.

Output:

`features/<feature>/plan.md`

The plan is done only when open points are resolved or explicitly accepted by the human.

### 3. Spike

A spike validates one specific technical uncertainty.

A spike must be falsifiable and must produce code.

Output:

`features/<feature>/spikes/<spike>/`

A spike answers:

- what was uncertain;
- what was built;
- what was observed;
- whether the plan must change.

If no POC is needed, the task is not a spike. It should return to Research or Plan refinement.

### 4. Develop

Development applies the approved plan to the codebase.

This phase is intentionally constrained.

The implementation agent should not redesign, re-research, or reinterpret the feature.

It should:

- follow the plan;
- implement task by task;
- satisfy DODs;
- run checks where possible;
- report deviations;
- stop when the plan is wrong.

Output:

- code changes;
- implementation report;
- test results or validation notes.

Development is allowed to discover that the plan is invalid, but it must not silently replace the plan.

## Principle: Front-Loaded Intelligence

RPSD puts the most capable reasoning models in Research, Plan, and Spike.

Implementation is the final translation of an approved decision into code.

The goal is not autonomous coding, but controlled delivery.

## Principle: Artifact Authority

Only reviewed artifacts carry authority.

Private chat reasoning, hidden agent memory, and unreviewed assumptions do not carry forward.

Each phase consumes explicit artifacts, not vibes.

## Principle: Human Gatekeeping

A phase does not advance because the agent completed output.

A phase advances only when the human reviews and accepts the artifact.

## Anti-Patterns

RPSD avoids:

- researching while implementing;
- planning while coding;
- spiking without a falsifiable question;
- using spikes as vague exploration;
- treating research suggestions as final decisions;
- allowing implementation agents to redesign;
- relying on hidden chat context;
- letting polished artifacts hide weak evidence.