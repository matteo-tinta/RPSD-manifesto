---
name: "planning"
description: Use this skill for creating an implementation plan for a specific user request using the given template. This skill provides guidelines and best practices for creating a comprehensive and actionable plan for implementing a task in the codebase. More instructions may be added in the project.
user-invocable: false
---

# Goal
- *plan.md*: executable, testable `plan.md` file, as for templates.
- *plan.summary.md*: concise senior-level task recap with links to plan tasks, as for templates.

# Done When
- *Open points*: all resolved.
- *Dependencies/blockers*: clearly identified.
- *Tasks*: each includes DOD and tests.

# Templates
> inside resources/templates folder

- *Header*: task scope, status, open points, dependencies, guardrails. Reference: templates/plan.header.template.md
- *Task*: status, description, files, tests, DOD, QA checklist. Reference: templates/plan.task.template.md
- *Summary*: concise senior-level task recap with links to plan tasks. Reference: templates/plan.summary.template.md

# Rules
- *Length*: try keeping plan.md under 200 lines.
- *Atomicity*: keep tasks small and manageable.
- *No duplication*: do not repeat AGENTS.md or README.md content.
- *Compatibility*: prefer non-breaking changes; document breaking changes explicitly.

# Patterns and Principles
- *KISS*: keep it simple and straightforward. Avoid unnecessary complexity or over-engineering.
- *DRY (in patterns)*: reuse existing patterns and abstractions in the codebase. Avoid creating new ones unless necessary.
- *SOLID*: follow solid principles for object-oriented design, especially SRP and OCP.

> SRP (Single Responsibility Principle): a component should have only one reason to change, meaning it should be linked to one and just one actor.

# Skill Workflow
1. *Analysis*: challenge gaps, ambiguities, inconsistencies, and weak assumptions.
2. *Document open points*: record all open points in the plan header.
3. *Draft plan.md*: write using templates.
   - *Blocked rule*: if open points exist, set status to DRAFT_BLOCKED.
   - *Readiness rule*: never mark blocked tasks as READY.
   - *User action*: request user resolution of open points.
   - *Loop rule*: if open points remain, stop and resume from step 2 after resolution.
4. *Write plan.summary.md*: using summary template.
   - *Summary limit*: max 3 lines per task recap.
   - *Summary links*: link each item to its task in plan.md.
5. *End*: both files complete.

# Agent Guidance
- *Discovery order*: local discovery/docs first, then git history, then broader research.
- *Contract priority*: API contract discovery (swaggers, OpenAPI specs, etc) before historical/code inferring pattern discovery.
- *Consistency*: align plan with relevant existing patches and codebase patterns.
