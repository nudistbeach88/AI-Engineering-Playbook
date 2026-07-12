# Lessons

This ledger captures reusable engineering lessons from real projects. Each entry begins as evidence for review, not an automatic rule. Nathan decides whether a lesson is accepted into the Playbook, rejected, or superseded.

The entries below are illustrative Version 0.1 examples based on common AI engineering experiences.

## Lesson 001

- **Lesson Number:** 001
- **Date:** 2026-07-11
- **Project:** Example customer portal
- **Context:** An AI collaborator was asked to add account settings to an unfamiliar repository.
- **Observation:** The first proposal referenced a routing convention and component directory that did not exist.
- **Root Cause:** The prompt's assumptions were treated as repository facts before the codebase was inspected.
- **Recommendation:** Inspect structure, local instructions, dependencies, and nearby implementations before proposing an implementation plan.
- **Proposed Playbook Update:** Require a repository-state summary that separates verified facts from assumptions before implementation.
- **Status:** Accepted

## Lesson 002

- **Lesson Number:** 002
- **Date:** 2026-07-11
- **Project:** Example analytics dashboard
- **Context:** A dashboard feature compiled and passed unit tests but had not been opened in a browser.
- **Observation:** The delivered view overflowed on smaller screens and displayed an empty chart during loading.
- **Root Cause:** Static checks and isolated tests were mistaken for evidence of a successful user experience.
- **Recommendation:** Inspect the running interface at relevant viewport sizes and verify loading, empty, error, and success states.
- **Proposed Playbook Update:** Make rendered-reality verification a completion gate for user-facing milestones.
- **Status:** Accepted

## Lesson 003

- **Lesson Number:** 003
- **Date:** 2026-07-11
- **Project:** Example internal automation service
- **Context:** A small workflow change prompted a proposal for a new plugin framework and generalized event bus.
- **Observation:** The proposed architecture greatly expanded the change surface without serving another confirmed use case.
- **Root Cause:** Hypothetical future flexibility was valued above the current milestone and existing architecture.
- **Recommendation:** Implement the smallest coherent change and introduce abstractions only after repeated needs establish their shape.
- **Proposed Playbook Update:** Require every new abstraction to cite present consumers or demonstrated change pressure.
- **Status:** Proposed

## Lesson 004

- **Lesson Number:** 004
- **Date:** 2026-07-11
- **Project:** Example subscription application
- **Context:** An intermittent checkout failure was patched by adding retries before the failure path was traced.
- **Observation:** Retries reduced visible errors but created occasional duplicate requests and hid the actual timeout mismatch.
- **Root Cause:** A plausible symptom treatment was implemented without reproducing and diagnosing the failure.
- **Recommendation:** Establish the failure mechanism before patching; verify that the correction removes the root cause without introducing new behavior.
- **Proposed Playbook Update:** Require a written root-cause hypothesis for every defect before any code may be changed.
- **Status:** Rejected

The proposed update was rejected because a mandatory written artifact would be disproportionate for trivial defects. The underlying diagnose-before-patching recommendation remains valid.

## Lesson 005

- **Lesson Number:** 005
- **Date:** 2026-07-11
- **Project:** Example content platform
- **Context:** An unavailable design asset was silently replaced with a generic icon during implementation.
- **Observation:** The feature functioned, but the substitution changed the intended brand experience and was discovered only during review.
- **Root Cause:** The collaborator optimized for apparent completion instead of surfacing a missing dependency and its impact.
- **Recommendation:** Report missing inputs and obtain a decision before making substitutions that alter the requested outcome.
- **Proposed Playbook Update:** Add a separate substitution approval form for every missing asset.
- **Status:** Superseded

The proposed form was superseded by the leaner quality gate against silent substitutions in `.ai/QUALITY_GATES.md`.
