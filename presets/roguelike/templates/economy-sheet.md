# Economy Sheet -- Roguelike Template

---

## Currency Sources Per Round

| Source              | Currency Type | Amount    | Notes                                      |
|---------------------|---------------|-----------|--------------------------------------------|
| Basic encounter     | Gold          | [X]-[Y]   | Range per encounter, scales with floor      |
| Elite encounter     | Gold          | [X]       | Fixed bonus on top of base reward           |
| Boss encounter      | Gold          | [X]       | Large payout, once per act                  |
| Bonus objective     | Gold          | [X]       | Optional challenge reward (e.g., no damage) |
| Event reward        | Gold          | [X]-[Y]   | Varies by event; some events cost currency  |
| Streak bonus        | Gold          | [X] per N  | Bonus for consecutive wins without damage   |
| Meta currency       | Souls/Tokens  | [X]       | Earned per run completion, scales with score |

### Expected Income Per Floor
| Floor Range | Avg Gold Earned | Cumulative Total | Notes                    |
|-------------|-----------------|------------------|--------------------------|
| 1-3         | [X]             | [X]              | Enough for 1 common item |
| 4-6         | [X]             | [X]              | Enough for 1 uncommon    |
| 7-10        | [X]             | [X]              | Enough for 1 rare        |
| 11-15       | [X]             | [X]              | Late-game budget         |
| Boss floors | [X] bonus       | --               | Lump sum                 |

---

## Currency Sinks

### Shop
| Item Rarity | Base Price | Floor Scaling Formula              | Example (Floor 1) | Example (Floor 10) |
|-------------|------------|------------------------------------|--------------------|---------------------|
| Common      | [X]        | `base * (1 + floor * [rate])`      | [X]                | [X]                 |
| Uncommon    | [X]        | `base * (1 + floor * [rate])`      | [X]                | [X]                 |
| Rare        | [X]        | `base * (1 + floor * [rate])`      | [X]                | [X]                 |
| Epic        | [X]        | `base * (1 + floor * [rate])`      | [X]                | [X]                 |
| Legendary   | [X]        | `base * (1 + floor * [rate])`      | [X]                | [X]                 |

### Upgrades
| Upgrade Type        | Cost          | Max Level | Notes                          |
|---------------------|---------------|-----------|--------------------------------|
| Item upgrade (+1)   | [X] per level | [N]       | Diminishing returns per level  |
| Reroll shop         | [X], +[Y]/use | No cap    | Escalating cost prevents abuse |
| Heal                | [X] per HP    | --        | Priced to compete with items   |
| Remove/banish item  | [X]           | --        | Useful for build focus         |

### Sacrifices / Gambles
| Action              | Cost          | Reward                           | Risk                          |
|---------------------|---------------|----------------------------------|-------------------------------|
| Sacrifice item      | 1 item        | [X] gold or random higher-tier   | Lose the item permanently     |
| Gamble at event     | [X] gold      | 50% double, 50% nothing          | Expected value should be < 1x |
| Blood offering      | [X] HP        | [X] gold or bonus item           | HP is a finite resource       |

---

## Expected Income Curve

Plot or describe the intended gold-over-time curve:

- **Early game (floors 1-3):** Income is low. Player affords 1-2 commons. This forces meaningful choices.
- **Mid game (floors 4-8):** Income ramps. Player can afford an uncommon every 2 floors. Rerolls become tempting.
- **Late game (floors 9+):** Income is high but prices scale too. The gap between "can afford" and "want to buy" should stay constant.
- **Target surplus at run end:** Player should have [X]% of total gold unspent. Too much unspent = prices too high or items not appealing. Too little = no meaningful shop decisions.

---

## Price Tiers by Rarity

| Rarity    | Price Range (Floor 1) | Price Range (Floor 10) | Design Intent                              |
|-----------|-----------------------|------------------------|--------------------------------------------|
| Common    | [X]-[Y]              | [X]-[Y]               | Always affordable; impulse buy              |
| Uncommon  | [X]-[Y]              | [X]-[Y]               | Requires saving 1-2 floors                  |
| Rare      | [X]-[Y]              | [X]-[Y]               | Requires deliberate saving or lucky income  |
| Epic      | [X]-[Y]              | [X]-[Y]               | Major investment; skip other purchases      |
| Legendary | [X]-[Y]              | [X]-[Y]               | Costs most of a run's savings               |

---

## Drop Rate Tables

### Post-Encounter Reward Rarity
| Rarity    | Base Rate | With Luck Modifier | Pity Timer Adjustment           |
|-----------|-----------|--------------------|---------------------------------|
| Common    | [X]%      | [X]%               | --                              |
| Uncommon  | [X]%      | [X]%               | --                              |
| Rare      | [X]%      | [X]%               | Guaranteed after [N] non-rares  |
| Epic      | [X]%      | [X]%               | Guaranteed after [N] non-epics  |
| Legendary | [X]%      | [X]%               | Guaranteed after [N] non-legendaries |

### Shop Slot Rarity (per slot)
| Rarity    | Slot 1 | Slot 2 | Slot 3 | Notes                                |
|-----------|--------|--------|--------|--------------------------------------|
| Common    | [X]%   | [X]%   | [X]%   | At least one common guaranteed       |
| Uncommon  | [X]%   | [X]%   | [X]%   |                                      |
| Rare      | [X]%   | [X]%   | [X]%   | Higher chance in later slots         |
| Epic      | [X]%   | [X]%   | [X]%   | Only appears in slot 3 before floor 5|
| Legendary | 0%     | 0%     | [X]%   | Only in slot 3, only after floor [N] |

### Boss Drop Table
| Boss       | Guaranteed Drop       | Bonus Drop Chance | Bonus Drop Pool             |
|------------|-----------------------|-------------------|-----------------------------|
| Act 1 Boss | 1 Rare item           | [X]%              | Epic pool                   |
| Act 2 Boss | 1 Epic item           | [X]%              | Legendary pool              |
| Final Boss | 1 Legendary item      | 100%              | Meta-currency bonus         |
