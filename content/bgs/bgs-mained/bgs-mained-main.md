+++
title = "MainEd: Main"
weight = 10
+++

The main section is where most of BGS' settings are defined.

### Startup & Scenes

![Startup & Scenes](/images/main-ed/00.png?height=100px&classes=border,shadow)

This is where you manage what scenes are part of the game and how they are loaded. Scenes can be added here or via the Build Settings window. You may click on a scene in this window to quickly open that scene in Unity.

BGS requires the `Assets/projectData/Scenes/00-bootstrap` scene to be first in the build list. This scene is responsible for loading other scenes and global prefabs. Do not edit or move this scene. Your own scenes may follow after the bootstrap scene.

You will note two buttons in front of scene button (name). The 1st is used to tell BGS which scenes should be loaded when the game is run and in what order. This is for a build of the game and not while testing in editor, although the BGS Play Button, or `menu: BGS > Start Game`, will honor this startup order since it is used to test a "typical flow" of the game.

The second button is used to tell BGS which scenes should be treated specially.

Setting a scene to **auto-load** will cause the scene to auto-load when you test a game scene via the Unity Play button. This is useful when the scene you are about to test has dependencies on GameObject defined in another scene. This other scene can be auto loaded by BGS if you mark it with this button.

The **loading screen** option tells that the scene should be shown as soon as the bootstrap is loaded, after the splash screen, and stay up until loading of all scenes are completed and then be unloaded. This is a way to show something on screen while the game is taking long to complete loading resources. You should not set objects in this sene to "not destroy on load" else those objects will not auto-unload when the scene is unloaded, except of course if you have a reason to do so.

### Main Settings

![Main Settings](/images/main-ed/01.png?height=100px&classes=border,shadow)

This section contains various settings needed by other systems of BGS.

- Auto-load Bootstrap: Should the bootstrap auto-load when the Unity play button is pressed? You normally want to keep this on so that bootstrap can load auto-load scenes and global prefabs but the option is here to prevent this loading if you need it.
- Minimum Resolution: The minimum screen width and height that will be presented by the Settings Manager.
- Namespaces & Classes: The namespaces and classes to scan whenever looking for members. For example during member binding or when displaying a list of members that can be turned into Blocks.

### Persistence

![Persistence](/images/main-ed/07.png?height=100px&classes=border,shadow)

The persistence system is what is used to save and load player game sessions in-game (at runtime). It supports player profiles and makes use of save slots unique per player profile. Player profiles are optional however and if you do not set an active profile, via help of the Profiles Panel, then the default will simply be active.

There are [UI components](/bgs/bgs-components-ui/#persistence) you can use to help in building an interface for profiles, save panel, and load panel. This is the preferred way of building the UI around this system.

Many systems tie into this one and provide automatic saving and restoring of data while you simply have to select what can be saved, where applicable (like in case of Variables and Game Data systems).

This system save data to a folder provided by Unity. This location will depend on what platform the game is running and is provided by the Unity property, [persistentDataPath](https://docs.unity3d.com/ScriptReference/Application-persistentDataPath.html). You can see the path that will be used while running the game in the editor (note that this location might differ for stand-alone builds). You can also quickly open the location in the OS file browser by clicking on [Open Location].

Save data can get corrupt if you saved a play session and then made a lot of changes to the game. In this case you will want to delete all save data via the [Delete All Saves] button; or by simply deleting the folder the saves files are stored in.

- Compression: You can select whether the save data should be compressed or not. When compression is selected the data will be saved in an unreadable compressed format. If you select none then the data will be saved as plain text in a Json format. This format is relatively easy to read and can help with debugging problems in the save data.
- Formatting: Available when no compression selected. Determines how "pretty" the Json is formatted.
- Screenshots: Do not enable this if you will not be showing a thumb in the UI for save slots. This takes up extra space and makes saving slower while a screenshot is taken a and saved.

### Global Variables

![Global Variables](/images/main-ed/02.png?height=100px&classes=border,shadow)

Here you can define what Global Variables are present in the game. This is the same as editing the component found on the `Assets/projectData/GameGlobal` prefab.

Refer to the [section on variables](/bgs/bgs-vars/) to learn more about BGS' variables.

### Attribute Defs

<!--![Attribute Defs](/images/main-ed/03.png?height=100px&classes=border,shadow)-->

_This is not currently used_