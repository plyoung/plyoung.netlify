+++
title = "Setup"
weight = 2
+++

This page will explain the steps to take when creating a new Blox Game Systems (BGS) based project.

### Requirements

**.NET 4.x**

After creating a new project you need to make sure that the scripting runtime is set to **.NET 4.x**. There will be errors if this is not set. Go to the player settings `menu: Edit > Project Settings > Player` and find the **Scripting runtime version** option. If you had to change this you will need to restart Unity now.

**Packages**

BGS also requires some free 3rd party packages you can get from the Asset Store.

- [TextMesh Pro](https://assetstore.unity.com/packages/essentials/beta-projects/textmesh-pro-84126): A replacement for Unity's default UI text rendering. You are probably using this already.
- [DoTween](https://assetstore.unity.com/packages/tools/animation/dotween-hotween-v2-27676): This is not required by BGS but some of the BGS plug-ins might need it. 

### Tutorials

The easiest way to get started with BGS is to watch some of the [<i class="fa fa-youtube" aria-hidden="true"></i> tutorial videos](https://www.youtube.com/playlist?list=PLuaBtUXEKcdJFTn_N5rG7CQZfB57dcQDy). It is a big systems, especially with plug-ins present, with many interacting parts. You may also [<i class="fa fa-archive" aria-hidden="true"></i> download](https://goo.gl/V898p7) sample projects.

### Data & Assets

The BGS package and any of its plug-in you install can be found in the `Assets/Tools/` folder.

All BGS settings and assets are stored in the `Assets/projectData/` folder. It is advised to not rename or move this folder and certainly not anything inside of this folder.

BGS might also add an `Assets/Gizmos` folder. This is required for some icons to function in Unity. This folder should not be moved/ renamed.

After installing BGS or a BGS plug-in you need to run a data check `menu: BGS > Check Game Data`. This will make sure that some of the important scenes, assets and prefabs are present and set up in the project.

Your **Build Settings** should now show a *00-bootstrap* scene as the 1st in the list. This scene should always appear 1st in the list and is needed by BGS to auto-load other scenes and global prefabs during startup. Do not edit or move this scene from its location in `Assets/projectData/Scenes/`.

### The Editors

BGs includes a few main editors that you will interact with regularly. You will probably want to open them now and dock in Unity for quick access.

**Main Editor**

`menu: BGS > BGS Main Editor` This is where most settings are changed and data defined. This editor has tabs along the top to seperate main sections of the editor. BGS plug-ins will add their own tabs when they need you to configure some data.

**FlowGraph**

`menu: BGS > Global FlowGraph` This editor allows you to edit FlowGraphs. FlowGraphs are mainly used for creating story flow/ character dialogue or conversation. There are also FlowGraphs for getting and setting data. These are mainly used by the BGS UI updaters.

