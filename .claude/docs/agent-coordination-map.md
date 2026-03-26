# Agent Coordination and Delegation Map

## Organizational Hierarchy

```
                           [Human Developer]
                                 |
                 +---------------+---------------+
                 |               |               |
         creative-director  technical-director  producer
                 |               |               |
           +-----+-----+        |        (coordinates all)
           |           |        |
     game-designer  godot-spec  qa-tester
           |           |           |
     +-----+-----+    |           |
     |     |     |    |           |
    sys   eco   ux   gp  ui  ta  snd  proto  perf-a
```

### Legend
```
sys  = systems-designer       gp    = gameplay-programmer
eco  = economy-designer       ui    = ui-programmer
ta   = technical-artist       snd   = sound-designer
ux   = ux-designer            proto = prototyper
perf-a = performance-analyst
godot-spec = godot-specialist
```

## Delegation Rules

### Who Can Delegate to Whom

| From | Can Delegate To |
|------|----------------|
| creative-director | game-designer, sound-designer |
| technical-director | godot-specialist, performance-analyst, technical-artist (technical decisions) |
| producer | Any agent (task assignment within their domain only) |
| game-designer | systems-designer, economy-designer |
| godot-specialist | gameplay-programmer, ui-programmer, technical-artist |
| qa-tester | (works independently, files bug reports and test cases) |
| prototyper | (works independently, reports findings to producer and relevant leads) |

### Escalation Paths

| Situation | Escalate To |
|-----------|------------|
| Two designers disagree on a mechanic | game-designer |
| Game design vs technical feasibility | producer (facilitates), then creative-director + technical-director |
| Code architecture disagreement | technical-director |
| Schedule conflict between departments | producer |
| Scope exceeds capacity | producer, then creative-director for cuts |
| Quality gate disagreement | qa-tester, then technical-director |
| Performance budget violation | performance-analyst flags, technical-director decides |

## Common Workflow Patterns

### Pattern 1: New Feature (Full Pipeline)

```
1. creative-director  -- Approves feature concept aligns with vision
2. game-designer      -- Creates design document with full spec
3. producer           -- Schedules work, identifies dependencies
4. godot-specialist   -- Designs code architecture, creates interface sketch
5. gameplay-programmer -- Implements the feature
6. technical-artist   -- Implements visual effects (if needed)
7. sound-designer     -- Creates audio event list (if needed)
8. qa-tester          -- Writes test cases and executes tests
9. godot-specialist   -- Code review
10. producer          -- Marks task complete
```

### Pattern 2: Bug Fix

```
1. qa-tester          -- Files bug report with /bug-report
2. qa-tester          -- Triages severity and priority
3. producer           -- Assigns to sprint (if not S1)
4. godot-specialist   -- Identifies root cause, assigns to programmer
5. gameplay-programmer -- Fixes the bug
6. godot-specialist   -- Code review
7. qa-tester          -- Verifies fix and runs regression
```

### Pattern 3: Balance Adjustment

```
1. game-designer      -- Evaluates the issue against design intent
2. economy-designer   -- Models the adjustment
3. game-designer      -- Approves the new values
4. [data file update] -- Change configuration values
5. qa-tester          -- Regression test affected systems
```

### Pattern 4: Sprint Cycle

```
1. producer           -- Plans sprint with /sprint-plan new
2. [All agents]       -- Execute assigned tasks
3. producer           -- Daily status with /sprint-plan status
4. qa-tester          -- Continuous testing during sprint
5. godot-specialist   -- Continuous code review during sprint
6. producer           -- Sprint retrospective
7. producer           -- Plans next sprint incorporating learnings
```

### Pattern 5: Rapid Prototype

```text
1. game-designer        -- Defines the hypothesis and success criteria
2. prototyper           -- Scaffolds prototype with /prototype
3. prototyper           -- Builds minimal implementation (hours, not days)
4. game-designer        -- Evaluates prototype against criteria
5. prototyper           -- Documents findings report
6. creative-director    -- Go/no-go decision on proceeding to production
7. producer             -- Schedules production work if approved
```

## Cross-Domain Communication Protocols

### Design Change Notification

When a design document changes, the game-designer must notify:
- godot-specialist (implementation impact)
- qa-tester (test plan update needed)
- producer (schedule impact assessment)
- Relevant specialist agents depending on the change

### Architecture Change Notification

When an ADR is created or modified, the technical-director must notify:
- godot-specialist (code changes needed)
- All affected specialist programmers
- qa-tester (testing strategy may change)
- producer (schedule impact)

## Anti-Patterns to Avoid

1. **Bypassing the hierarchy**: A specialist agent should never make decisions
   that belong to their lead without consultation.
2. **Cross-domain implementation**: An agent should never modify files outside
   their designated area without explicit delegation from the relevant owner.
3. **Shadow decisions**: All decisions must be documented. Verbal agreements
   without written records lead to contradictions.
4. **Monolithic tasks**: Every task assigned to an agent should be completable
   in 1-3 days. If it is larger, it must be broken down first.
5. **Assumption-based implementation**: If a spec is ambiguous, the implementer
   must ask the specifier rather than guessing. Wrong guesses are more expensive
   than a question.
