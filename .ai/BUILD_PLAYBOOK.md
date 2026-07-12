# Nathan Build Playbook

Status: Version 0.1 foundation

This is the parent document for the methodology. It defines the durable frame; details should be added only when real engineering experience justifies them.

## Mission

Provide a reusable, evidence-led operating system for building maintainable software with AI. The playbook helps people and AI agents work from shared truth, make deliberate changes, and learn from completed projects.

## Engineering Philosophy

- Prefer systems over isolated prompts and architecture over hacks.
- Prefer truth over confidence and evidence over assumptions.
- Prefer clarity and maintainability over cleverness and novelty.
- Prefer the simplest design that meets the known need.
- Treat principles as defaults to examine, not dogma to obey blindly.

## Continuous Improvement Philosophy

The methodology evolves from observed outcomes. Capture lessons after real work, distinguish reusable patterns from local circumstances, and make small versioned changes. A new rule should name the failure or opportunity it addresses and the evidence behind it.

## Continuous Improvement Cycle

```text
Software Project
      ↓
Implementation
      ↓
Review
      ↓
Lessons Learned
      ↓
Playbook Updated
      ↓
Future Projects Improve
```

Every completed project should contribute evidence back into the Playbook. Reusable findings are recorded in `docs/LESSONS.md`, reviewed by Nathan, and incorporated only when they produce a justified improvement. Accepted changes then guide future projects, completing the learning cycle.

## Constitution First Development

Each project should define its non-negotiable product, engineering, security, and experience constraints before implementation. The constitution guides tradeoffs; it does not replace concrete requirements or acceptance criteria.

## Source of Truth Hierarchy

When sources disagree, resolve the conflict before building. Use this default order, adapted explicitly when a project requires it:

1. Verified behavior and current repository state
2. Approved project constitution and acceptance criteria
3. Current architecture and interface contracts
4. Project documentation and decisions
5. Task prompts and conversational context
6. Assumptions, conventions, and prior experience

Lower sources must not silently override higher ones. Record intentional exceptions.

## Repository Inspection Before Implementation

Inspect the actual repository before proposing changes: structure, instructions, working state, dependencies, tests, conventions, and nearby implementations. Summarize what is known, unknown, and potentially risky.

## Prompt Engineering Methodology

Prompts should communicate outcomes, constraints, relevant context, acceptance criteria, and required evidence. They should direct inspection rather than embed guesses about the repository. Reusable methodology belongs here; project facts belong in the project.

## Teaching Methodology

Technical teaching should create durable understanding, not merely simplify or compress information. Optimize for comprehension and retention rather than information density. Build an accurate mental model before introducing technical terminology.

This methodology applies to technical teaching, documentation, onboarding, and AI collaboration. It draws inspiration from communicators such as Bill Nye, whose use of clear analogies, storytelling, and progressively layered explanations made complex concepts memorable. It is not a general education framework; it is a practical protocol for engineering collaboration.

### The Bill Nye Protocol

When introducing an unfamiliar technical concept:

1. **Big Picture** — Explain what it is in one simple sentence.
2. **Why It Matters** — Explain why the learner should care and what problem it solves.
3. **Mental Model** — Give a memorable, accurate analogy before the technical definition so the learner can visualize the concept.
4. **What Is Happening Right Now?** — Use the mental model to explain exactly what the current step is doing.
5. **Risk** — Explain what could happen, including whether the action is reversible.
6. **Success Criteria** — Describe the observable successful outcome before performing the step.
7. **Execute** — Perform one step only; do not overload the learner.
8. **Reinforce** — Explain what happened and connect it back to the mental model.
9. **Connect** — Relate the concept to previously learned ideas, building an interconnected understanding rather than an isolated fact.

### Communication Principles

