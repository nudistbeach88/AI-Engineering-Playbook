# Shared Skill Topology

## Goal

Keep one shared skill base across all agents and one private overlay per Prime/ally.

## Why this exists

The company should feel coherent no matter which assistant is active.

If Claude, Codex, Claw, and Hermes each learn the same core standards from different places, drift becomes likely. A shared topology gives us one company brain and separate private desks.

## Structure

- Shared layer
  - build playbook
  - design process
  - safety rules
  - approved workflows
  - reusable standards
- Prime layer
  - role-specific instructions
  - preferences
  - experiments
  - local overrides

## Precedence

1. Prime override
2. Shared company skill
3. Default bundled skill

## What to reverse engineer

- Agent OS: standards capture, spec shaping, standards injection
- Design OS: planning, design system, feature design, export handoff
- bm-skills: installable skill packaging and repeatable workflow modules

## Operating rule

The same shared layer should be represented in:

- Obsidian as a note structure
- Notion as canonical shared context
- GitHub as versioned documentation
- runtime assistants as loaded skill bundles

## Acceptance test

If a new Prime joins and gets the same baseline behavior everywhere, the topology is working.
