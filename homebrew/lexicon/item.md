---
title: Homebrew: item
description: Homebrew Schema for the "item" type
published: true
date: 2021-07-07T18:01:39.233Z
tags: homebrew, schema
editor: markdown
dateCreated: 2021-07-07T17:45:56.188Z
---

# Building an item

As with any Homebrew item, make sure you have reviewed the [\_meta](/en/homebrew/lexicon/meta) section. If your file doesn't have it, it won't work.

## Basic skeleton
To start, copy the following code block and fill the empty `""` values.

```json
"item": [
    {
        "name": "",
        "source": "",
        "page": "",
        "type": "",
        "rarity": "none",
        "entries": [
            ""
        ]
    }
]
```
- `"name"` — the name of the item.
- `"source"` — make sure it is the same as the `"json"` key in the `_meta`.
- `"page"` — the page of the document where this item appears. If this does not apply, leave at 0.
- `"type"` — the type of the item. See the table below for all the different options.
- `"rarity"` — "None" is for mundane items. "Unknown (Magic)" is for miscellaneous magical items. "Unknown" is for miscellaneous mundane tems. "Varies" is for item groups.
- ```"rare", "none", "uncommon", "very rare", "legendary", "artifact", "unknown", "common", "unknown (magic)", "varies"```
- `"entries"` — the text of the item. You can write several strings ("") separated with a comma. If the item doesn't have any associated text, it is safe to remove.

## Adding info text or image
To add an image to an item, you need to use a **direct link**.
```json
"fluff": {
    "entries": [
        ""
    ],
    "images": [
        {
            "type": "image",
            "href": {
                "type": "external",
                "url": "example.com/image.jpg"
            }
        }
    ]
}
```

## General Tags
### Ability Score Adjustments
Some items will modify the ability scores of a player. They can increase the score a certain amount:
 "ability": {
     "str": 2
 }
It is possible to change the score into a static amount:
 "ability": {
     "static": {
         "con": 19
     }
 }
===Age===
The only current official ones are "modern"and "renaissance", but any string can be used. it will show up as a "Type" filter.
 "age": "modern"
===Attached Spells===
Useful for filtering purposes, write the name of any spell that the item allows to cast separated by commas.
 "attachedSpells": [
     "cone of cold",
     "ice storm"
 ]
===Bonuses===
Some items offer certain bonuses, either defensive or offensive ones.
 "bonusSpellAttack": "+1"
:*`"bonusAC"` — extra Armor Class.
:*`"bonusWeapon"` — weapon attack '''AND''' damage rolls.
:*`"bonusWeaponAttack"` — only weapon attack rolls.
:*`"bonusWeaponDamage"` — only weapon damage rolls.
:*`"bonusSpellAttack"` — spell attack rolls.
:*`"bonusSavingThrow"` — saving throws.
===Carrying capacity===
How many pounds a Mount (or similar) can carry.
 "carryingCapacity": 120
===Charges===
Some items have charges that power their special abilities
 "charges": 3
These charges can be regained after a certain amount of time. Choose between `"round"`, `"restShort"`, `"restLong"`, `"dawn"`
, `"dusk"` or `"midnight"`.
 "recharge": "dawn"
===Container Capacity===
This defines the capacity of a container such as a backpack or bag. Both weight and item capacity can be specified.
 "containerCapacity": {
     "weight": [
         6
     ],
     "item": [
         {
             "sling bullet|phb": 20,
             "blowgun needle|phb": 50
         }
     ],
     "weightless": true
 }
:*Note that `"weight"` is an array, if the container has more than one pocket defined (e.g. Handy Haversack) you can write more weights.
:*When linking an item, remember to add the source of it at the end after `|`. The number is the max amount of items it can store.
:* `"weightless: true` is an optional line for objects that render their contents weightless, no matter how heavy they are (e.g. Bag of Holding). The container will always weight the same amount.
===Cursed Items===
Some magic items bear curses that bedevil their users, sometimes long after a user has stopped using an item.
 "curse": true
===Damage resistance===
Enter the type of damage the item gives you resist to.
 "resist": "cold"
===Item Tier===
A distinction mainly used in the DMG that separates `"major"` and `"minor"` Magic Items.
 "tier": "major"
===Loot Tables===
This will add a handy link to the loot table in which the item appears on. The source is assumed to be DMG, but if using other sources such as homebrew files, add it with a pipe "|".
You can add more that one table as different entries separated with commas.
 "lootTables": [
     "Draconic Items|Dragoons"
 ]
