+++
title = "Blox Game Systems"
chapter = true
weight = 10
pre = "<b> </b>"
+++

# Blox Game Systems

[<i class="fa fa-cart-arrow-down" aria-hidden="true"></i> Asset Store](https://assetstore.unity.com/publishers/380)
&nbsp;&nbsp;|&nbsp;&nbsp;
[<i class="fa fa-youtube" aria-hidden="true"></i> Videos](https://www.youtube.com/playlist?list=PLuaBtUXEKcdJFTn_N5rG7CQZfB57dcQDy)

Blox Game Systems (BGS) is a core system which provide features for game-genre specific plug-ins. It can also be used stand-alone if you are only interested in the features it presents. The goal of this tool is to provide a no-coding required environment but that can only be achieved fully if you install one of the game-genre specific plug-ins.

#### Features

- BGS Variables system allows you to add data/properties to objects without writing a script via the Meta Properties component.
- Global Variables for easily defining and accessing global data/ properties.
- Sound volume control system with volume categories and a component which will auto-update Sound Sources set the categories.
- Bootstrap: manage game startup and auto-loading scenes. This also works while testing in Unity so that required scenes are loaded when testing a scene you are working on.
- Attributes System: mainly as a support system for plug-ins. This can be used to define character stats and how they influence each other's values via graphs and formulas to auto update when one value changes.
- FlowGraph: A node based editor for creating dialogue/conversation or to support other systems which needs to get/set values. It is not a full blown visual scripting system but does have nodes to perform logical operation like conditional checks or mathematics. It can get and set values from various systems like the BGS Variables. It's main purpose is to build story flow via Graphs containing Nodes. It also has two other types of Graphs for getting values or setting values (performing short actions) - these are used by systems which need to get or set values in other parts of BGS. The UI updaters for example uses these type of FlowGraphs.
- UI components
	+ UI Updaters are used to automatically get/set UI values on the UI. For example when updating a slider with values changing in a Variable or when you want to save the name a player entered to a global variable (automatic as player types after you set it up).
	+ UI Window/Panel Manager to easily switch active panels without scripting.
	+ Helper UI elements to easily update settings like resolution, quality, and sound volume.
	+ Dialogue, Button, and Generic panel components for use by the associated FlowGraph nodes (for example to show a conversation with a character).

#### Planned features (in development)

- Player Session system for loading/saving (short term)
- Localization system (short term)
- Blox Visual Scripting (long term)
- More game genre specific plug-in (long term)

#### Supported Build Targets

- Windows, OSX, and Linux are the only platforms officially supported. Other may work but please inquire on the [forum](http://forum.plyoung.com/) first and note that I can not necessarily provide help if something does not work well on that platform. This applies to BGS plug-ins too.
