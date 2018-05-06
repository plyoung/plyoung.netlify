+++
title = "FlowGraph"
weight = 22
+++

![FlowGraph](/images/flowgraph/00.png?classes=border,shadow)

FlowGraphs are mainly used for story flow, like a conversation (dialogue) with game characters. A Visual Novel game for example could be built with this system alone. There are also graphs used for getting or setting data/ values from BGS or plug-ins' systems. These are normally needed by the [UI updaters](/bgs/bgs-components-ui/#updaters).

The FlowGraph editor is divided in 2 section. To the left you define grouped graphs. In the middle is the active graph's canvas, and to the right is the list of available nodes which can be drag-and-dropped into the canvas.

The Canvas Toolbar contains various buttons, drop-downs, and other UI elements. Certain plug-ins may add their own elements here, normally to the right-hand side of this toolbar.

The [*trash*] button is used to remove all unlinked nodes from the canvas (and graph). The [*center*] button can be used to quickly recenter the view on the graph's start node.

### Inspector

After adding a graph you should see the Inspector changes to show properties for the active graph. Clicking on a node in the graph's canvas, to make the node selected, will change the Inspector to show properties related to the selected node.

### Settings

The [*gear*] button in the canvas toolbar can be used to open the FlowGraph settings panel.

- Deadlock Detect: This is used to detect when the Graph enters an endless loop, a deadlock.
- Canvas Color: Background colour of the canvas.
- Node Link Color: Colour of node links.
- Default Link Style: Default style for node links. You may also change this individually with the drop-down in the canvas toolbar.
- Node Link Thickness: Thickness of the node link lines.
- Canvas Scroll Speed: How fast the canvas moves up/down when using mouse scroll wheel.
- Canvas Scroll Sideways: Should using the mouse scroll wheel scroll the canvas up-down or left-right?

Short-cut keys:

The typical Copy, Cut, Paste, Duplicate, Delete and Undo keys can be used in addition to these.

- Mouse Scroll-Wheel + Shift: Scroll faster.
- Mouse Scroll-Wheel + Ctrl: Scroll left/right or up/down.
- Shift + Drag Node: Moves all connected to that node too.

### Search in Canvas

The [*search*] button in the canvas toolbar is used to start node searching. You can enter something and press Enter/Return to jump to a node which responded to the search terms. Press Enter again to jump to the next applicable node.

### FlowGraph type Dropdown

Here you may select what type of FlowGraph you want to create/ edit. The easiest way to open the correct type of graph type is to make use of the edit button found next to Graph bind buttons in the inspector. You will note that the [UI Updaters](/bgs/bgs-components-ui/#updaters) have buttons like this next to the FlowGraph selection drop-down in their inspectors.

These are just to select the type (or category) of graph you are working with. The actual graphs are created in the left-hand panel by pressing the [+] button in the graphs panel's toolbar.

- **Global FlowGraph**: This is a general purpose graph type mainly used for story flow. "Start" node is 1st node.
- **Data Getter FlowGraph**: This is mainly used by UI Updaters to get value from BGS and plug-in systems to update UI elements with. There are other systems which might make use of this too, for example the `Value/Get/Value from FlowGraph` node. "Return" node is 1st node.
- **Data Setter & Actions FlowGraph**: This is mainly used by UI updaters to execute a Graph when a value on the related UI element changed. "Start" node is 1st node.

### Nodes List

The nodes list (a tree view) is found on the right-hand side of the FlowGraph editor. You simply click and drag-and-drop nodes from here into the canvas area to add them to the active graph. Select a node in this list to see a description, at the bottom of the list, for the selected node.

### FlowGraph Canvas

The canvas is where an active (selected) graph is edited. You drag-and-drop nodes here and then link them up.

There are two types of graphs. Those with a Start node and those with a Return node as the 1st node. Anything not connected to these nodes, or nodes connected to these, are not considered to be part of the graph during execution. Execution of a graph starts at these nodes. These 1st nodes are green to help identify them as the 1st node.

To connect nodes you simply click and drag from a pin to one of another node's pins. If the destination pin turns red then you know the connection is invalid. Dragging from a pin and then releasing on the canvas will pop-up a menu from where you can select a new node to be created and linked to the line you just create - of the connection would be valid. Press [Esc] or right-click to cancel the pin line being created.

Click and drag in the canvas to drag the canvas around. You may also use the mouse scroll-wheel to scroll the canvas up/down or left/right. Hold [Ctrl] while scrolling to scroll in other direction group. Hold [Shift] to scroll faster.

Click on a node to selected it. Press [Esc] or click in the canvas to clear selection of the selected node.

Click and drag a node to move that node in the canvas. Hold [Shift] to also move all nodes considered to be ion the down-flow.

Right-click on a node for option like copy, cut, and delete.

Right-click in the canvas for a list of nodes that can be added to the canvas on the spot, or to paste a copied node.

The short-cut keys for copy, cur, duplicate, delete, paste and undo also works in the canvas.

### Anatomy of a Node

![FlowGraph](/images/flowgraph/01.png?classes=border,shadow)

Nodes may have all or only some of these pins and which are used will depend on what type of graph they are used in or what nodes are connected and how they are connected.

#### Flow-in

Connected to from Flow-out pins.

The top pin of a node is the flow-in pin of a node. There is always only one of these. More than one node can connect to this pin to redirect its flow to this node. This pin can only be used in Graphs which has "Start" node as 1st node. The "Return" type graphs can't use it.

Execution/ flow will continue on one of this node's Flow-out pins if it has any and flow entered via its Flow-in pin.

#### Flow-out

Connects to Flow-in pins, or nothing, in which case the graph execution stops if that Flow-out node is reached.

The bottom pin(s) of a node are the flow-out pins of the node. There can be more than one or even no flow-out pins. If there are more than one then only one pin will be selected by the node during execution. Why there are more than one pin will depend on the node. A Conditional node for example can calculate a possible one of two result types and then choose a pin according to the result. The Buttons Panel node would select the node associated with the button the player pressed.

Numbering of these pins starts at with the left-most of the pins as 1, follow by 2, and so on when there are more than one of these pins.

A Flow-out pin is only used if execution of the node occurred because of flow coming from its Flow-in pin.

#### Value-in

Connected to from Value-out, or none.

These are on the left-hand side of a node. They are normally present where a node supports input data from other nodes. They may also be optional in some cases since the node might either take a value on the pin or one entered in the node's inspector.

Numbering of these pins starts with the top-most of the pins as 1, followed by 2, and so on when there are more than one of these pins. You might see labels like [1] and [2], etc on the Node or its Inspector. This means Value-in nodes [1], [2], etc.

Use-case example; The node (A) will make a call to the node (B) connected to this pin when node A executes. Node B would then calculate a value and return it. Node B will not continue execution on its Flow-out pin, if it has one, in this case but it might make calls via its own Value-in pins to any nodes connected there.

#### Value-out

Connects to Flow-in pins, or nothing.

 This pin is located on the right-hand side of a node. There can be only a maximum of one Value-out pin per node. This is where a node will provide a value it calculated. A connected node will make a call to this node via its Value-out pin to ask it to calculate and return a value to the node connected to this pin.

### Blackboard

While a graph is executing you might want to interact with the Blackboard. This is a variables type which are normally used temporarily. The active Blackboard, the one the Blackboard related get/ set nodes interacts with, is the Blackboard defined by the object executing the Graph. So if an [UI Input element updater](/bgs/bgs-components-ui/#gui-updaters-input) executes the graph then you would have access to its Blackboard and thus the **uivalue** variable defined on its Blackboard.

