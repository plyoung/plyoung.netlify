+++
title = "Setup"
weight = 2
+++

This page will explain the steps to take when creating a new Blox Game Systems (BGS) based project.

### Setup

**1) .NET 4.x**

After creating a new project you need to make sure that the scripting runtime is set to **.NET 4.x**. There will be errors if this is not set this before importing BGS. Go to the player settings `menu: Edit > Project Settings > Player` and find the **Scripting runtime version** option. If you had to change this you will need to restart Unity now.

**Api Compatibility Level** should be set to `.NET 4.x`, not `.NET Standard 2.0`.

**2) Packages: TextMesh Pro**

[TextMesh Pro](https://assetstore.unity.com/search?q=textmesh&q=pro) is a replacement for Unity's default UI text rendering. You are probably using this already. This can be installed via the Unity Package Manager `menu: Window > Package Manager`.

**3) Packages: DoTween**

[DoTween](https://assetstore.unity.com/packages/tools/animation/dotween-hotween-v2-27676) (free) is a fast, efficient, fully type-safe object-oriented animation engine, optimized for C#. It is required by some systems in BGS and BGS plug-ins.

Be sure to run the setup before you continue. Open the utility panel `menu: Tools > Demigiant > DOTween Utility Panel`  and press the setup button.

**4) Install BGS and its plug-ins**

Now you can import Blox Game Systems without error. If you mixed up the steps and installed BGS first you should still be fine after completing all the steps. You will simply get some error messages in the UNity console while performing the steps.

BGS plug-ins should be installed after BGS is installed.

After installing BGS or a BGS plug-in you will want to run the data check to make sure some default data is present in the project. This is done via `menu: BGS > Check BGS Data`. You only have to do this once after BGS or a new BGS plug-in was installed.

Your **Build Settings** should now show a *00-bootstrap* scene as the 1st in the list. This scene should always appear 1st in the list and is needed by BGS to auto-load other scenes and global prefabs during startup. Do not edit or move this scene from its location in `Assets/projectData/Scenes/`.

### Tutorials

The easiest way to get started with BGS is to watch some of the [<i class="fa fa-youtube" aria-hidden="true"></i> tutorial videos](/tutorials/). It is a big systems, especially with plug-ins present, with many interacting parts. You may also [<i class="fa fa-archive" aria-hidden="true"></i> download](/tutorials/) sample projects to help get started with BGS or a BGS plug-in.

### Data & Assets

The BGS package and any of its plug-in you install can be found in the `Assets/Tools/` folder.

All BGS settings and assets are stored in the `Assets/projectData/` folder. It is advised to not rename or move this folder and certainly not anything inside of this folder.

BGS might also add an `Assets/Gizmos` folder. This is required for some icons to function in Unity. This folder should not be moved/ renamed.

After installing BGS or a BGS plug-in you need to run a data check `menu: BGS > Check Game Data`. This will make sure that some of the important scenes, assets and prefabs are present and set up in the project.

Your **Build Settings** should now show a *00-bootstrap* scene as the 1st in the list. This scene should always appear 1st in the list and is needed by BGS to auto-load other scenes and global prefabs during startup. Do not edit or move this scene from its location in `Assets/projectData/Scenes/`.

### The Editors

BGS includes a few main editors that you will interact with regularly. You will probably want to open them now and dock in Unity for quick access.

**Toolbar**

`menu: BGS > Toolbar` This opens a toolbar window which you can dock somewhere. It provides a quick way to open a BGS  main editor.

**Main Editor**

`menu: BGS > BGS Main Editor` This is where most settings are changed and data defined. This editor has tabs along the top to separate main sections of the editor. BGS plug-ins will add their own tabs when they need you to configure some data.

**Game Data**

`menu: BGS > Game Data Editor` This will open the Game Data system's editor where you can define new game data types or add data to the definitions.

**FlowGraph**

`menu: BGS > FlowGraph Editor` This editor allows you to edit FlowGraphs. FlowGraphs are mainly used for creating story flow/ character dialogue or conversation. There are also FlowGraphs for getting and setting data. These are mainly used by the BGS UI updaters.