- Explain the purpose before the procedure.
- Explain the mental model before the terminology.
- Explain the expected outcome before the command.
- Never assume prior knowledge; establish what the learner already understands.
- Avoid unnecessary jargon, and define necessary terminology when introduced.
- Use concrete, accurate analogies whenever possible.
- Break large concepts into one-step learning increments.
- Favor understanding over memorization.

An explanation is successful when the learner can predict what will happen, recognize success or failure, and connect the new concept to the larger system—not merely repeat the terminology.

## Role Assignment Philosophy

Assign roles when specialization clarifies ownership or improves review. Define each role by responsibility, decision boundary, inputs, and expected evidence—not by theatrical persona. Keep coordination proportional to the work.

## Project Context Standards

Project context should identify the goal, users, current milestone, constraints, source-of-truth locations, architecture boundaries, commands for verification, and known uncertainties. Keep it current, concise, and close to the work.

## Architecture Principles

Start from user and system boundaries. Preserve separation of concerns, explicit interfaces, and understandable dependency direction. Avoid abstractions without demonstrated repetition or change pressure. Record consequential decisions and their tradeoffs.

## User Experience First Engineering

Implementation is successful only when the intended experience works for the user. Define the user journey and observable outcomes before choosing internal mechanisms. Include accessibility, failure states, latency, and recovery where relevant.

## Emotional Design Considerations

Software communicates through clarity, pacing, feedback, and tone. Decide what users should feel—such as confidence, control, or calm—and verify that the interface supports it. Emotional goals never justify deception or impaired usability.

## Hallucination Prevention

Do not present inferred repository state, APIs, assets, behavior, or results as fact. Inspect authoritative sources, label uncertainty, and ask or test when the uncertainty could change the solution.

## Evidence-Based Engineering

Match claims to evidence. Cite inspected code, observed behavior, test output, rendered results, measurements, or authoritative documentation. State the limits of the evidence.

## Inspect Before Editing

Read the target and its surrounding system before modifying it. Understand local conventions, consumers, dependencies, and existing uncommitted work. Preserve unrelated user changes.

## Diagnose Before Patching

For defects, reproduce the symptom when practical, trace the cause, and distinguish root cause from downstream effects. A patch should explain which diagnosis it addresses and how verification would catch a recurrence.

## Small Reversible Changes

Prefer the smallest coherent change that satisfies the milestone. Keep changes reviewable, isolate risky migrations, and provide a safe rollback path when impact warrants it.

## Preserve Working Systems

Do not rewrite stable components merely to align with preference. Protect compatibility and user data, assess regression risk, and expand scope only when evidence shows the existing system blocks the requested outcome.

## Acceptance Criteria

Define observable, testable completion conditions before implementation. Cover the primary user outcome, important constraints, failure behavior, and explicit exclusions. If criteria change, record the decision.

## Rendered Reality Verification

Source code and successful builds are intermediate evidence. For user-facing work, inspect the rendered or running result at relevant sizes and states. Verify content, layout, interaction, accessibility, errors, and loading behavior as applicable.

## Testing Philosophy

Use the least costly evidence that provides adequate confidence, then increase rigor with risk. Favor tests that protect behavior and boundaries over tests coupled to implementation detail. Include focused checks, relevant regression coverage, and real-environment verification when mocks cannot establish the outcome.

## Review Methodology

Review against intent, acceptance criteria, architecture, user experience, risk, and evidence. Prioritize correctness, security, data integrity, and regressions before style. Findings should be specific, reproducible, and proportionate.

## Completion Reporting

Report what changed, what was verified, the evidence obtained, known limitations, and any remaining decisions. Never convert partial verification into a claim of full success.

## Continuous Refinement Process

After meaningful project milestones:

1. Capture outcomes, surprises, failures, and effective practices.
2. Separate project-specific facts from reusable lessons.
3. Propose the smallest playbook change with supporting evidence.
4. Review for contradiction, duplication, and unnecessary rigidity.
5. Version the accepted change and observe it in later work.

Future versions may deepen these sections, but only where use has exposed a real gap.
