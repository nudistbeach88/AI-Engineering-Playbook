# Core Intelligence Architecture

This pattern describes how an AI system can move from storing records to building an explainable, continuously improving understanding of a domain. It is domain-neutral and optional: adopt only the capabilities justified by the product, its evidence, and its risk.

The architecture is a conceptual model, not a required service topology. A small system may implement several capabilities in one module; a mature system may separate them behind explicit interfaces.

## Mental Model

Think of the system as an intelligence dossier with a chain of custody.

Raw observations enter from known sources. The system resolves them into canonical entities, records which evidence supports each claim, derives conclusions, and shows why those conclusions are credible. Human decisions become durable learning events. Those events improve the system's future understanding without erasing how it reached the earlier state.

The goal is not to make AI output look authoritative. The goal is to make knowledge inspectable, uncertainty actionable, and improvement observable.

## Reference Flow

```text
Acquisition
    ↓
Raw Observations and Sources
    ↓
Canonical Entities
    ↓
Evidence and Claims
    ↓
Relationships
    ↓
Reasoning and Conclusions
    ↓
Confidence
    ↓
Operator Decisions
    ↓
Learning and Audit Events
    ↓
Intelligence Completeness
    ↓
Work Queue and Recommendations
    ↓
Knowledge Graph and Dossiers
```

This flow is iterative rather than strictly linear. New evidence may revise an entity, relationship, conclusion, task, or recommendation. Every material revision should remain traceable.

## Capability Boundaries

### 1. Acquisition

Collectors or source adapters capture observations without deciding what becomes canonical truth. Preserve the original content, source identity, collection time, and relevant source metadata so later conclusions can be reproduced or challenged.

### 2. Canonical Entities

Canonical entities provide stable identities for the things the system understands. Normalization and entity resolution may merge multiple observations, aliases, or identifiers while preserving their provenance.

Do not force uncertain observations into an invented taxonomy. Model the narrowest concept supported by evidence, retain ambiguity when necessary, and allow classifications to evolve.

### 3. Evidence and Claims

A claim is a specific assertion about an entity or relationship. Evidence links the claim to one or more observations, operator decisions, or trusted systems.

For every material claim, retain:

- supporting and contradicting evidence;
- source identity, reliability, and freshness;
- whether the claim is observed, verified, inferred, contradicted, or unknown;
- the method and time of its latest evaluation.

Conclusions must not silently replace their evidence.

### 4. Relationships

Relationships are first-class records, not unexplained links embedded in presentation code. Record the relationship type, participants, evidence, confidence, validity period when relevant, and how it was created or verified.

### 5. Reasoning and Conclusions

Reasoning transforms evidence into decision-relevant conclusions. Store a concise, inspectable rationale: the observations considered, the interpretation applied, the inference produced, important contradictions, and the recommended response.

Do not expose or depend on private model chain-of-thought. The durable artifact is an evidence-backed explanation that another engineer or operator can inspect and evaluate.

### 6. Confidence

Confidence answers: **How certain is the system that this conclusion is correct?**

Confidence should be derived from named factors such as source agreement, reliability, freshness, verification, contradiction, and model or rule performance. A score without its factors is confidence theater.

### 7. Operator Decisions

When ambiguity, risk, or product policy requires human judgment, present a structured decision rather than a passive warning. Show the evidence, alternatives, expected impact, and a safe reversal path when practical.

Material operator actions should create durable decision and audit events. Do not silently mutate the canonical record and discard the previous state.

### 8. Learning and Audit Events

Learning means the system visibly incorporates new evidence or approved feedback into later state. It does not necessarily mean online model training.

Record append-only events for material changes such as verification, correction, merge, split, relationship change, recommendation resolution, and confidence revision. Recompute affected conclusions through explicit rules or services, and preserve enough history to explain what changed and why.

### 9. Intelligence Completeness

Intelligence completeness answers: **How much does the system understand about this entity?**

It is distinct from confidence. A system can be highly confident about a small amount of information while still understanding very little overall.

Completeness may consider evidence coverage, relationship coverage, verification, history, source diversity, freshness, and operator validation. Dimensions must reflect meaningful domain knowledge rather than a raw count of populated fields.

### 10. Work Queue and Recommendations

Unknowns, contradictions, and weak evidence should become prioritized work. Recommendations should explain:

- the evidence gap or risk;
- why action matters;
- expected impact on confidence, completeness, health, or downstream decisions;
- dependencies, reversibility, and required authority.

