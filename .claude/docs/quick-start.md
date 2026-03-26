# Game Studio Agent Architecture -- Quick Start Guide

## What Is This?

This is a complete Claude Code agent architecture for game development. It
organizes specialized AI agents into a studio hierarchy that mirrors
real game development teams, with defined responsibilities, delegation
rules, and coordination protocols. It includes a Godot engine specialist
agent. All design agents and templates are grounded in established game design
theory (MDA Framework, Self-Determination Theory, Flow State, Bartle
Player Types).

## How to Use

### 1. Understand the Hierarchy

There are three tiers of agents:

- **Tier 1 (Opus)**: Directors who make high-level decisions
  - `creative-director` -- vision and creative conflict resolution
  - `technical-director` -- architecture and technology decisions
  - `producer` -- scheduling, coordination, and risk management

- **Tier 2 (Sonnet)**: Leads who own their domain
  - `game-designer`, `godot-specialist`, `qa-tester`

- **Tier 3 (Sonnet/Haiku)**: Specialists who execute within their domain
  - `systems-designer`, `economy-designer`, `gameplay-programmer`,
    `ui-programmer`, `technical-artist`, `sound-designer`, `ux-designer`,
    `prototyper`, `performance-analyst`

### 2. Pick the Right Agent for the Job

Ask yourself: "What department would handle this in a real studio?"

| I need to... | Use this agent |
|-------------|---------------|
| Design a new mechanic | `game-designer` |
| Write gameplay code | `gameplay-programmer` |
| Create a shader | `technical-artist` |
| Plan the next sprint | `producer` |
| Review code quality | `godot-specialist` |
| Write test cases | `qa-tester` |
| Fix a performance problem | `performance-analyst` |
| Design a loot table | `economy-designer` |
| Resolve a creative conflict | `creative-director` |
| Make an architecture decision | `technical-director` |
| Design UI flows | `ux-designer` |
| Implement UI screens | `ui-programmer` |
| Design sound effects | `sound-designer` |
| Design a game system | `systems-designer` |
| Test a mechanic idea quickly | `prototyper` |
| Get Godot advice | `godot-specialist` |
| Brainstorm a new game idea | Use `/brainstorm` skill |

### 3. Use Slash Commands for Common Tasks

| Command | What it does |
|---------|-------------|
| `/start` | First-time onboarding — asks where you are, guides you to the right workflow |
| `/brainstorm` | Guided game concept ideation from scratch |
| `/sprint-plan` | Creates or updates sprint plans |
| `/design-review` | Reviews a design document |
| `/balance-check` | Analyzes game balance data |
| `/code-review` | Reviews code for quality and architecture |
| `/prototype` | Scaffolds a throwaway prototype |
| `/playtest-report` | Creates or analyzes playtest feedback |
| `/bug-report` | Creates a structured bug report |
| `/scope-check` | Detect scope creep against plan |
| `/estimate` | Produces structured effort estimates |
| `/perf-profile` | Performance profiling and bottleneck ID |
| `/tech-debt` | Scan, track, and prioritize tech debt |
| `/team-gameplay` | Orchestrate full gameplay team pipeline |
| `/team-ui` | Orchestrate full UI team pipeline |
| `/team-audio` | Orchestrate full audio team pipeline |
| `/team-polish` | Orchestrate full polish team pipeline |
| `/release-checklist` | Validates pre-release checklist |
| `/changelog` | Generates changelog from git history |
| `/hotfix` | Emergency fix with audit trail |

### 4. Use Templates for New Documents

Templates are in `.claude/docs/templates/`:

