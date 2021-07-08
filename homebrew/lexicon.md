---
title: Homebrew Lexicon
description: Directory of type schemata for homebrew
published: true
date: 2021-07-08T15:10:31.982Z
tags: homebrew, schema
editor: markdown
dateCreated: 2021-07-07T17:51:36.299Z
---

# Lexicon

This page serves as a directory and summary of keys and objects used to create a `.JSON` file for homebrew.

## A

`abbreviation`  - A **Key** type for homebrew
Abbreviated form of the source document, to display on the site.
> For example: `PHB` - Player's Handbook
> You should choose one that matches your source's name
{.is-info}

`action` - An Object type for homebrew
Reference for the mechanical economy of a creature's combat turn.

`adventure`  - An Object type for homebrew
A playable adventure. Should include maps, event descriptions, creatures, NPCs, items, etc.


## B

`background`  - An Object type for homebrew
A character background that gives proficiencies in skills/tools/languages and some starting equipment.


`book` - An Object type for homebrew
Books are a single file containing all of the content in a published reference such as rules, classes, fluff and descriptions.
> Books are different to `adventures`; which contain the expedition a party may go on and what they may find.
> Some books may even contain `adventures` in addition to the rest of their content.
> For example; the Player's Handbook is a `book`, while Curse of Strahd is an `adventure`
{.is-info}

`boon`  - An Object type for homebrew
Special rewards from powerful creatures for a character's service.


## C

`class` - An Object type for homebrew
Character class information, including progression, hit dice, starting equipment, class resources etc
> `class` does NOT include the detail of a `classFeature` or a `subclass`, only links to them. 
{.is-warning}

`classFeature` - An Object type for homebrew
Features such as Invocations, Fighting Styles, Metamagic, Maneuvers, Invocations, etc.


`collection` - An Organization Category
The organizational name for a homebrew that contains varied types of Objects.
> Collections can include `book`, `adventure`, `creature`, `item` and many other types of bjects. 
> They can even include multiple `book` or `adventure` objects, like a library. 
{.is-info}

`conditions` - An Object type for homebrew
Condition names and a description of their mechanical effects.

`creature` - An Object type for homebrew
This is the equivalent of a Stat Block; for both monsters and NPCs.


`cult` - An Object type for homebrew
An organization or guild, usually with a religious cohessive element

## D


`deity` - An Object type for homebrew
A god; usually with a description of their alignment, domains and pantheon.


`disease` - An Object type for homebrew
A description of a disease, ailment or illness and its mechnaical effect.


## E


## F
`feat` - An Object type for homebrew
Feats that can be chosen by a character

## G

## H
`hazard` - An Object type for homebrew
These are most often enviromental hazards and climate issues, though can also include traps.

## I
- [`item` *An Object type for homebrew*](/en/homebrew/lexicon/item)
{.links-list}

Items are the most complicated homebrew structures due to their broad scope which covers:
Magical & Mundane items, Trade Goods, Tool Kits, Mounts, Vehicles, Instruments, Weapons, Armour, etc.


## J

`json` - A **Key** type for homebrew (string)
An identifying string, as seen in the JSON in "source" fields.	
:::: FOUND IN: [[Homebrew:_Meta|_Meta]] Object


=====K=====
<hr>


=====L=====
<hr>

:: [[Homebrew:_Language |`Language`]]  - An Object type for homebrew
:::: Sets of written and spoken languages, who speaks them, what font they use, etc.



=====M=====
<hr>


:: [[Homebrew:_Magic Variant |`Magic Variant`]]  - An Object type for homebrew
:::: A playable adventure. Should include maps, event descriptions, Monsters, Items etc.


:: [[Homebrew:_Makebrew |`Make Homebrew's Monster Traits`]]  - An Object type for homebrew
:::: Extensible Sets of Monster trains and feature usable by the Homebrew builder.


:: [[Homebrew:_Meta tag |`Meta tag`]]  - An REQUIRED Object type that starts EVERY homebrew
:::: This is required for each JSON


:: [[Homebrew:_Monster |`Monster`]]  - An Object type for homebrew
:::: Bestiary - Monsters, NPCs and the like