Completing work should update the same canonical intelligence model rather than a parallel task-only state.

### 11. Knowledge Graph and Dossiers

Knowledge graphs and dossiers are delivery views over canonical entities, claims, evidence, relationships, decisions, and history. They should not become separate sources of truth.

A dossier summarizes current understanding and uncertainty. A graph supports exploration of entities and evidence. Both must link back to provenance.

## Core Data Contracts

Names may vary by project, but durable implementations usually need explicit representations for:

- **Source:** where information originated and how it was collected;
- **Observation:** immutable or versioned raw input;
- **Entity:** canonical identity and current approved state;
- **Claim:** a specific assertion about an entity or relationship;
- **Evidence Link:** support or contradiction connecting a claim to its provenance;
- **Relationship:** a typed, evidenced connection between entities;
- **Conclusion:** a derived interpretation with an inspectable rationale;
- **Decision:** an authorized human or system judgment;
- **Learning Event:** an append-only record of a material change in understanding;
- **Intelligence Task:** prioritized work generated by a gap, conflict, or opportunity;
- **Dossier:** a generated view of current intelligence, not an independent record.

These are conceptual contracts. Do not create a microservice for each noun unless deployment, ownership, scale, or reliability requirements justify it.

## Engineering Principles

1. **Canonical entities over duplicated records.** Resolve identity while retaining every source observation and alias.
2. **Evidence before conclusions.** Every material AI conclusion should be inspectable through its supporting and contradicting evidence.
3. **Explain confidence.** Show the factors that raised or lowered certainty; never present an unexplained score as truth.
4. **Separate certainty from completeness.** Confidence measures how sure the system is; completeness measures how much it understands.
5. **Surface unknowns.** Missing, stale, weak, and contradictory information should remain visible and actionable.
6. **Human judgment changes the system.** Approved corrections should update affected reasoning, confidence, recommendations, and history.
7. **Preserve an audit trail.** Material decisions and intelligence changes should be durable, attributable, and reversible when practical.
8. **Explain recommendations.** State why an action matters, what evidence supports it, and what impact is expected.
9. **Do not invent concepts before evidence justifies them.** Let stable patterns emerge before hardening taxonomies or abstractions.
10. **Treat intelligence as continuous.** Understanding evolves as sources, relationships, feedback, and time change.
11. **Keep simulation honest.** Mocked scores and local-only state can validate interaction design, but they are not production intelligence services.
12. **Automate proportionally to risk.** Higher autonomy requires stronger evaluation, permissions, observability, recovery, and human override.

## Capability Maturity Model

The maturity model is a planning aid, not a compliance score. A product should stop at the level that serves its actual need and risk profile.

### Level 0: Data Storage

The system stores source data or documents. Retrieval may exist, but identity, provenance, and structure are limited.

### Level 1: Structured Records

The system normalizes observations into defined records with stable identifiers and validation. Provenance is retained.

### Level 2: Relationships

The system resolves canonical entities and records evidenced relationships between them. Users can navigate connected information without losing source context.

### Level 3: Explainable Intelligence

The system derives conclusions, confidence, and recommendations from evidence. Operators can inspect support, contradictions, uncertainty, and rationale.

### Level 4: Human-in-the-Loop Learning

Structured operator decisions create durable learning events. Corrections visibly update affected conclusions, confidence, completeness, health, tasks, and history.

### Level 5: Autonomous Recommendations

The system prioritizes and may execute bounded next actions under explicit policy. Recommendations remain evidence-backed, monitored, reversible where practical, and subject to human approval when risk, authority, or uncertainty requires it.

Do not claim a level because the interface simulates it. Maturity is established by real data flow, persistence, verification, auditability, and observed behavior.

## Adoption Guidance

Before adopting this architecture:

1. Identify the real decisions the product must improve.
2. Define the authoritative sources and evidence boundaries.
3. Start with one end-to-end vertical slice from acquisition to an observable outcome.
4. Separate simulated interactions from production capabilities in documentation and reporting.
5. Establish persistence, provenance, and audit history before claiming learning.
6. Evaluate confidence and recommendations against real outcomes.
7. Add autonomy only after permissions, failure modes, rollback, and monitoring are explicit.

Success is not the number of services, scores, graphs, or AI summaries created. Success is whether the system helps people make better decisions while making its evidence, uncertainty, and evolution understandable.
