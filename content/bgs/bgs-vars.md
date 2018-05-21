+++
title = "Variables"
weight = 20
+++

Blox Game Systems includes a variables systems which helps you to define data/ values to be used in the game.

![P-icon](/images/vars/01.png?classes=inline,border) Some variables can be saved and restored via the [persistence system](/bgs/bgs-mained/bgs-mained-main/#persistence). Only certain types of variable values can be saved via the persistence system. The UnityObject, Prefab, GameObject, and Component types can not be saved during a game session. A small **"P"** icon next to the variable can be toggled to indicate whether the variable entry should take part in persistence. Change it to a blue icon to enable, or black to disable. A gray icon means it can not be toggled and will not take part in persistence.

### Variable Groups

The variables are defined as certain groups of variables; Global Variables, Blackboard, Meta Properties, Blox Variables, and Blox Event Variables. The group used will depend on where it is needed.

**Global Variables**

These variables are global to a game session. There is only one set of Global Variables and is useful for unique values, for example a player's name. Global variable can be defined in the [Main Editor](/bgs/bgs-mained/bgs-mained-main/#global-variables).

These variables can be saved and restored via the persistence system.

**Meta Properties**

Meta properties can be added to GameObject via the `menu: Component > BGS > Data > Meta Properties` component. The meta properties of an object is unique to that object. Some systems might include their own sets of meta properties, for example FlowGraph graphs, or an attribute in the Attributes system.

These variables can be saved and restored via the persistence system.

**Blackboard**

Blackboards are normally available on systems which will be executing FlowGraph graphs. These include systems like the UI updaters, VN Engine's main component, etc. The Blackboard will be on the component and you can add and edit variables as needed. Blackboard can normally add new variables as needed if not predefined.

These variables *might* be saved and restored via the persistence system. It depends on how they are used. The VNEngine component, in the VN Engine plug-in, save and restore the values of its Blackboard for example.

**Blox Variables**

_These are not yet available and will be part of the Blox Visual Scripting system._

**Blox Event Variables**

_These are not yet available and will be part of the Blox Visual Scripting system._

### Variables Editor

![Variables](/images/vars/00.png?height=100px&classes=border,shadow)

All variables that can be defined using the same visual editor. 

The [+] button is used to add a new variable. This will bring up a window where you can enter a unique name for the variable and choose the type of value it will hold. Variable names must be unique per group of variables. The name can be edited the variable is defined but type can not be changed.

