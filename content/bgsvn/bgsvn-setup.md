+++
title = "Setup"
weight = 2
+++

There is a [<i class="fa fa-youtube" aria-hidden="true"></i> video tutorial](https://www.youtube.com/playlist?list=PLuaBtUXEKcdK9UtD8rx3tYMfLzPRawwOV) covering the creation of a Visual Novel game with BGS.

It is assumed that you have read the [documentation for Blox Game Systems](/bgs/) before you continue with the documentation for this plug-in.

### Requirements

All [requirements listed for BGS](/bgs/bgs-setup/#requirements) must be met.

**Packages**

This plug-in requires the following packages:

- [Blox Game Systems](https://assetstore.unity.com/publishers/380): Core system.
- [TextMesh Pro](https://assetstore.unity.com/packages/essentials/beta-projects/textmesh-pro-84126): UI text rendering.
- [DoTween](https://assetstore.unity.com/packages/tools/animation/dotween-hotween-v2-27676): Tweening/ animation.

### Misc Settings

Remember to do a Data Check after adding this plug-in, as required with all BGS plug-ins `menu: BGS > Check Game Data`. The VN Engine adds new Sorting Layers. These can be seen in the Tags and Layers Inspector `menu: Edit > Project Settings > Tags and Layers`.

There should be Sorting Layers for:

- Background: The background sprites are placed in this layer so that they render behind characters.
- Character: The character sprites are placed in this layer.
- Foreground: A layer which an be used on sprites which should render in front of characters.

### Main Controller

The VN Engine adds a new component `menu: Component > BGS  > VN > VN Engine`. This must be placed on a GameObject of your main Unity scene and controls various aspects of the engine. 

There will normally be only one Unity scene which contains the main controller and your UI. All dialogue and story is created in the FlowGraph editor and you point to the start of your VN (the graph to start with) via the main controller.

- Game Graph: This is the graph to execute when a new game is started. The VN engine can be instructed to start a new game via the `VN Engine > Start New Game` FlowGraph node.
- VN Camera: The main 2D camera. Used when calculating what the size of a background image should be for example.
- Menu UI: The GameObject containing the "main menu" of your game.
- In Game UI: The GameObject containing the "in-game" UI of the game (ex. the the dialogue panels). When a new game is started (or game session restored) the main menu is set inactive while this GameObejct will be activated.
- Menu Song: A song which will be started when the menu is shown. This song will be stopped when the story FlowGraph is started via new game or loading of a previous session.
- Blackboard: The [Blackboard](/bgs/bgs-vars/) accessible to graphs executed by the VN Engine.

### FlowGraph

The VN Engine nodes can be found under the `VN Engine` category.

The VN Engine adds a new [Test Scene] button to the FlowGraph toolbar. Use this to quickly test the active Global FlowGraph. It is like pressing the Unity play button so the scene with the VN Engine controller in it should be open. You may also use the drop-down to choose whether the graph should execute from the Start node or from the currently selected node. Keep in mind that there could be errors if you choose to execute from a node which depends on previous nodes having made changes to the scene.

### Main Editor

The VN Engine adds a new tab to the main editor where some settings can be changed and data defined.

**Settings**

- Pixels per Unit: This should be the same as the value used with imported sprites. The Unity default is 100.
- Design Size: The screen resolution you are designing the game at. Normally the same aspect ratio as background images you will be using.
- Scene Border: Determine what the characters and other elements will consider as the scene border/ edge when being repositioned in the scene.

**Characters**

Here you define the characters who will appear in the scene. The `VN Engine > Character Action` FlowGraph node will be used to access this list of characters. This action can make a character enter or exit a scene and change the character's pose.

Press the [+] to add a new character definition. If there are no groups yet you will first create a group where new character can be added to. The name you give a character must be unique and is the name you will see in other areas of the editor, for example the Character Action node's Inspector. It is not a name shown in the game UI.

Add a character prefab to complete the setup of a new character.

![Character](/images/bgsvn/00.png?height=120px&classes=inline,border,shadow)

Characters are GameObject containing sprites which represents the various poses of that character. The main object will normally have no components attached and then contain one or more GameObjects, each with a SpriteRender. The "pose" objects may contain further child objects with SpriteRenderers if the pose is built from various sprites. You do not have to setup the layer options of the SpriteRender since the VN Engine will take care of these when the character is shown.






