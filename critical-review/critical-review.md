---
name: critical-review
description: Enforce a structured critical review process on any multi-step task. Before executing each major phase of work, identify assumptions, question decisions, evaluate alternatives, and assess risks — then provide a reasoned recommendation and proceed. Use this skill whenever the user asks to "review phases", "question the approach", "challenge each step", "do a critical review", "metti in discussione", or when working on any non-trivial task where phase-by-phase validation adds value. Triggers on any task that involves planning, coding, analysis, writing, design, or strategy where the user wants each phase scrutinized before moving forward.
---

# Critical Review Skill

Apply a rigorous, phase-by-phase critical review to any task. For each major phase, challenge assumptions, surface risks, explore alternatives, and provide a clear recommendation — then proceed unless the user intervenes.

## Workflow

### Step 1: Decompose the Task into Phases

At the start of any task, identify and list the **main phases** required to complete it. Present them to the user as a numbered list:

```
This task has N main phases:
1. [Phase name] — [one-line description]
2. [Phase name] — [one-line description]
...
```

### Step 2: Critical Review per Phase

Before executing each phase, perform a **complete review** covering all of the following dimensions. Do not skip any dimension — address each one explicitly, even if briefly.

#### Review Dimensions

| # | Dimension | Key questions |
|---|-----------|---------------|
| 1 | **Assumptions** | What are we taking for granted? Are these assumptions valid? What happens if they are wrong? |
| 2 | **Alternatives** | What other approaches exist? Why is this one preferable? What are the trade-offs of each? |
| 3 | **Risks** | What can go wrong? What is the probability and impact? How can we mitigate? |
| 4 | **Dependencies** | What does this phase depend on? What depends on this phase? Are there circular or fragile dependencies? |
| 5 | **Cost / Effort** | Is this phase proportionate to the value it delivers? Is there a simpler way? |
| 6 | **Scalability** | Will this approach hold up at scale? What are the limits? |
| 7 | **Maintainability** | Will this be easy to understand and modify later? Are we creating technical debt? |
| 8 | **Edge cases** | What unusual inputs, states, or conditions could break this? |
| 9 | **Alignment** | Does this phase align with the overall goal? Could it conflict with other phases? |

#### Review Output Format

For each phase, present the review as:

```
## Phase N: [Name]

### Critical Review

**Assumptions:**
- [assumption 1] — [valid/risky/needs verification] — [explanation]
- ...

**Alternatives considered:**
- [alternative A] — [pros] — [cons]
- [alternative B] — [pros] — [cons]
- **Chosen approach:** [which and why]

**Risks:**
- [risk 1] — Probability: [low/medium/high] — Impact: [low/medium/high] — Mitigation: [action]
- ...

**Dependencies:** [list]

**Cost / Effort:** [assessment]

**Scalability:** [assessment]

**Maintainability:** [assessment]

**Edge cases:** [list with handling strategy]

**Alignment check:** [confirmation or concern]

### Recommendation
[Clear statement of the recommended approach with reasoning]

### Proceeding with Phase N...
[Execute the phase]
```

### Step 3: Execute the Phase

After presenting the review and recommendation, **proceed with execution** of the phase. The user can interrupt at any point to redirect, ask deeper questions, or override the recommendation.

If the user provides feedback or raises concerns, address them fully before continuing.

### Step 4: Transition to Next Phase

After completing a phase, briefly summarize what was done, then move to the critical review of the next phase. Repeat Steps 2-3 for each phase.

### Step 5: Final Summary

After all phases are complete, provide a closing summary:

```
## Review Summary

| Phase | Key Decision | Risk Level | Notes |
|-------|-------------|------------|-------|
| 1. [name] | [what was decided] | [low/med/high] | [any flag] |
| ...   | ...         | ...        | ...   |

**Open concerns:** [any unresolved risks or items to revisit]
**Overall confidence:** [high/medium/low with reasoning]
```

## Guidelines

- Communicate in the user's language
- Be honest and direct — flag real concerns, do not sugarcoat
- When a dimension has no concerns, state it briefly (e.g., "Scalability: not applicable for this task") rather than padding
- Prioritize the most critical dimensions for each phase — spend more words on dimensions that matter most for that specific phase
- If a phase is trivial, compress the review into 2-3 sentences covering only the relevant dimensions
- Do not slow down work unnecessarily — the review should add value, not bureaucracy
- Adapt depth to complexity: simple phases get lighter review, complex/risky phases get deeper analysis