===Pack Contents===
When building an item that contains other items, such a bundle of ammunition or a gear pack, you can define the items that it contains. Very useful for importing into VTTs.
 "packContents": [
     "backpack|phb",
     {
         "item": "torch|phb",
         "quantity": 3
     },
     {
         "special": "wooden stake",
         "quantity": 3
     }
 ]
:*The first is a simple single item, remember to add the source of the item using a pipe `|`.
:*The second item has a `"quantity"` that you can define.
:*The third option is for "special" items, those that do not exist as such in the 5eTools data. Add whatever text you see fit. The `"quantity"` is optional.
===Poison===
If the item is a poison, add the following.
 "posion": true
The type of poison can be specified. Choose between injested, injury, inhaled or contact (accepts custom types).
  "poisonTypes": [
     "injested",
     "pill"
 ]
===Requires Attunement===
If anyone can attune with the item, use `"true"`.
 "reqAttune": true
The item may only be attunable by a certain class/people. Can handle any string.
 "reqAttune": "by a bard"
It is possible that the attunement is optional.
 "reqAttune": "optional"
===Spellcasting Focus Types===
Choose between `"arcane"` (Sorcerers, Warlocks and Wizards), `"holy"` (Clerics and Paladins) or `"druid"` (Druids)
 "sfcType": "arcane"
For other items that work as spellcasting focus for any class, you can add the following:
 "focus": true
If it only works for certain classes:
  "focus": [
     "Sorcerer",
     "Warlock"
 ]
===Speed===
The top speed of mounts and vehicles
 "speed": 50
===Value===
Monetary value of the item. Use copper pieces.
 "value": 1000
An item can also have a multiplier as value, like Barding. Will render as "x4".
 "valueMult": 4
===Weight===
Specify the weight in pounds.
 "weight": 10
An item can also have a multiplier as weight, like Barding. Will render as "x2".
 "weightMult": 2
Text can be added as a note next to the weight of an item, useful for containers. Will render between parenthesis.
 "weightNote": "full"
===Wondrous Items===
A tag for all items considered Wondrous
 "wondrous": true

==Weapon tags==
===Ammunition===
For items that '''use''' ammunition, not the ammunition items themselves.
 "ammunition": true
===Category===
Differentiate between Simple, Martial or other categories of weapons.
 "weaponCategory": "Simple"
===Damage===
The damage dice of a weapon is declared as follows.
 "dmg1": "1d8"
For Versatile weapons or those that offer an alternative damage dice, a second one can be defined.
 "dmg2": "2d6"
Finally, declare the type of damage the weapon deals. For all the different damage types, see the table at the bottom of the page.
 "dmgType": "S"
===Range===
Define the range of a ranged weapon.
 "range": "80/320"
===Reload===
The amount of shots before the weapon needs to be reloaded.
 "reload": 5
 
==Armor tags==
===Armor Class===
The base Armor Class the item provides.
 "ac": 12
There is also a free text version of this:
 "acSpecial": "12 AC, 15 AC during the night"
===Stealth Disadvantage===
Mainly used for Heavy Armors, displays a text explaining this drawback.
 "stealth": true
===Minimum Strength===
The minimum Strength value a character needs to not be slowed when wearing the item.

This will result in a line saying "If the wearer has a Strength score lower than x, their speed is reduced by 10 feet."
 "strength": 15

==Vehicles==
The following will help you create an item-type vehicle, like those present in the DMG. For the type seen in GoS and BGDIA, with Ability Scores and Features, see [[Homebrew:_Vehicles|Vehicles]]
===Crew===
The crew can be defined as a static number.
 "crew": 10
It can also be specified as a X-Y min-max
 "crewMin": 5,
 "crewMax": 15
===Carrying capacity===
Specify the amount of passengers the vehicle can carry
 "capPassenger": 30
It also works for cargo, specified in pounds.
 "capCargo": 500
===Speed - Hit Points and AC===
The speed is measured in miles per hour. A damage threshold can also be defined.
 "vehSpeed": 1
 "vehAc": 15,
 "vehHp": 100,
 "vehDmgThresh": 10
===Costs===
Personal travel cost is measured per mile and per passenger. The shipping cost is measured per 100 pounds per mile. Both costs are specified in copper pieces.
 "travelCost": 200,
 "shippingCost": 100


