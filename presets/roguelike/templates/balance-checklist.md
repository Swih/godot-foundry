# Balance Checklist -- Roguelike Template

Complete all items before locking a balance pass. Each item must be verified, not assumed.

---

## Core Systems

- [ ] Score formula documented with exact numbers and step-by-step example
- [ ] Difficulty curve simulated 100+ runs per tier with results recorded
- [ ] Win rate per difficulty validated against targets (Normal 60-70%, Hard 30-40%, Expert 10-15%)
- [ ] All multiplicative effects are conditional (require setup, cost, or tradeoff)
- [ ] No infinite loops or degenerate combos (every new item checked against all existing multipliers)
- [ ] Early game is fun without items (base mechanics carry the first 2-3 floors)
- [ ] Endgame requires synergies (raw stats alone cannot beat the final boss on Hard+)
- [ ] Economy is stable with no inflation or deflation across a full run

## Economy

- [ ] Currency sources and sinks documented per floor
- [ ] Average gold at each shop visit matches intended purchasing power
- [ ] Shop prices scale correctly with floor (verified with formula)
- [ ] Player ends run with target surplus (not too much, not too little unspent gold)
- [ ] Reroll cost escalation prevents infinite fishing

## Items and Relics

- [ ] Every item has exact numbers documented (no vague "increases damage")
- [ ] Common items are simple and standalone useful
- [ ] Uncommon items introduce conditions or synergy hooks
- [ ] Rare items are build-defining but not auto-pick
- [ ] Epic items warp strategy and demand building around them
- [ ] Legendary items have major tradeoffs (not strictly better than epics)
- [ ] No single item is an auto-pick regardless of build
- [ ] No single item is never picked (all items have at least one viable use case)

## Difficulty and Progression

- [ ] Floor power budgets defined and tested
- [ ] Boss encounters test specific skills or punish specific weaknesses
- [ ] Difficulty tiers change mechanics, not just numbers
- [ ] Meta-progression expands options without raw power creep
- [ ] Unlock conditions are achievement-based, not grind-based

## Anti-Frustration

- [ ] Pity timer threshold set and tested
- [ ] Safety net drops activate below power thresholds
- [ ] Last-chance mechanic prevents single-hit run-enders
- [ ] Bad luck protection on shops verified
- [ ] Streak breaker active after consecutive losses

## Builds and Archetypes

- [ ] At least 3 distinct builds are viable at each difficulty tier
- [ ] No single build dominates win rate by more than 15% over others
- [ ] Build-defining items appear frequently enough to be discovered naturally
- [ ] Hybrid builds are possible but not strictly optimal (specialization rewarded)

## Juice and Feel

- [ ] Screen shake values set per event type
- [ ] Damage numbers and death particles implemented
- [ ] Every player action has audio feedback
- [ ] Score ticker counts up with escalating pitch
- [ ] Hit-stop on heavy attacks implemented
- [ ] UI elements animate into position (no instant state changes)
