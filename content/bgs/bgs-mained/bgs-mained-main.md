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

The second button is used to tell BGS which scenes should be auto loaded when you test a game scene via the Unity Play button. This is useful when the scene you are about to test has dependencies on GameObject defined in another scene. This other scene can be auto loaded by BGS if you mark it with this button.

### Main Settings

![Main Settings](/images/main-ed/01.png?height=100px&classes=border,shadow)

This section contains various settings needed by other systems of BGS.

- Auto-load Bootstrap: Should the bootstrap auto-load when the Unity play button is pressed? You normally want to keep this on so that bootstrap can load auto-load scenes and global prefabs but the option is here to prevent this loading if you need it.
- Minimum Resolution: The minimum screen width and height that will be presented by the Settings Manager.
- Namespaces & Classes: The namespaces and classes to scan whenever looking for members. For example during member binding or when displaying a list of members that can be turned into Blocks.

### Global Variables

![Main Settings](/images/main-ed/02.png?height=100px&classes=border,shadow)

Here you can define what Global Variables are present in the game. This is the same as editing the component found on the `Assets/projectData/GameGlobal` prefab.

Refer to the [section on variables](/bgs/bgs-vars/) to learn more about BGS' variables.

### Attribute Defs

<!--![Main Settings](/images/main-ed/03.png?height=100px&classes=border,shadow)-->

_This is not currently used_