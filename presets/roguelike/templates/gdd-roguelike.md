# Game Design Document -- Roguelike Template

---

## 1. Game Identity

- **Working Title:** [Your game's name]
- **Elevator Pitch:** One sentence that captures the core fantasy. Example: "A roguelike deckbuilder where you sacrifice cards to power up relics."
- **Reference Games:** List 2-4 games that share DNA with yours and note what you are borrowing from each (e.g., "Slay the Spire -- map pathing and card rewards; Vampire Survivors -- auto-battler pacing").
- **Target Audience:** Describe the player. Are they speedrunners, theory-crafters, casual run-and-done players? State expected session length (15 min? 45 min?).
- **Platform / Input:** PC, console, mobile? Controller, keyboard, touch?

---

## 2. Core Loop

Describe what the player *does* at two timescales:

### 10-Second Loop
What is the moment-to-moment action? Examples: play a card, position a unit, dodge an attack. This is the "verb" the player repeats most often. It must feel good on its own before any systems layer on top.

### 10-Minute Loop
What does a full cycle look like? Typically: encounter -> reward -> shop/upgrade -> next encounter. Map out the sequence and note decision points where the player chooses between two meaningful options.

---

## 3. Scoring System

- **Base Score Formula:** Write the exact formula. Example: `base_score = enemies_defeated * 10 + floors_cleared * 50 + boss_bonus`
- **Step-by-Step Breakdown:** Walk through how a mid-skill player's score builds across a run. Show the math for floors 1, 5, 10, and the final boss.
- **Scaling:** How does score scale in the late game? Linear, exponential, logarithmic? Justify why.
- **Leaderboard Considerations:** Are scores comparable across difficulty tiers? Do modifiers apply a multiplier?

---

## 4. Progression -- Within a Run

- **Power Curve:** Describe how strong the player should feel at 25%, 50%, 75%, and 100% of a run. Early game should feel dangerous but winnable; late game should feel powerful but not trivial.
- **Milestones:** List key moments (first shop, first elite, first boss, midpoint event, final boss). Note what the player should have acquired by each.
- **Boss Encounters:** How many bosses per run? What makes each distinct? Bosses should test a specific skill or punish a specific weakness.
- **Difficulty Spikes:** Identify where intentional difficulty spikes occur and why they exist (e.g., "Floor 6 elite forces players to have an AOE answer or lose").

---

## 5. Progression -- Between Runs

- **Meta-Progression:** What carries over between runs? Unlockable characters, starting bonuses, cosmetics? Keep meta-progression feeling like expanding options, not raw power creep.
- **Unlock Conditions:** List unlock triggers. Prefer achievement-style unlocks ("beat boss X without taking damage") over grind-style ("play 100 runs").
- **Difficulty Tiers:** Define 3-5 difficulty tiers (e.g., Normal, Hard, Expert, Ascension 1-20). Each tier should change at least one mechanic, not just inflate numbers.
- **Prestige / New Game+:** If applicable, describe what changes on repeated completions.

---

## 6. Item / Relic System

### Categories
Define item categories (e.g., Weapons, Passives, Consumables, Relics). State how many slots the player has for each.

### Rarity Tiers
Define 3-5 rarity tiers and their design intent:

| Tier     | Color  | Design Intent                                  |
|----------|--------|------------------------------------------------|
| Common   | White  | Simple stat boosts, easy to understand          |
| Uncommon | Green  | Conditional bonuses, introduces synergy hooks   |
| Rare     | Blue   | Build-defining, strong with the right setup     |
| Epic     | Purple | Warps strategy, demands building around it      |
| Legendary| Gold   | One per run max, dramatically alters playstyle  |

### Example Items (5 per tier)

**Common:**
1. [Name] -- [Effect with exact numbers, e.g., "+3 damage per attack"]
2. [Name] -- [Effect]
3. [Name] -- [Effect]
4. [Name] -- [Effect]
5. [Name] -- [Effect]

**Uncommon:**
1. [Name] -- [Effect with condition, e.g., "+5 damage if HP > 75%"]
2. [Name] -- [Effect]
3. [Name] -- [Effect]
4. [Name] -- [Effect]
5. [Name] -- [Effect]

**Rare:**
1. [Name] -- [Effect with synergy hook, e.g., "Double all poison damage; take 1 damage per turn"]
2. [Name] -- [Effect]
3. [Name] -- [Effect]
4. [Name] -- [Effect]
5. [Name] -- [Effect]

**Epic:**
1. [Name] -- [Effect that warps strategy]
2. [Name] -- [Effect]
3. [Name] -- [Effect]
4. [Name] -- [Effect]
5. [Name] -- [Effect]

**Legendary:**
1. [Name] -- [Run-defining effect with major tradeoff]
2. [Name] -- [Effect]
3. [Name] -- [Effect]
4. [Name] -- [Effect]
5. [Name] -- [Effect]

---

## 7. Economy

- **Currency Types:** List each currency and its purpose (e.g., Gold for shops, Souls for meta-upgrades).
- **Sources Per Round:** How much currency does the player earn per encounter? Per boss? Per bonus objective?
- **Sinks:** Shop prices, reroll costs, upgrade costs, sacrifice mechanics. Every source must have a sink.
- **Pricing Formula:** Example: `price = base_cost * rarity_multiplier * floor_scaling`. Write the actual formula with numbers.
- **Inflation Control:** How do you prevent late-game players from buying everything? Escalating prices? Limited shop slots? Currency caps?

---

## 8. Difficulty Curve

- **Target Win Rates:** State the intended win rate per difficulty tier. Example: Normal 60-70%, Hard 30-40%, Expert 10-15%.
- **Scaling Formula:** How do enemy stats scale per floor? Example: `enemy_hp = base_hp * (1 + floor * 0.12)`. Write the actual formula.
- **Simulation Requirement:** Before locking balance, run 100+ simulated runs per difficulty tier. Document median run length, win rate, and average score. Flag any tier where win rate deviates more than 10% from target.
- **Rubber Banding:** Does the game get easier if the player is struggling? If so, describe the mechanism (e.g., "shop offers a free heal if HP < 25%").

---

## 9. Content Requirements

### Early Access Launch (Minimum Viable)
- [ ] Items: [number] common, [number] uncommon, [number] rare, [number] epic, [number] legendary
- [ ] Enemies: [number] basic, [number] elite, [number] boss
- [ ] Floors/Stages: [number]
- [ ] Characters/Classes: [number]
- [ ] Events: [number]

### 1.0 Release
- [ ] Items: [number] per tier (target total: [number])
- [ ] Enemies: [number] total with [number] bosses
- [ ] Floors/Stages: [number]
- [ ] Characters/Classes: [number]
- [ ] Meta-progression unlocks: [number]
- [ ] Difficulty tiers: [number]

---

## 10. Balancing Rules

These rules should be enforced during all design and review:

1. **Additive bonuses are the default.** Flat "+X" effects are common and easy to reason about.
2. **Multiplicative effects are rare and conditional.** Any "x2" or "x1.5" effect must require a setup condition, a health cost, or a tradeoff.
3. **Every powerful effect has a cost.** If an item is strong, it must demand something: HP, gold, a slot, a restriction.
4. **No unconditional infinite scaling.** If something grows without limit, it must have diminishing returns or a cap.
5. **Test degenerate combos.** For every new item, check it against every existing multiplicative effect. Document known synergies and flag anything that breaks target score ranges.
6. **Floor power budgets.** Define a "power budget" per floor. If the player exceeds it, encounters should feel trivial -- this is a design signal, not a reward.

---

## 11. Builds / Archetypes

Define 3-6 intended emergent builds. Players should discover these organically through item synergies, not be told about them.

### Build 1: [Name, e.g., "Poison Alchemist"]
- **Core Items:** [2-3 items that define this build]
- **Playstyle:** [How this build plays differently]
- **Strengths:** [What it excels at]
- **Weaknesses:** [What counters it or where it struggles]
- **Key Decision:** [The interesting choice this build forces]

### Build 2: [Name]
- **Core Items:** [...]
- **Playstyle:** [...]
- **Strengths:** [...]
- **Weaknesses:** [...]
- **Key Decision:** [...]

### Build 3: [Name]
- **Core Items:** [...]
- **Playstyle:** [...]
- **Strengths:** [...]
- **Weaknesses:** [...]
- **Key Decision:** [...]

*(Add builds 4-6 as needed)*

---

## 12. Anti-Frustration

Invisible or semi-visible systems that prevent the worst player experiences:

- **Pity Timer:** After [X] rewards without a rare+ item, the next reward is guaranteed rare or better. Document the exact threshold.
- **Safety Net Drops:** If the player enters a boss encounter below a power threshold, offer a free item or heal beforehand.
- **Last-Chance Mechanic:** When HP hits 0, grant one free revive per run (or a "death-defying" relic that activates once). This prevents a single unlucky hit from ending an otherwise good run.
- **Bad Luck Protection on Shops:** If the shop rolls items that are useless for the player's current build, re-roll one slot with a synergy-weighted pick.
- **Streak Breaker:** After [X] consecutive losses, offer a temporary buff or bonus starting item on the next run.
- **Floor Skip / Shortcut:** If the player has beaten a section many times, consider offering a shortcut so repeat content does not become a chore.

---

## 13. Juice Requirements

The game should *feel* good before it *is* good. Minimum juice targets:

- **Screen Shake:** On hit, on kill, on boss death. Define intensity per event (e.g., kill = 2px for 0.1s, boss death = 6px for 0.3s).
- **Particles:** Damage numbers, death explosions, item pickup sparkle, currency collection trail.
- **Audio Feedback:** Every player action needs a sound. Hits, pickups, purchases, level-ups, score ticks. No silent actions.
- **Score Ticker:** End-of-run score should count up digit by digit with escalating sound pitch. Bonus multipliers should pop in with a delay and re-trigger the count-up.
- **Time Manipulation:** Hit-stop on heavy attacks (freeze 2-3 frames). Slow-motion on final kill of a wave.
- **UI Animation:** Cards/items slide, bounce, or flip into position. No instant state changes in the UI.
- **Camera:** Slight zoom on big moments. Ease-in/ease-out on transitions. Never snap the camera.
