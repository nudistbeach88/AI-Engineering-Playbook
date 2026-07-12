# AI Engineering Anti-Patterns

This living catalog names recurring failure modes so they can be recognized and prevented. Add entries only when experience reveals a reusable pattern; include context and evidence when expanding the catalog.

## Hallucinating Repository State

**Failure:** Describing files, dependencies, behavior, or conventions that were not inspected.

**Countermeasure:** Inspect first, separate observation from inference, and state what remains unknown.

## Feature Creep and Scope Expansion

**Failure:** Adding adjacent features, cleanup, or infrastructure beyond the agreed milestone.

**Countermeasure:** Tie each change to an acceptance criterion and defer unrelated opportunities explicitly.

## Premature Abstraction

**Failure:** Creating generalized layers before repetition or change pressure is understood.

**Countermeasure:** Implement the simplest clear solution and extract abstractions from demonstrated patterns.

## Overengineering

**Failure:** Introducing complexity, configuration, or coordination disproportionate to the current problem.

**Countermeasure:** Choose the least complex design that satisfies current constraints and preserves a credible evolution path.

## Unverified Claims

**Failure:** Declaring correctness, completion, performance, or visual quality without relevant evidence.

**Countermeasure:** Report the exact checks performed, their results, and their limits.

## Speculative Fixes

**Failure:** Patching a plausible symptom without reproducing or tracing the underlying cause.

**Countermeasure:** Diagnose first and verify that the fix addresses both the cause and the observed behavior.

## Silent Substitutions

**Failure:** Replacing requested functionality, assets, dependencies, or behavior without disclosure and agreement.

**Countermeasure:** Surface the constraint and tradeoff; obtain a decision when the substitution changes the outcome.

## Cargo Cult Architecture

**Failure:** Copying patterns because they are fashionable or familiar rather than because this system needs them.

**Countermeasure:** Connect architectural choices to concrete forces, constraints, and measured tradeoffs.

## Breaking Working Code Unnecessarily

**Failure:** Rewriting stable systems or broadening a change surface without evidence that it is required.

**Countermeasure:** Preserve existing behavior, make focused edits, and test likely regressions.

## Compilation-as-Completion

**Failure:** Treating a successful build or type check as proof that the user outcome works.

**Countermeasure:** Test behavior and inspect rendered reality in addition to static checks.

## Prompt-as-Source-of-Truth

**Failure:** Letting prompt wording override verified repository behavior or approved project decisions.

**Countermeasure:** Resolve conflicts using the source-of-truth hierarchy and record intentional changes.

## Dogmatic Methodology

**Failure:** Applying a playbook rule when context or evidence shows it harms the project.

**Countermeasure:** Treat rules as revisable defaults, document justified exceptions, and feed the lesson back into the playbook.
