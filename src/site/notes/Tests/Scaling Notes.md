---
{"dg-publish":true,"permalink":"/tests/scaling-notes/","tags":["Notes"],"dg-note-properties":{"tags":["Notes"]}}
---

Level = IF (Base > Player, Base, Player -2 UNLESS < base THEN base)
HP
MA = Base * Class multiplier * (1 + ((Level - BLevel) * 0.05))
PA

Higher level enemy stays the same
lower level dragged up by factor of player level
Difference of player level and base enemy level should be factored

HP= 10
MA=30
PA=40

Tier	Multiplier
Minion	0.9
Normal	1.0
Elite	1.1
Boss	1.2

GrowthRates:
HP = 0.08
PA = 0.10
MA = 0.05

EnemyLevel = PlayerLevel - 2

ΔLevel = EnemyLevel - DesignLevel

ScaledStat = BaseStat × (1 + GrowthRate × ΔLevel)

TieredStat = ScaledStat × TierMultiplier

| Specialisation |	HP |	PhysArmour |	MagArmour	|
Tank	1.4	1.5	1.2	
Warrior	1.1	1.1	0.7	
Mage	0.8	0.7	1.5	

Final Stat = Tiered Stat × Specialisation Multiplier

Orc Scout = L 1 = 10/5/0 = L 20 = 25 / 14 / 0 = No specialisation = Minion = 23/13/0
Khaz = L 1 = 10/30/40 = L20 = 25 / 87 / 78 = Boss = 30 / 105 / 94 = No spec



#### Damage

Bite does 4 PA 

EnemyLevel = PlayerLevel - 2

ΔLevel = EnemyLevel - DesignLevel

Damage  = BaseDmg * (1 + (ΔLevel * (0.5/6.666))

0.5 being the approximate gain every 6.66 levels
E.g at level 7, it is an approximate 1.5x multiplier

