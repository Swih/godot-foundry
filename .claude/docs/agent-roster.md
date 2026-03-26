# Agent Roster

The following agents are available. Each has a dedicated definition file in
`.claude/agents/`. Use the agent best suited to the task at hand. When a task
spans multiple domains, the coordinating agent (usually `producer` or the
domain lead) should delegate to specialists.

## Tier 1 -- Directors (Opus)
| Agent | Domain | When to Use |
|-------|--------|-------------|
| `creative-director` | High-level vision | Major creative decisions, pillar conflicts, tone/direction |
| `technical-director` | Technical vision | Architecture decisions, tech stack choices, performance strategy |
| `producer` | Production management | Sprint planning, milestone tracking, risk management, coordination |

## Tier 2 -- Leads (Sonnet)
| Agent | Domain | When to Use |
|-------|--------|-------------|
| `game-designer` | Game design | Mechanics, systems, progression, economy, balancing |
| `godot-specialist` | Godot 4 | GDScript patterns, node/scene architecture, signals, Godot optimization |
| `qa-tester` | Quality assurance | Test strategy, bug triage, test cases, regression planning |

## Tier 3 -- Specialists (Sonnet or Haiku)
| Agent | Domain | Model | When to Use |
|-------|--------|-------|-------------|
| `systems-designer` | Systems design | Sonnet | Specific mechanic implementation, formula design, loops |
| `economy-designer` | Economy/balance | Sonnet | Resource economies, loot tables, progression curves |
| `gameplay-programmer` | Gameplay code | Sonnet | Feature implementation, gameplay systems code |
| `ui-programmer` | UI implementation | Sonnet | UI framework, screens, widgets, data binding |
| `technical-artist` | Tech art | Sonnet | Shaders, VFX, optimization, art pipeline tools |
| `sound-designer` | Sound design | Haiku | SFX design docs, audio event lists, mixing notes |
| `ux-designer` | UX flows | Sonnet | User flows, wireframes, accessibility, input handling |
| `prototyper` | Rapid prototyping | Haiku | Throwaway prototypes, mechanic testing, feasibility validation |
| `performance-analyst` | Performance | Sonnet | Profiling, optimization recs, memory analysis |
