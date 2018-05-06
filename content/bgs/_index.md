+++
title = "Blox Game Systems"
chapter = true
weight = 10
pre = "<b> </b>"
+++

# Blox Game Systems

[<i class="fa fa-cart-arrow-down" aria-hidden="true"></i> Asset Store](https://assetstore.unity.com/publishers/380)
&nbsp;&nbsp;|&nbsp;&nbsp;
[<i class="fa fa-youtube" aria-hidden="true"></i> Videos](/tutorials/)

Blox Game Systems (BGS) is a core system which provide features to game-genre specific plug-ins. It can also be used stand-alone if you are only interested in the features it presents. The goal of this tool is to provide a no-coding required environment but that can only be achieved fully if you install one of the game-genre specific plug-ins.


#### Requirements

- Scripting runtime .NET 4.x
- TextMesh Pro (free)
- DOTween (free)


#### Supported Build Targets

- Windows, OSX, and Linux are the only platforms officially supported. Other may work but please inquire on the [forum](http://forum.plyoung.com/) first and note that I can not necessarily provide help if something does not work well on that platform. This applies to BGS plug-ins too.


#### Features

- Most of the components and systems dealing with game mechanics are provided via scripts in the Unity project so that you have access to the source to make changes or learn from when creating your own or derived classes. These script are all associated with [assembly definitions](https://docs.unity3d.com/Manual/ScriptCompilationAssemblyDefinitionFiles.html) to reduces compilation time. BGS plug-ins normally provide the full source to the plug-in scripts since they generally deal with game mechanics. The BGS core systems (variable system, game data editor, persistence system, and various other editors) are provided via DLLs and the source is not available.
- [Bootstrap](bgs/bgs-mained/bgs-mained-main/): manage game startup and auto-loading of scenes. This also works while testing in Unity so that required scenes are auto-loaded when testing a scene you are working on.
- [Persistence System](/bgs/bgs-mained/bgs-mained-main/#persistence): is used to save and load player sessions in-game. 
	+ Save data to Json (text) or a Compressed format files in the [persistent data path](https://docs.unity3d.com/ScriptReference/Application-persistentDataPath.html) location provided by Unity.
	+ Support for player profiles and any number of separate Save Slots per profile.
	+ UI components for profile creation/selection, saving, and loading makes it easy to create these UI without code.
- [Variables System](/bgs/bgs-vars/): provides a way to add data quickly without writing scripts. It supports Lists, various primitive types, and most of the Unity types. Changes to the these variables' values can also be saved and restored at runtime where applicable.
	+ Global Variables gives access to globally unique data.
	+ Meta Properties provides a way to add data on to objects.
	+ Blackboard and Blox variables are normally provided by systems where needed to allow a way to add data to these systems or have access to a place to store temporary data created at runtime.
- [Game Data System](bgs/bgs-gamedata/): is used to define your own game data types/ definitions and then add values to these definitions.
	+ You can select from almost any type available, from the primitives like integer and string, to the unity types like Vector3 and Sprite. 
	+ Generic types are not supported but there is an option to create lists.
	+ The editor will generate the C# scripts for the data definitions you defined.
	+ It auto-creates and manages the associated assets for you.
	+ You can define these types:
		* "basic" which are only there to be used in other definitions.
		* "single" which are basically ScriptableObject.
		* "list" which allows you to add a list to of data entries to a definition.
		* "group" is basically the same idea as list but the lists can be grouped. It provides a way to organize data when you know there will be a lot of data entries added to the definition.
	+ It ties in with the Persistence System to allow saving and restoring values changes at runtime.
- [FlowGraph](bgs/bgs-flowgraph/): A node based editor for creating dialogue/conversation or to support other systems which needs to get/set values. It is not a full blown visual scripting system but does have nodes to perform logical operation like conditional checks or to do mathematics. It can get and set values from various systems like the Variables or Game Data systems. It's main purpose is to build story flow via Graphs containing Nodes. It also has two other types of Graphs for getting values or setting values (performing short actions). These are used by systems which need to get or set values in other parts of BGS. The UI updaters for example uses these type of FlowGraphs.
	+ Nodes to perform conditional checks and branch the flow.
	+ Mathematics and graphed values.
	+ Dialogue, buttons, and generic panels related nodes used in building dialogue/ conversation.
	+ Getters and Setters for BGS Variables, Game Data, and member properties/fields.
	+ Execute methods.
	+ Interact with Unity (start animation, create/destroy objects, etc)
- [Components](bgs/bgs-components/):
	+ Sound volume control system with volume categories and a component which will auto-update Sound Sources set to these categories via attached component.
	+ Helpers to set objects to not destroy, follow an object, or auto-disable.
- [UI components](bgs/bgs-components-ui/):
	+ UI Updaters are used to automatically get/set UI values on the UI. For example when updating a slider with values changing in a Variable or when you want to save the name a player entered to a Global Variable (automatic as player types after you set it up).
	+ UI Window/Panel Manager to easily switch active panels without scripting.
	+ Helper UI elements to easily update settings/ options like resolution, quality, and sound volume.
	+ Dialogue, Button, and Generic panel components for use by the associated FlowGraph nodes (for example to show a conversation with a character).
	+ Profile, Save, and Load panel components for handling UI around player session saving and loading (persistence).


#### Planned features (in development)

- Localization system (short term)
- Blox Visual Scripting (long term)