=====N=====
<hr>

:: [[Homebrew:_Adventure `Adventure`]]  - An Object type for homebrew
:::: A playable adventure. Should include maps, event descriptions, Monsters, Items etc.



=====O=====
<hr>

:: [[Homebrew:_Adventure`Adventure`]]  - An Object type for homebrew
:::: A playable adventure. Should include maps, event descriptions, Monsters, Items etc.



=====P=====
<hr>

:: <code>"page"</code> — the page number of the document the information appears. If there's no page, leave it at 0.
:::: (Its a required field)

:: [[Homebrew:_Adventure`Adventure`]]  - An Object type for homebrew
:::: A playable adventure. Should include maps, event descriptions, Monsters, Items etc.



=====Q=====
<hr>


=====R=====
<hr>

:: [[Homebrew:_Adventure`Adventure`]]  - An Object type for homebrew
:::: A playable adventure. Should include maps, event descriptions, Monsters, Items etc.


:: [[Homebrew:_Adventure`Adventure`]]  - An Object type for homebrew
:::: A playable adventure. Should include maps, event descriptions, Monsters, Items etc.



=====S=====
<hr>

:: [[Homebrew:_Adventure`Adventure`]]  - An Object type for homebrew
:::: A playable adventure. Should include maps, event descriptions, Monsters, Items etc.

:: <code>"sense"</code> — Object keys are Sense names, which can referenced using {@sense <key>} (case insensitive).

:: <code>"skill"</code> — Object keys are Skill names, which can referenced using {@skill <key>} (case sensitive).

:: <code>"source"</code> — make sure it is the same as the <code>"json"</code> key in the <code>_meta</code>.

:: <code>"source"</code> — make sure it is the same as the <code>"json"</code> key in the <code>_meta</code>.

:: [[Homebrew:_MetaspellDistanceUnits | "spellDistanceUnits"]] — values should be objects with optional "singular" (singular form of the unit, e.g. "foot" for the singular of "feet"--if unspecified, a trailing "s" is removed from the plural version, if it exists, and the result is used as the singular form) and "feetPerUnit" (e.g. for a "yards" custom unit, this would be `3`, as there are three feet in a yard) key/values.

:: [[Homebrew:_MetaspellSchools | "spellSchool"]] — Object names are spell school abbreviations; values should be objects with "full" (used in the main entry, e.g. "Evocation") and "short" (used in the list view, e.g. "Evoc") key/values.

:: [[Homebrew:_Adventure`Adventure`]]  - An Object type for homebrew
:::: A playable adventure. Should include maps, event descriptions, Monsters, Items etc.


:: [[Homebrew:_Adventure`Adventure`]]  - An Object type for homebrew
:::: A playable adventure. Should include maps, event descriptions, Monsters, Items etc.

=====T=====
<hr>

:: <code>targetSchema</code> - The target schema version in 5etools, e.g. current schema version is v1.1.0.

:: [[Homebrew:_Adventure`Adventure`]]  - An Object type for homebrew
:::: A playable adventure. Should include maps, event descriptions, Monsters, Items etc.


:: [[Homebrew:_Adventure`Adventure`]]  - An Object type for homebrew
:::: A playable adventure. Should include maps, event descriptions, Monsters, Items etc.

:: <code>"time"</code> — here you can describe how long the action takes. <code>"unit"</code> can be "action", "bonus" or "reaction". <code>"number"</code> is the amount of units it takes. If it does not apply to the action, you can delete this block.


=====U=====
<hr>
:: <code>url</code> - A direct link to the source, if available in web form or on a store.


=====V=====
<hr>

:: <code>version</code> - The source version.


:: [[Homebrew:_Adventure`Adventure`]]  - An Object type for homebrew
:::: A playable adventure. Should include maps, event descriptions, Monsters, Items etc.


:: [[Homebrew:_Adventure`Adventure`]]  - An Object type for homebrew
:::: A playable adventure. Should include maps, event descriptions, Monsters, Items etc.



=====W=====
<hr>


=====X=====
<hr>


=====Y=====
<hr>


=====Z=====
<hr>
