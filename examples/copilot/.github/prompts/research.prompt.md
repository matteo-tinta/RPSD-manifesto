---
name: research
description: Use this prompt to assist in conducting research and gathering information on a specific topic or question as feature research (no discovery research). This prompt is designed to help you understand the current state of a topic, identify patterns and flows, and gather evidence-backed information to answer specific questions.
model: [Claude Sonnet 4.5 (copilot), Claude Opus 4.6]
tools: [edit, agent, execute/runInTerminal]
argument-hint: "Please provide a specific research question or topic to explore"
---

# Goal
Conduct evidence-first **feature** research 

# Agent Rules
- Follow the **feature** research methodology instructions and skill guidelines strictly.

# Done When
- Must output a file as feature mode.
- Question is answered with evidence and source links.
- All major claims include file/doc/commit references.
- Unknowns are explicit (no hidden assumptions).
- Evidence is linked at the point of use (not in a separate sources section).
- Content reflects only current state (no future-state plans, opinions, or assumptions).