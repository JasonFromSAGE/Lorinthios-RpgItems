# Attributes #

Attributes are the base of the entire plugin. They can do anything from increasing health, to giving you critical change, or even stealing your enemies health! Attributes are added to items via modifications and provide the user with different effects and bonuses. 

The descriptions here are for base mechanics the plugin provides. If you mess with formulas.yml you will mess with how these attributes affect combat.

## List of Attributes ##

* Health - Increases max health
* Damage - Increases damage when attacking entities
* PvEDamage - Increases damage against non-player entities
* PvPDamage - Increases damage against player entities
* Defense - Reduces incoming damage from entities
* PvEDefense - Reduces incoming damage from non-player entities
* PvPDefense - Reduces incoming damage from player entities
* CriticalChance - Provides a chance for users to deal critical damage (base 150% damage)
* CriticalDamage - Provides an increase to critical modifier (150% + CriticalDamage)
* DodgeChance - Provides a chance to negate damage
* BlockChance - Provides a chance to reduce damage by a flat amount
* BlockDamage - Reduces incoming damage when block takes effect
* MovementSpeed - Increases player movement speed
* Penetration - Reduces targets defense (or increases damage by a percentage)
* AttackSpeed - Increases player attack speed (not implemented)
* Vampirism - Provides a percentage of outgoing damage to heal the attacker
* Accuracy - Reduces chance for target to dodge
* BurnChance - Provides a chance to burn your target
* BurnDamage - increases burn damage when burn takes effect
* PoisonChance - Provides a chance to poison your target (custom poison deals damage to all entities including zombies)
* PoisonDamage - Increases poison damage done to target

### Heroes Specific ###

There are additional attributes added that work with the plugin Heroes. These are listed below, if you have a question about these attributes please look at Heroes documentation.

* Mana
* ManaRegeneration
* Stamina
* StaminaRegeneration
* Strength
* Constitution
* Endurance
* Dexterity
* Intellect
* Wisdom
* Charisma

## Configuration (attributes.yml) ##

Example configuration for reference
```
  Health:
    Enabled: true
    Display: '&aHealth'
    DisplayMaterial: COOKED_BEEF
    DefaultValue: 0.0
    IsDecimal: false
    IsPercent: false
```

Each attribute has an id, in this case 'Health'. **This id cannot be changed or it will break the health attribute in the plugin**. 

To disable an attribute use **Enabled: false**

* Enabled: (true/false) determines if the attribute is used in the plugin
* Display: (string) the way the attribute is displayed on an item when generated and also when reading an item
* DisplayMaterial: ([material](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/Material.html)) - The material of this attribute used in /lri stats
* DefaultValue: (decimal) What are the default stats you want players / entities to have? 
* IsDecimal: (true/false) Do you want stats to be flat integers or decimals?
* IsPercent: (true/false) Displays a % after the value in the lore and changes how some attributes act

## Other Notes ##

IsPercent namely affects MovementSpeed and Health. Other values are handled as a percentage in formulas.yml