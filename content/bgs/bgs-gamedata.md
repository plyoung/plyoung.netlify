+++
title = "Game Data"
weight = 21
+++

![GameData](/images/gamedata/00.png?classes=border,shadow)

The Game Data editor allows you define almost any kind of data your game might require without writing scripts.

It allows you create Game Data **Definitions** in a visual manner by choosing names and types for fields of the new definition (game data type). The editor then generate a script for your new define type (game data definition). The scripts are stored in `Assets\projectData\Scripts\GameData`. You should not edit these scripts since your changes will be lost if you use the Game Data editor and it needs to update the script.

The same editor can then be used to add data entries to this newly created definition. This data is stored in assets located in `Assets\projectData\Resources\GameData`. These assets should not be renamed or moved.

The Game Data definitions can be accessed via other systems, like the FlowGraph or Blox. It also ties in with the persistence system to provide auto saving/ loading of field values where you indicated such data should take part in persistence.

It is a powerful, yet simple to use, system and editor. The difficult part will be deciding on what kind of data you need and how it should be organized and presented in the editor.

### Definition List

![GameData](/images/gamedata/01.png?classes=border,shadow)

You will see a list of all your data definition in the list to the left-hand side of the editor. Use the [+] button to add a new definition. You will first need to add a group for the definition if there are not any groups yet.

When you click the add or edit buttons you will be presented with a window to edit the game data definition. Here you may enter a name and select what kind of game data it is. Note that you can not change the game data type after the game data definition has been created, so first think about what the data is you are creating and choose carefully what type it will be. The name can be changed but it is advised that you do not depend on doing this often since it might require updates in other game data definitions (if they make use of this one) or even other systems, like the FLow Graph node which accesses the data. The point is, there are many things that might depend on the definition after you start using it and, even though great care is taken to update everything internally, it might still lead to bugs if you change the name after (*please report on support forum if this happens*).

**Asset (or definition type)** is where you select what kind of game data it is.

- None: This means you are not creating an asset (a definition you can directly add data to) but rather a type that will be used when adding fields to other definitions. This is here in case you want to group certain data for whatever reason.
- Single: This is the simplest data type and will allow you do edit data related to fields you added to this definition. This is a good choice for data which represents a singular thing, for example a Player's data.
- List: You will use this when you want to create more than one piece of data related to this definition. For example, you might define the Character Classes used in your game. There might be a Mage, a Warrior, and a Rogue. These are all separate pieces of data/ entities but they share similar fields. So you would want to create one definition which can hold a list of these classes.
- Grouped: This is similar to List but allows you to group the lists. This is useful when you will be creating a large amount of entries and it makes sense to group these entries in some way. For example if you created a definition to hold a list of all Sprites used in the game and want to group it to Player sprites, Monsters sprites, and NPC sprites.

**Options** 

- Static: Choose this option if the data is considered to be "static" and will not take part in the persistence system. You can still use this definition in fields of other and even persists data via the other definition if that one is set to persists. Therefore you will see the option to select which fields to persist (*P* icon next to field name).
- Sorted: This allows you to choose whether list/ grouped data should auto sort by entry Ident (name) or not. If not enabled then you will be able to move entries around in the list.
- Meta properties: Should meta properties be enabled and available when editing data for this definition. You will rarely need to use this.
- Runtime persistence: Should this data definition take part in persistence, have runtime/ in-game changes to fields of its data entries saved and restored? You have the option to select which fields should be saved by toggling the "P" icon next to the field name to blue (enabled) or black (disabled). A gray icon means the field is of a type which can not be persisted.

**Fields**

Here to define what fields/ properties the definition contains. Fields are what holds data/ values. The type you select will depend on what type of data you are trying to create. A "player name" for example would be of type "String", while "health points" or "experience" would be "Integer", and a toggle/ flag would be of type "Boolean". 

The Unity types like Sprite and GameObject (prefab) can be found under the UnitYEngine group. The easiest way to quickly find there is to type the name in the search field since there are a lot of types defined in the unityEngine group.

You can even select other definitions to be used for fields. These can be found in the "GameData" group when looking for a type.

The types you see listed in the Type Selection will depend on what namespaces or types are selected in the [Main Settings](/bgs/bgs-mained/bgs-mained-main/#main-settings). By adding the namespaces for other tools there you will be able to select types from them in this window. Please ask on the support forum if you are not sure how to gain access to a type from another Unity asset.

![GameData](/images/gamedata/02.png?classes=border,shadow)

### Editing the Data

Selecting a definition will present a way to add and edit data related to the definition. If you create a list or group type data definition then you will be presented with another list where you can add new data entries. Selecting any of these entries will present you with the fields where you can enter data for that entry.

