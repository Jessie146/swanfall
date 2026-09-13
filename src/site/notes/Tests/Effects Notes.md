---
{"dg-publish":true,"permalink":"/tests/effects-notes/","tags":["Notes"],"dg-note-properties":{"tags":["Notes"]}}
---

1. Status Effect Framework

Every status should define:

- Type: Physical / Magic / Hybrid  
- Applies To: Phys Armour / Mag Armour / HP  
- Trigger Condition  
- Effect  
- Duration  
- Scaling

2. Armour-Gated Application (VERY important)

Use this rule:

If Armour > 0 → Status is weakened or altered  
If Armour = 0 → Status is fully applied
Example:
Burn on Magic Armour → weak DoT
Burn on HP → full DoT + panic effect

👉 This makes breaking armour a goal, not just damage

3. Physical Status Effects
Bleed
Type: Physical  
Applies: HP (reduced if Phys Armour exists)
Deals % max HP over time
Ignores armour once applied

Bonus:

If Phys Armour = 0 → Bleed stacks faster

👉 Anti-tank mechanic

Shatter
Type: Physical  
Applies: Phys Armour
Reduces Physical Armour effectiveness
Can stack
ArmourMultiplier = 1 - (0.1 × stacks)

👉 Makes future hits stronger instead of just adding damage

Cripple
Type: Physical  
Applies: Movement / attack speed
If Phys Armour > 0 → minor slow
If Phys Armour = 0 → heavy slow + interrupt chance
Rend
Type: Physical  
Applies: Phys Armour directly
Deals bonus damage ONLY to armour
Converts % damage into “true armour damage”

👉 Great for breaking tanks

🔮 4. Magic Status Effects
Burn
Type: Magic  
Applies: Mag Armour → HP
On armour → small DoT
On HP → strong DoT + healing reduction
Shock
Type: Magic  
Applies: Mag Armour
Increases damage taken:
DamageTaken += 5% per stack
If Mag Armour = 0 → can chain to nearby enemies
Freeze
Type: Magic  
Applies: Movement / actions
On armour → slows
On HP → full freeze (stun)

👉 Classic “reward for breaking magic armour”

Arcane Rupture
Type: Magic  
Applies: Mag Armour
Causes damage taken to “spill” into HP:
X% of damage bypasses armour

👉 Counters high magic armour builds

⚔️ 5. Hybrid Status Effects (most interesting)
Corruption
Type: Hybrid  
Applies: Both armours
Gradually converts:
Phys Armour → Mag Armour (or vice versa)

👉 Messes with enemy strengths

Hemorrhage
Type: Hybrid  
Trigger: Bleed + Burn active
Burst damage based on missing HP

👉 Rewards combo builds

Disruption
Type: Hybrid  
Applies: Both armour types
Prevents armour regeneration
Reduces resistances
🔄 6. Status Scaling Formula

Avoid flat damage—scale off enemy stats:

DoT = MaxHP × (0.01 + 0.0005 × Level)

Duration:

Duration = Base × (1 + 0.01 × Level)

Stacks:

MaxStacks = 3 → 5 (based on skill power)
🧱 7. Armour Interaction Types (design toolkit)

Each status should follow one of these roles:

Type	Effect
Breaker	Destroys armour faster (Rend)
Amplifier	Increases damage taken (Shock)
Bypasser	Ignores armour (Rupture)
Punisher	Strong only after armour breaks (Bleed, Freeze)
Converter	Changes armour types (Corruption)

👉 Mix these across enemies and player builds.

🧑‍🤝‍🧑 8. Enemy Design Using Status

Instead of more HP, give enemies:

Resistance to certain statuses
Immunity while armour is active
Enrage when a status is applied
Example:

Stone Golem

Immune to Bleed
Weak to Shatter
Gains damage when Burned

👉 Forces adaptation without scaling stats

⚖️ 9. Anti-Spam Rules

Prevent status abuse:

StatusResistance = Base + (Level × scaling)

OR

Each reapply → duration reduced by 20%
🔥 10. Example Combat Flow

Player vs Armoured Knight:

Use Shock → increase damage taken
Apply Rend → break physical armour faster
Armour breaks
Apply Bleed → high HP damage
Finish with burst

👉 This creates a rotation, not button mashing.

🧩 Final Philosophy

Your system becomes great when:

Status effects don’t just add damage—they change how the fight is played.

If you want next, I can:

Design player skill trees built around these effects
Create enemy factions with unique status identities
Or build a PvP-ready status balance system (very different tuning)