## What is Rarity? ##

Rarity is a visible way to see if an item is more or less rare. There are 5 different Rarity tiers

* Common
* Uncommon
* Rare
* Epic
* Legendary

## How does it affect Generation? ##

Rarity can contribute to the items that get generated on your server. They can change the following...

* Display: The name displayed on an item that is generated by this rarity
* ColorCode: The color of the item name, of this rarity
* Modifications: How many modifications are added to an item of this rarity
* AttributeMultiplier: After all modifications are applied, multiply the values by this value
* Materials: list of materials that will be generated from this rarity

Lets walk through an example.

```
  Uncommon:
    Display: 'Uncommon'
    ColorCode: '&a'
    Modifications: 1
    AttributeMultiplier: 1.1
    Materials:
    - STONE_SWORD
    - STONE_AXE
    - IRON_SWORD
    - IRON_AXE
    - GOLD_SWORD
    - GOLD_AXE
    - BOW
    - SHIELD
    - CHAINMAIL_HELMET
    - CHAINMAIL_CHESTPLATE
    - CHAINMAIL_LEGGINGS
    - CHAINMAIL_BOOTS
    - IRON_HELMET
    - IRON_CHESTPLATE
    - IRON_LEGGINGS
    - IRON_BOOTS
    - GOLD_HELMET
    - GOLD_CHESTPLATE
    - GOLD_LEGGINGS
    - GOLD_BOOTS
```

In this tier, the id of the rarity is Uncommon. **You cannot change the id or it will break the rarity.** When this rarity is selected in the generation process, a couple things will happen.

![Uncommon.PNG](https://bitbucket.org/repo/ek9o8ey/images/570167747-Uncommon.PNG)

1. A material will be selected from the **Materials** list (example item was CHAINMAIL_LEGGINGS
2. The display name will be prefixed with the **color code** '&a' making the name green.
3. There will be a Rarity tag added to the lore with the **Display name** and Rarity **color code**. 
4. A single **modification** will be selected in this case 'Minor Health'
5. All attributes added were multiplied by 1.1 from the **AttributeMultiplier**

## Can I change the rarity drop chances? ##

In the rarity.yml file, at the bottom, there is a section for **RarityChance**. This is the section where you can determine rarity chances for either **MobDrops** or **Crafted** items. You also have the additional control of changing these rarities at **different levels**. In the default config it shows a section for level 1+ and level 20+.

The default configuration has the following snippet. The result is what is commented to the right of each line.

```
RarityChance:
  MobDrops:
    1:
      Common: 200 # (200 / 337) = 59.3%
      Uncommon: 90 # (90 / 337) = 26.7%
      Rare: 30 # (30 / 337) = 8.9%
      Epic: 15 # (15 / 337) = 4.5%
      Legendary: 2 # (2 / 337)) = 0.06%
    20:
      Common: 150
      Uncommon: 90
      Rare: 30
      Epic: 15
      Legendary: 2
  Crafted:
    1:
      Common: 200
      Uncommon: 20
```

In short this system is a "Weight-based" system. If you want something to be more common, increase its weight. If you want something super rare (like legendary gear) make it super small. The % chance is calculated by (rarity weight / total weight from all rarity).