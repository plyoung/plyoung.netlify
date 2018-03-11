+++
title = "MainEd: FlowGraph"
weight = 11
+++

FlowGraph graphs and nodes uses this section for settings and data definition when needed.

### Buttons

![Startup & Scenes](/images/main-ed/04.png?height=100px&classes=border,shadow)

This is the settings for the `UI/Buttons Panel` node. The node needs to know about all defined Buttons Panels and this is where you can initiate a scan for such panels. This scans for all GameObject with components derived from the `ButtonsPanelBase` class, like the default [Buttons Panel](/bgs/bgs-components-ui/#gui-panels-buttons-panel) component.

### Dialogue

![Startup & Scenes](/images/main-ed/05.png?height=100px&classes=border,shadow)

This is the settings for the `UI/Dialogue Panel` node. The node needs to know about all defined Dialogue Panels and this is where you can initiate a scan for such panels. This scans for all GameObject with components derived from the `DialoguePanelBase` class, like the default [Dialogue Panel](/bgs/bgs-components-ui/#gui-panels-dialogue-panel) component.

### Panels

![Startup & Scenes](/images/main-ed/06.png?height=100px&classes=border,shadow)

This is the settings for the `UI/General Panel` node. The node needs to know about all defined general purpose panels and this is where you can initiate a scan for such panels. This scans for all GameObject with components derived from the `GeneralPanelBase` class, like the default [General Panel](/bgs/bgs-components-ui/#gui-panels-general-panel) component.