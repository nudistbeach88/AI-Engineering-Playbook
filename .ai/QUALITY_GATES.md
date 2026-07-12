# Quality Gates

These gates apply to future implementation prompts and completion reviews. A gate is satisfied by evidence, not assertion. If a gate is not applicable, state why; if it cannot be verified, report the uncertainty.

## Before Implementation

- [ ] Inspect the repository and relevant instructions; never invent repository state.
- [ ] Confirm interfaces and authoritative documentation; never invent APIs.
- [ ] Identify existing system boundaries; never invent architecture.
- [ ] Verify required files and media exist; never invent assets.
- [ ] Define the requested milestone and observable acceptance criteria.
- [ ] Record uncertainties that could materially change the solution.

## During Implementation

- [ ] Build only the requested milestone; reject unapproved scope expansion.
- [ ] Diagnose observed problems before applying speculative fixes.
- [ ] Protect working behavior, user data, and unrelated changes.
- [ ] Keep the change small, reviewable, and reversible.
- [ ] Do not silently replace, remove, or approximate requested functionality.
- [ ] Follow the established architecture unless evidence and approval justify a change.

## Verification

- [ ] Test behavior against acceptance criteria, not merely compilation.
- [ ] Verify rendered results for user-facing work.
- [ ] Distinguish internal implementation from the actual user experience.
- [ ] Exercise relevant failure states, boundaries, and regression risks.
- [ ] Base conclusions on inspected or observed evidence.

## Completion

- [ ] State what changed and what was intentionally left unchanged.
- [ ] Report verification performed and its results.
- [ ] State uncertainty, skipped checks, and limitations honestly.
- [ ] Do not claim success beyond the evidence available.
