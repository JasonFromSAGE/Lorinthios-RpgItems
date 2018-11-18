# Lore Generation Tags #

There may be some cases where you want to generated attributes on an item dropped from another plugin such as Mythic Drops. There are some simple tags you can add to your dropped items lore to cause random attributes to be generated like normal from LorinthsRpgItems.

## Tags ##
**Required**

* [LriGeneration:{level}] - replace {level} with the level of the targeted generation you want to apply to this item
Note: {level} can accept a range from min-max level. Example, [LriGeneration:1-10] will generate an item between levels 1-10 (inclusive)

**Optional**

* [LriGeneration-Name] - Will apply prefix / suffix and rarity color to the items display name
* [LriGeneration-Level] - Adds the level and iLevel(if applicable) lines as configured in display.yml to the lore at this spot
* [LriGeneration-Rarity] - Adds the rarity tier as configured in display.yml
* [LriGeneration-Durability] - Adds the durability line (or moves existing durability line) to this location on the lore
* [LriGeneration-Attributes] - Adds all the attributes from the generated attributes and attributes already added to the item together and places them here