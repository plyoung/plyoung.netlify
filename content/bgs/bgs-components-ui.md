+++
title = "UI Components"
weight = 31
+++

The BGS Components can be found under `menu: Component/BGS`.

#### Panels

##### GUI/Panels/Buttons Panel

The default buttons panel. A buttons panel is needed when you make use of the Buttons Panel FlowGraph node. Custom button panels may be created by deriving from the `ButtonsPanelBase` class.

This panel can either show predefined buttons or automatically add/remove buttons as requested from the FlowNode. The buttons should have the [Buttons Panel Button](#gui-elements-buttons-panel-button) component on them.

- existingButtons: Should a set of predefined buttons be used or should buttons be added and removed as needed?
	+ buttons: The button objects to use if existingButtons option was chosen.
- container: Where new buttons are added. It is best if this object has a layout component on it to automatically reposition buttons as they get added or removed.
- buttonTemplate: The template or prefab to use when a new button must be added.

##### GUI/Panels/Dialogue Panel

The default dialogue panel. A dialogue panel is needed when you make use of the Dialogue Panel FlowGraph node. Custom dialogue panels may be created by deriving from the `DialoguePanelBase` class.

- UI Elements
	+ dialogueText: Where the dialogue text should be shown.
	+ nameText: Where name of speaker is shown.
	+ portrait: Where the portrait should be shown.
- Input
	+ clickToAdvance: Can player click on the dialogue text area to advance?
	+ clickArea: The object representing the area the player can click in to advance. This would normally be an Image covering the area with Raycast Target enabled.
- Settings
	+ hideAtEnd: Hide the panel when all text read and player click to continue?
	+ splitOnNewLine: Should text be shown all at once or split up by paragraphs/new-lines?
	+ autoAdvance: Should dialogue advance automatically after all text is shown?
	+ autoAdvanceSpeed: (Seconds) How long should it wait after all text was shown before advancing?"
	+ typeWriterReveal: Should a type-writer effect be used to show the characters one after another?
	+ wordBasedReveal: Should reveal be character or word based?
	+ revealSpeed: (Seconds) Delay between showing next character/word.

##### GUI/Panels/General Panel

A general panel is needed when you make use of the General Panel FlowGraph node. Custom general panels may be created by deriving from the `GeneralPanelBase` class.

- closeButtons: The button(s) which will closes the panel.

##### GUI/Panels/Panel Manager

The panel manager is used to show and hide panels (or any child objects of this object). The `SetActivePanel(string panelName)` can be called with the name of a child GameObject to make that the active panel while the previously active panel will be deactivate, if any.

- activeAtStart: The panel which should be set active at start.
- ignore: The objects to ignore. Any child objects not in this list will automatically be set inactive at start.

#### Elements

##### GUI/Elements/Buttons Panel Button

This component is required on buttons used with the [Default Buttons Panel](#gui-panels-buttons-panel)

- label: Label shown on the Button.

#### Settings

##### GUI/Elements/Settings/Fullscreen Toggle

Place on a toggle in your settings panel to allow the player to change between Fullscreen and Windowed mode.

##### GUI/Elements/Settings/Quality Dropdown

Place on a TMPro Dropdown to allow a player to change quality settings.

##### GUI/Elements/Settings/Resolution Dropdown

Place on a TMPro Dropdown to allow a player to change resolution.

##### GUI/Elements/Settings/Sound Volume Slider

Place on a slider, allowing player to change a volume type's value.

#### Updaters

UI updaters help create a bind between UI elements and internal data. They can automatically update UI elements when internal values changes or automatically update internal data when user input occurs on a UI element. The binding is handled via [FlowGraph](/bgs/bgs-flowgraph/).

All updaters have a [Blackboard (variables)](/bgs/bgs-vars/). Some might update a **uivalue** variable on the Blackboard. This variable is updated with the element's current value when it changes.

##### GUI/Updaters/Active State

Changes the active state of target object.

- targetObject: The object to activate or deactivate as needed.
- valueGetter: The bind used to determine the active state the target object should be in. This bind should return a boolean (True/ False) value.

##### GUI/Updaters/Button Action

React on a button press.

- targetButton: The button to bind to.
- actionBind: The graph to execute when the button is pressed.

##### GUI/Updaters/Button Quick Action

React on a button press. Invokes bound member when the button is pressed.

##### GUI/Updaters/Color

Changes the colour of target graphic.

- targetElement: The target graphic.
- valueGetter: The bind used to get the value to set the target element with. The graph must return a color value.

##### GUI/Updaters/Image

Changes the sprite of target image.

- targetElement: The target Image.
- valueGetter: The bind used to get the value to set the target element with. The graph must return a Sprite.

##### GUI/Updaters/Input (TMPro)

Get and/or set the value of target TextMesh Pro input element.

- targetElement: Target input element.
- playerCanChange: Should the player be able to change the value via the UI?
- valueGetter: The bind used to get the value to set the target element with. The graph must return a text value.
- valueSetter: The bind used to update internal data when the player entered a value in the UI.

##### GUI/Updaters/Input

Get and/or set the value of target input element.

- targetElement: Target input element.
- playerCanChange: Should the player be able to change the value via the UI?
- valueGetter: The bind used to get the value to set the target element with. The graph must return a text value.
- valueSetter: The bind used to update internal data when the player entered a value in the UI.

##### GUI/Updaters/RawImage

Changes the texture of target raw image.

- targetElement: The target Image.
- valueGetter: The bind used to get the value to set the target element with. The graph must return a texture.

##### GUI/Updaters/Slider

Get and/or set the value of a slider.

- targetElement: Target slider element.
- playerCanChange: Should the player be able to change the value via the UI?
- valueGetter: The bind used to get the value to set the target element with. The graph must return a number (float)
- valueSetter: The bind used to update internal data when the player entered a value in the UI.

##### GUI/Updaters/Text Params

Changes text on target TextMehs Pro element by inserting values wherever {0}, {1}, {2}, etc occurs in the target text. It does not replace all the text in the target like the Text updaters do but only the occurrences of {0}, {1}, etc depending on how many graphs are linked to this component.

Example: Original text on the UI element is "My name is {0}".

If you now use the `Text Params` updater on this text it will get a value through a graph, for example 'Leslie', and replace the {0} with that value so that the UI element then read "My name is Leslie".

- targetElement: Target text element.
- valueGetter: The bind used to get the value to set the target element with. The graph must return a string (text) value.

##### GUI/Updaters/Text (TMPro)

Changes text on target TextMehs Pro element.

- targetElement: Target text element.
- valueGetter: The bind used to get the value to set the target element with. The graph must return a string (text) value.

##### GUI/Updaters/Text

Changes text on target element.

- targetElement: Target text element.
- valueGetter: The bind used to get the value to set the target element with. The graph must return a string (text) value.

##### GUI/Updaters/Toggle

Changes value on target toggle element.

- targetElement: Target toggle element.
- playerCanChange: Should the player be able to change the value via the UI?
- valueGetter: The bind used to get the value to set the target element with. The graph must return a boolean (True/False) value.
- valueSetter: The bind used to update internal data when the player entered a value in the UI.

