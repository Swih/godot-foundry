# godot-foundry

> From idea to playable prototype in one session.

Multi-agent game development studio for Godot Engine, powered by Claude Code.
15 specialized agents. Genre presets. GDAI MCP integration.
Built for solo devs who ship.

## Why this exists

Building a game solo with AI is powerful — but a single chat session has no structure.
Nobody stops you from hardcoding magic numbers, skipping design docs, or writing spaghetti.
There's no QA, no design review, no one asking "does this fit the vision?"

godot-foundry gives your AI session the structure of a real Godot studio.
15 agents organized in a hierarchy — directors who guard the vision,
leads who own their domains, specialists who do the work.

You make every decision. They ask the right questions, catch mistakes,
and keep your project clean from first brainstorm to Steam launch.

## Quick Start

```bash
git clone https://github.com/Swih/godot-foundry my-game
cd my-game
claude
```

Then type `/start` — the system asks where you are and guides you to the right workflow.

Or pick a genre preset:
```
/start --preset roguelike
/start --preset platformer
/start --preset topdown-rpg
/start --preset tower-defense
```

## What's Inside

| Category | Count | Description |
|----------|-------|-------------|
| Agents | 15 | Godot-native specialists across design, code, art, audio, QA |
| Skills | 20 | Slash commands: /start, /brainstorm, /design-review, /balance-check... |
| Hooks | 8 | Auto-validation on commits, sessions, assets |
| Rules | 6 | Path-scoped Godot coding standards |
| Presets | 4 | Genre templates: roguelike, platformer, RPG, tower defense |

## Agent Roster

### Tier 1 — Directors
| Agent | Domain |
|-------|--------|
| creative-director | Game vision, tone, player experience |
| technical-director | Architecture, performance, code quality |
| producer | Scope, planning, shipping deadlines |

### Tier 2 — Leads
| Agent | Domain |
|-------|--------|
| game-designer | Mechanics, systems, game feel |
| godot-specialist | Godot 4.x engine, GDScript, shaders, GDAI |
| qa-tester | Testing, bugs, edge cases, regression |

### Tier 3 — Specialists
| Agent | Domain |
|-------|--------|
| systems-designer | Scoring, progression, math balance |
| economy-designer | Currency, pricing, drop rates |
| gameplay-programmer | Core gameplay GDScript |
| ui-programmer | UI scenes, menus, HUD |
| technical-artist | Shaders, VFX, particles, juice |
| sound-designer | Audio integration, SFX, dynamic audio |
| ux-designer | Onboarding, flow, accessibility |
| prototyper | Rapid throwaway prototypes |
| performance-analyst | FPS, memory, optimization |

## GDAI MCP Integration

For the full AI → Godot pipeline, add GDAI MCP ($19, lifetime):

1. Get it at https://gdaimcp.com
2. Install the Godot plugin
3. Configure in Claude Code

With GDAI, agents can see your game, test it, screenshot it,
read errors, and fix bugs in an autonomous loop.

Without GDAI, agents still write code and create files,
but can't see or test the running game.

## Genre Presets

| Preset | Emphasized Agents | Templates |
|--------|------------------|-----------|
| roguelike | systems-designer, economy-designer | GDD, economy sheet, balance checklist |
| platformer | ux-designer, technical-artist | GDD, level design sheet |
| topdown-rpg | game-designer, economy-designer | GDD, faction template |
| tower-defense | systems-designer, economy-designer | GDD, wave designer |

## Slash Commands

```
/start              — Guided project setup
/brainstorm          — Explore game ideas
/sprint-plan         — Plan the week
/design-review       — Check design coherence
/balance-check       — Validate game balance
/code-review         — Code quality review
/prototype           — Build a quick test
/playtest-report     — Log playtest feedback
/bug-report          — Document a bug
/scope-check         — Am I overscoping?
/estimate            — How long will this take?
/perf-profile        — Performance analysis
/tech-debt           — Find technical debt
/team-gameplay       — Multi-agent gameplay work
/team-ui             — Multi-agent UI work
/team-audio          — Multi-agent audio work
/team-polish         — Multi-agent polish pass
/release-checklist   — Pre-launch validation
/changelog           — Generate changelog
/hotfix              — Emergency fix workflow
```

## Project Structure

```
src/
├── core/           # Autoloads, managers, state machines
├── gameplay/       # Game logic, systems, entities
├── ui/             # UI scenes and scripts
└── audio/          # Audio bus, SFX manager
assets/             # Art, audio, fonts, themes
design/             # GDD, balance sheets
prototypes/         # Throwaway tests (relaxed rules)
production/         # Sprint plans, milestones
```

## Built With godot-foundry

- **Channel 77** — A bingo roguelike on a haunted TV (in development)

## Credits

This project builds upon:
- [oh-my-claudecode](https://github.com/Yeachan-Heo/oh-my-claudecode) by @Yeachan-Heo (MIT)
- [Claude-Code-Game-Studios](https://github.com/Donchitos/Claude-Code-Game-Studios) by @Donchitos (MIT)

Recommended companion:
- [GDAI MCP](https://gdaimcp.com) by @3ddelano

## License

MIT — use it, fork it, ship games with it. Just keep the credits.
