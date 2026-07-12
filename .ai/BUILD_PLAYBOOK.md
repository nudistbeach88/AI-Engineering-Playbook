# AI Engineering Playbook: Build Methodology

Status: Version 0.2.1

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

The methodology evolves because real engineering work reveals gaps, exceptions, and better practices that theory alone cannot predict. Improvements should come from observed outcomes, generalize beyond one project, and remain small enough to evaluate and reverse.

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

Every completed project should contribute evidence back into the Playbook. Review turns project outcomes into reusable findings recorded in `docs/LESSONS.md`; accepted improvements then guide future projects and complete the learning cycle.

## Constitution First Development

Serious or durable projects should define their non-negotiable product, engineering, security, and experience constraints before implementation. The formality of the constitution should scale with project duration, risk, complexity, number of collaborators, and expected longevity. A disposable experiment does not require the ceremony of a long-lived product, but important constraints and intended outcomes must still be explicit. The constitution guides tradeoffs; it does not replace concrete requirements or acceptance criteria.

## Source of Truth Model

Two kinds of truth guide engineering work:

**Descriptive truth** is verified evidence of what currently exists or happens: repository state, rendered behavior, tests, logs, runtime output, and environment state. It cannot be ignored or replaced by assumption.

**Normative authority** defines the approved direction for what should exist or happen: the project constitution, approved requirements, acceptance criteria, architecture decisions, and approved milestone documentation. Current implementation cannot override that direction merely by being different.

A verified defect is evidence of current reality, not proof of desired behavior. Conflict between descriptive truth and normative authority should trigger diagnosis and implementation work. Conversation context and assumptions must never override verified repository evidence or approved project authority; unresolved conflicts should be surfaced before proceeding.

## Repository Inspection Before Implementation

Inspect the actual repository before proposing changes: structure, instructions, working state, dependencies, tests, conventions, and nearby implementations. Summarize what is known, unknown, and potentially risky.

## Prompt Engineering Methodology

Prompts should communicate outcomes, constraints, relevant context, acceptance criteria, and required evidence. They should direct inspection rather than embed guesses about the repository. Reusable methodology belongs here; project facts belong in the project.

## Communication & Teaching Methodology

The Playbook should teach engineering, not merely report engineering. Communication should maximize durable understanding, retention, engineering intuition, and long-term judgment rather than information density. Never assume prior knowledge, but do not simplify by removing important concepts; simplify by introducing them in the right order. The goal is an accurate mental model, not memorized terminology or commands.

This methodology is inspired by communicators such as Bill Nye, whose clear analogies, storytelling, and progressively layered explanations made complex concepts memorable. It applies to repository walkthroughs, architecture and implementation reviews, planning, prompting, debugging, Git and DevOps explanations, onboarding, documentation, code explanations, system design, and AI collaboration—not only beginner tutorials.

### Mental Model First

Build understanding before terminology. Explain purpose before procedure, concepts before commands, expected outcomes before execution, and risks before action. When appropriate, use this sequence:

1. **Big Picture** — State what is being done in one simple sentence.
2. **Purpose** — Explain the problem it solves, why it matters, and why the learner should care.
3. **Mental Model** — Introduce a memorable analogy before technical definitions without sacrificing accuracy.
4. **Current Action** — Explain exactly what the current step is doing through the mental model.
5. **Risk** — Explain what could happen, whether it is reversible, and whether concern is warranted.
6. **Success Criteria** — Describe the observable successful outcome before execution.
7. **Execute** — Perform one meaningful step at a time. Use progressive disclosure and add complexity only after understanding is established.
8. **Reinforce** — Explain what happened and reconnect it to the original mental model.
9. **Connect** — Relate the concept to previously learned ideas so understanding forms a connected system rather than isolated facts.

Useful analogies might describe a repository as a notebook, Git as the notebook's memory, GitHub as a fireproof vault, a commit as a photograph, a branch as an alternate timeline, an API as a waiter, a database as a library, or a build pipeline as an assembly line. These examples are illustrative, not prescriptive; choose analogies that improve understanding without distorting the engineering reality.

### Communication Principles

- Never assume prior knowledge; establish what the learner already understands.
- Avoid unnecessary jargon and define necessary terminology when it becomes useful.
- Favor memorable, technically accurate analogies.
- Teach progressively and avoid unnecessary cognitive overload.
- Ensure the learner understands why something exists before explaining how to use it.

### Engineering Reviews

When appropriate, present reviews in this order: Big Picture, Purpose, Mental Model, What Changed, Why It Changed, Risks, Expected Outcome, Implementation Summary, Verification, Lessons Learned, and Next Recommendation. The objective is for Nathan to understand the engineering decision and its consequences, not merely receive an implementation report.

Communication succeeds when the learner can explain why the concept exists, predict what will happen, recognize success or failure, connect it to the larger system, and make better future decisions.

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
2. Separate project-specific facts from reusable lessons and retain recoverable evidence when available.
3. Submit the lesson for Nathan's decision; acceptance approves the recommendation for incorporation but does not itself implement it.
4. Apply the smallest approved playbook change and review it for contradiction, duplication, and unnecessary rigidity.
5. Record the implementation in the changelog, version the release, and evaluate the result in later work.

Future versions may deepen these sections, but only where use has exposed a real gap.