- `game-design-document.md` -- for new mechanics and systems
- `architecture-decision-record.md` -- for technical decisions
- `risk-register-entry.md` -- for new risks
- `narrative-character-sheet.md` -- for new characters
- `test-plan.md` -- for feature test plans
- `sprint-plan.md` -- for sprint planning
- `milestone-definition.md` -- for new milestones
- `level-design-document.md` -- for new levels
- `game-pillars.md` -- for core design pillars
- `art-bible.md` -- for visual style reference
- `technical-design-document.md` -- for per-system technical designs
- `post-mortem.md` -- for project/milestone retrospectives
- `sound-bible.md` -- for audio style reference
- `release-checklist-template.md` -- for platform release checklists
- `changelog-template.md` -- for player-facing patch notes
- `release-notes.md` -- for player-facing release notes
- `incident-response.md` -- for live incident response playbooks
- `game-concept.md` -- for initial game concepts (MDA, SDT, Flow, Bartle)
- `pitch-document.md` -- for pitching the game to stakeholders
- `economy-model.md` -- for virtual economy design (sink/faucet model)
- `faction-design.md` -- for faction identity, lore, and gameplay role
- `systems-index.md` -- for systems decomposition and dependency mapping
- `project-stage-report.md` -- for project stage detection output
- `design-doc-from-implementation.md` -- for reverse-documenting existing code into GDDs
- `architecture-doc-from-code.md` -- for reverse-documenting code into architecture docs
- `concept-doc-from-prototype.md` -- for reverse-documenting prototypes into concept docs

### 5. Follow the Coordination Rules

1. Work flows down the hierarchy: Directors -> Leads -> Specialists
2. Conflicts escalate up the hierarchy
3. Cross-department work is coordinated by the `producer`
4. Agents do not modify files outside their domain without delegation
5. All decisions are documented

## First Steps for a New Project

**Don't know where to begin?** Run `/start`. It asks where you are and routes
you to the right workflow. No assumptions about your game, engine, or experience level.

If you already know what you need, jump directly to the relevant path:

### Path A: "I have no idea what to build"

1. **Run `/start`** (or `/brainstorm open`) -- guided creative exploration:
   what excites you, what you've played, your constraints
   - Generates 3 concepts, helps you pick one, defines core loop and pillars
   - Produces a game concept document and recommends an engine
2. **Validate the concept** -- Run `/design-review design/gdd/game-concept.md`
3. **Test the core loop** -- Run `/prototype [core-mechanic]`
4. **Playtest it** -- Run `/playtest-report` to validate the hypothesis
5. **Plan the first sprint** -- Run `/sprint-plan new`
6. Start building

### Path B: "I know what I want to build"

If you already have a game concept and engine choice:

1. **Write the Game Pillars** -- delegate to `creative-director`
2. **Plan the first sprint** -- Run `/sprint-plan new`
3. Start building

### Path C: "I have an existing project"

If you have design docs, prototypes, or code already:

1. **Run `/start`** -- analyzes what exists, identifies gaps, and recommends next steps
2. **Plan the next sprint** -- Run `/sprint-plan new`

## File Structure Reference

```
CLAUDE.md                          -- Master config (read this first, ~60 lines)
.claude/
  settings.json                    -- Claude Code hooks and project settings
  agents/                          -- 15 agent definitions (YAML frontmatter)
  skills/                          -- 20 slash command definitions (YAML frontmatter)
  hooks/                           -- 8 hook scripts (.sh) wired by settings.json
  rules/                           -- 6 path-specific rule files
  docs/
    quick-start.md                 -- This file
    technical-preferences.md       -- Project-specific standards
    coding-standards.md            -- Coding and design doc standards
    coordination-rules.md          -- Agent coordination rules
    context-management.md          -- Context budgets and compaction instructions
    review-workflow.md             -- Review and sign-off process
    directory-structure.md         -- Project directory layout
    agent-roster.md                -- Full agent list with tiers
    skills-reference.md            -- All slash commands
    rules-reference.md             -- Path-specific rules
    hooks-reference.md             -- Active hooks
    agent-coordination-map.md      -- Full delegation and workflow map
    setup-requirements.md          -- System prerequisites (Git Bash, jq, Python)
    settings-local-template.md     -- Personal settings.local.json guide
    hooks-reference/               -- Hook documentation and git hook examples
    templates/                     -- 28 document templates
```