==Extra tables==
<div><ul>
<li style="display: inline-table;">
{| class="wikitable sortable"
|+ Item types
|-
! Code !! Meaning
|-
| "A"|| Ammunition
|-
| "AF"|| Ammunition (futuristic)
|-
| "AT"|| Artisan Tool
|-
| "EM"|| Eldritch Machine
|-
| "EXP"|| Explosive
|-
| "G"|| Adventuring Gear
|-
| "GS"|| Gaming Set
|-
| "HA"|| Heavy Armor
|-
| "INS"|| Instrument
|-
| "LA"|| Light Armor
|-
| "M"|| Melee Weapon
|-
| "MA"|| Medium Armor
|-
| "MNT"|| Mount
|-
| "GV"|| Generic Variant
|-
| "P"|| Potion
|-
| "R"|| Ranged Weapon
|-
| "RD"|| Rod
|-
| "RG"|| Ring
|-
| "S"|| Shield
|-
| "SC"|| Scroll
|-
| "SCF"|| Spellcasting Focus
|-
| "OTH"|| Other
|-
| "T"|| Tool
|-
| "TAH"|| Tack and Harness
|-
| "TG"|| Trade Good
|-
| "$"|| Treasure
|-
| "VEH"|| Vehicle (land)
|-
| "SHP"|| Vehicle (water)
|-
| "AIR"|| Vehicle (air)
|-
| "WD"|| Wand
|} </li>
<li style="display: inline-table; margin-left:30px;">
{| class="wikitable sortable"
|+ Damage types
|-
! Code !! Meaning
|-
| "A"|| Acid
|-
| "B"|| Bludgeoning
|-
| "C"|| Cold
|-
| "F"|| Fire
|-
| "O"|| Force
|-
| "L"|| Lightning
|-
| "N"|| Necrotic
|-
| "P"|| Piercing
|-
| "I"|| Poison
|-
| "Y"|| Psychic
|-
| "R"|| Radiant
|-
| "S"|| Slashing
|-
| "T"|| Thunder
|-
|} </li>
<li style="display: inline-table; margin-left:30px;">
{| class="wikitable sortable"
|+ Properties
|-
! Code !! Meaning
|-
| "T"|| Thrown
|-
| "V"|| Versatile
|-
| "H"|| Heavy
|-
| "2H"|| Two-Handed
|-
| "F"|| Finesse
|-
| "L"|| Light
|-
| "R"|| Reach
|-
| "A"|| Ammunition
|-
| "LD"|| Loading
|-
| "S"|| Special
|-
| "AF"|| Ammunition (futuristic)
|-
| "RLD"|| Reload
|-
| "BF"|| Burst Fire
|-
|} </li>
</ul></div>

==Reference Tag==
How to link to entries within the `"entries":`
::`{@item <name_of_item>|<json_source>|<optional_text>}`

:: Example:
:::{@item alchemy jug}
:::{@item longsword|phb}
:::{@item longsword|phb|and optional link text added with another pipe}
----
<div style="font-weight:bold;line-height:1.6;font-size:140%">🗄️ Reference Files:</div>
:: [https://raw.githubusercontent.com/TheGiddyLimit/TheGiddyLimit.github.io/master/test/schema/items.json 🛢️ Requirements Specs (Schemata)]
:: [[ |🧾 Blank Template]]
:: [https://raw.githubusercontent.com/TheGiddyLimit/homebrew/master/item/Sample%20-%20Giddy;%20Hook%20of%20Butchery.json 📖 Sample JSON]
:: [[ |💾 Functional Example]]
:: [https://github.com/TheGiddyLimit/homebrew/tree/master/item 📚 Repository of Other Examples]
----


==Homebrew Support==
----
<div class="toccolours mw-collapsible mw-collapsed" style="width:600px; overflow:auto;">
<div style="font-weight:bold;line-height:1.6;">Known Issues</div>
<div class="mw-collapsible-content">
:: Looks like its perfect... (Did we miss anything?)
<br/>
:: '''NAME OF THE ISSUE'''

:::: <font color="#2e7bab">Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.</font>

:::: <font style="font-weight: bold; font-variant: small-caps"> Work Around </font> : <font style="font-variant: small-caps">Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</font>
<br/>
</div>
<div style="font-weight:bold;line-height:1.6;">FAQ</div>
<div class="mw-collapsible-content">
:: Nothing's here (Do you have any suggestions?)
</div>
<div style="font-weight:bold;line-height:1.6;">Best Practices</div>
<div class="mw-collapsible-content">
:: None as yet (Do you have any suggestions?)
</div>
</div>

<br/>
----
==Related Features==
----
:*[[Homebrew]]
:*[[]]
:*[[]]

<br/>
{{FeatureSupport}}
