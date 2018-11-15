# How does Item Generation Work? #

A lot of logic goes into the Item Generation but boiled down simply...

1. Randomly select a rarity based on config chances
2. Randomly select modifications (number based on rarity chosen) (provides prefix/suffix logic)
3. Apply Durability (if CustomDurability enabled)
4. Generate Lore