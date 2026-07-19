# AI Engineering Playbook

The AI Engineering Playbook is a living engineering operating system for building software with AI. It captures reusable methods—not project-specific prompts—so future projects can begin with a shared standard for truth, architecture, quality, and verification.

Nathan owns and curates the methodology, and the `AI-Engineering-Playbook` repository is its canonical source of truth. AI models are collaborators that help inspect, implement, critique, and refine the system; they do not own the methodology or determine its direction.

The playbook starts intentionally small. Evidence from real projects drives its evolution: lessons are captured, reviewed, generalized only when useful, and added through small versioned changes.

Future projects should adopt `.ai/BUILD_PLAYBOOK.md` as the parent methodology and reference `.ai/QUALITY_GATES.md` in implementation work. Project-specific constitutions and requirements remain local to each project; improvements that prove broadly useful flow back here.

This repo also anchors the shared skill topology: one company-wide skill base plus one private overlay per Prime/ally. The same shared layer should be reflected in Obsidian, Notion, GitHub, Claude, Codex, Claw / OpenClaw, and Hermes.

Start with the [build methodology](.ai/BUILD_PLAYBOOK.md). For evidence-driven AI systems, use the [Core Intelligence Architecture](.ai/CORE_INTELLIGENCE_ARCHITECTURE.md) as an optional domain-neutral reference pattern. Use the [quality gates](.ai/QUALITY_GATES.md) and [anti-pattern catalog](.ai/ANTI_PATTERNS.md) during planning, implementation, and review. Record reusable findings in the [lessons ledger](docs/LESSONS.md), track direction in the [roadmap](docs/ROADMAP.md), and review release history in the [changelog](docs/CHANGELOG.md).

## Index

- [Build Methodology](.ai/BUILD_PLAYBOOK.md)
- [Core Intelligence Architecture](.ai/CORE_INTELLIGENCE_ARCHITECTURE.md)
- [Quality Gates](.ai/QUALITY_GATES.md)
- [Anti-Pattern Catalog](.ai/ANTI_PATTERNS.md)
- [Lessons Ledger](docs/LESSONS.md)
- [Roadmap](docs/ROADMAP.md)
- [Changelog](docs/CHANGELOG.md)
- [Shared Skill Topology](docs/SHARED_SKILL_TOPOLOGY.md)

---

## Visible Craft

Meaningful waiting states are part of the product experience, not dead time.

Whenever a product is analyzing, organizing, generating, searching, transforming, or building, the interface should make the user feel that skilled work is taking place.

The governing metaphor is a master craftsperson who says, “One moment, please,” steps behind the counter, and begins working. The user may only see a silhouette and catch brief glimpses of the process, but they should be able to see, hear, and feel the machinery of careful work.

A successful processing experience communicates three things:

1. **Competence:** the system knows what it is doing.
2. **Intention:** the work is being handled carefully rather than rushed.
3. **Inevitability:** the result is progressing toward a worthwhile completion.

### Core rule

Never ship a raw loading state for meaningful work.

Generic spinners, sterile progress bars, and implementation language such as `Processing...` or `0 of 200` should be replaced by a designed processing experience that reinforces trust and communicates progress in human terms.

### The Workshop System

Different classes of work may use different craft metaphors while sharing the same reusable component system:

- **The Tailor:** categorization, organization, inbox management, and refinement
- **The Librarian:** search, memory, retrieval, and knowledge work
- **The Cartographer:** planning, strategy, roadmaps, and navigation
- **The Blacksmith:** code generation, system construction, and automation
- **The Calligrapher:** writing, editing, and communication
- **The Alchemist:** research, synthesis, testing, and experimentation
- **The Watchmaker:** debugging, diagnosis, precision repair, and optimization

These metaphors guide the emotional tone. They should not become distracting, theatrical, or gimmicky.

### Processing language

Progress copy should describe the work in clear human language.

Prefer:

- Taking a careful look...
- Studying your inbox...
- Looking for patterns...
- Organizing with intention...
- Choosing the right place for each sender...
- Checking the final details...
- Almost finished...

Avoid exposing low-level implementation details unless they are genuinely useful to the user.

### Multi-sensory standard

**Visual:** Use slow, confident motion, silhouettes, frosted-glass glimpses, objects moving into order, or other restrained signs of work. Confidence moves slowly; anxiety moves quickly.

**Sound:** When appropriate and optional, use quiet material and workshop sounds such as paper, wood, fabric, pens, mechanical clicks, drawers, tools, or sorting mechanisms. Avoid default futuristic beeps and loud science-fiction effects.

**Haptics:** On supported devices, use subtle breathing-like pulses during longer operations and one clean confirmation pulse at completion. Haptics must remain optional, soothing, and easy to disable.

**Copy:** Narrate meaningful stages of the work. Never fabricate progress or claim a stage has completed unless the system can verify it.

### Universal processing component

Build the pattern once, then apply it across meaningful AI operations, including:

- Categorization
- Search and retrieval
- Brief generation
- Reply drafting
- Report generation
- Planning
- Research
- Code generation
- Analysis
- Data transformation

The component should support:

- Task-specific workshop themes
- Honest stage updates
- Determinate or indeterminate progress
- Reduced-motion behavior
- Optional sound
- Optional haptics
- Cancellation when safe
- Error recovery
- A distinct completion state

### Product principle

**Let users witness craftsmanship rather than computation.**

The purpose is not merely to entertain users while they wait. The waiting experience itself should deepen trust, clarify that meaningful work is underway, and make the final result feel intentionally made.

### Origin

This principle was defined by Nathan for Cyberpunk Augmented Labs on July 14, 2026 and was first recorded in the CAL Brand & Design System in Notion by Shinzo, ChatGPT.

---

## Living Data Visualization

### Philosophy

Data should not simply appear.

Data should tell its story.

Every visualization should answer three questions before the user consciously reads the numbers:

1. Where am I now?
2. How did I get here?
3. Which direction am I moving?

Motion is not decoration.

Motion is information.

Animations should exist to improve comprehension, reinforce trust, and communicate change.

### The Living Data Principle

Static dashboards feel like screenshots.

Living dashboards feel connected to real systems.

Charts should feel as though they are actively reconstructing history, not simply displaying a final state.

The user should immediately understand trends through motion rather than needing to interpret numbers.

### Animation Hierarchy

#### Level 1, Static Display

Shows only the current value.

Example:

72%

Useful, but provides no context.

#### Level 2, Value Animation

Animate from zero to the current value.

Example:

0 → 72%

Adds polish but still communicates only the present.
