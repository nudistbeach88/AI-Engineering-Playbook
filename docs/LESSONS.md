# Lessons

This ledger captures reusable engineering lessons from real projects. Each entry begins as evidence for review, not an automatic rule. Nathan is the final decision-maker for every lesson.

Version 0.1.0 included illustrative entries to demonstrate the format. They were not real project evidence and have been removed from the active ledger in Version 0.2.0; their former status labels must not be interpreted as engineering history. No real project lessons are currently recorded.

## Lesson Structure

- **Lesson Number:** Sequential identifier
- **Date:** Date recorded
- **Project:** Project in which the lesson was observed
- **Context:** Relevant circumstances
- **Observation:** What happened
- **Root Cause:** Why it happened, when known
- **Evidence (optional):** A commit, issue, test result, review, local document, retrospective, external source, or a clear statement that recoverable evidence is unavailable
- **Recommendation:** Reusable response to the lesson
- **Proposed Playbook Update:** Smallest methodology change proposed
- **Status:** Proposed, Accepted, Rejected, or Superseded

## Status Definitions

- **Proposed:** The lesson is awaiting Nathan's review and decision.
- **Accepted:** The recommendation has been approved for incorporation into the methodology.
- **Rejected:** The lesson was reviewed and declined.
- **Superseded:** The lesson or recommendation was replaced by a later decision.

Acceptance does not itself implement a lesson. Implementation is recorded through changes to the relevant documents and an entry in `docs/CHANGELOG.md`; additional implementation statuses are unnecessary.
