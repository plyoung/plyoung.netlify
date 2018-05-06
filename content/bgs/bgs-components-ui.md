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

##### GUI/Panels/Confirmation Panel

This panel can be used to provide the player with some information or a question that needs to be confirmed. This panel is normally needed by other panels, like the profiels panel and saving/ loading related UI panels.

- acceptButton: The button used to accept the request (OK, Yes, Accept).
- declineButton: The button used to decline the request (Cancel, No).
- message: (optional) The text message shown to player.
- acceptButtonText: (optional) Element used to shown text on accept button.
- declineButtonText: (optional) Element used to show text on decline button.

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

##### GUI/Panels/Text Input Panel

This general purpose panel can be used to ask the player to enter some text. This kind of panel might be required while setting up other, like the profiles panel.

- closeButtons: The button(s) which will close the panel. There should be at least 1 with the 1st being the button for 'accepting' the input while a second button can be used to 'cancel input'.
- inputField: The input field where the player will enter text.

-----------------------------------------------------------------------------------------------------------------------------

#### Persistence

These UI components help with creating a UI around the persistence system, used for saving and restoring the player's game session.

##### GUI/Panels/Persistence/Profiles Panel

If you make use of player profiles then you will want to create this UI to give the player a way to create or select a profile to play with.

- buttons: The profile buttons. The player click on these create or select a profile.
	+ profileButton: The button on which the profile name will be shown. On click a new profile is created when this profile is empty, else the profile will be loaded and this panel closed.
	+ profileNameText: (optional) The label used to show the profile name on the button.
	+ deleteButton: (optional) The button used to delete this profile.
- emptyProfileName: (optional) Text to be shown on profile buttons for profiles that are empty.
- nameEntryPanel: A panel used to enter a profile name.
- nameNotificationPanel: (optional) A panel shown to warn the player that a duplicate or invalid profile name was entered.
- notificationText: (optional) Text to show on notification panel. No text on the target panel will be replaced if you entered nothing here.
- autoLoadCreated: Auto-load and trigger 'onProfileLoaded' when a new profile is created?
- deleteConfirmationPanel: (optional) A confirmation panel to show when player selects to delete a profile.
- confirmationText: (optional) Text to show on confirmation panel. No text on the target panel will be replaced if you entered nothing here.
- onProfileLoaded: The event(s) to perform after a profile was loaded. This is a good place to close this panel and load the main menu.

##### GUI/Panels/Persistence/Save Panel

A panel used to create a new save slot or overwrite an existing save slot.

- slotTemplate: Template used to create [slot buttons](#gui-panels-persistence-elements-save-slot-button). This should be an object in the scene under the same container that all slots will be added to.
- newSlotButton: Button used to create a new slot.
- dateTimeFormat: What the date and time should look like on the slot's date-time text field. Default: "yyyy-MM-dd HH:mm". You can learn more about this string's format [here](https://docs.microsoft.com/en-us/dotnet/standard/base-types/standard-date-and-time-format-strings).
- overrideConfirmationPanel: (optional) A confirmation panel to show when player selects to override an existing slot.
- confirmationText: (optional) Text to show on confirmation panel. No text on the target panel will be replaced if you entered nothing here.

##### GUI/Panels/Persistence/Load Panel

A panel from where the player can select a game session to restore.

- slotTemplate: Template used to create [slot buttons](#gui-panels-persistence-elements-load-slot-button). This should be an object in the scene under the same container that all slots will be added to.
- loadButton: Button used to load selected slot.
- deleteButton: (optional) Button used to delete selected slot.
- dateTimeFormat: What the date and time should look like on the slot's date-time text field. Default: "yyyy-MM-dd HH:mm". You can learn more about this string's format [here](https://docs.microsoft.com/en-us/dotnet/standard/base-types/standard-date-and-time-format-strings).
- slotText: (optional) Where selected slot's slot text should be shown.
- slotDatetime: (optional) Where selected slot's DateTime text should be shown.
- slotImage: (optional) Where selected slot's screenshot should be shown.
- deleteConfirmationPanel: (optional) A confirmation panel to show when player selects to delete a slot.
- confirmationText: (optional) Text to show on confirmation panel. No text on the target panel will be replaced if you entered nothing here.

-----------------------------------------------------------------------------------------------------------------------------

#### Elements

##### GUI/Elements/Buttons Panel Button

This component is required on buttons used with the [Default Buttons Panel](#gui-panels-buttons-panel)

- label: Label shown on the Button.

##### GUI/Panels/Persistence/Elements/Save Slot Button

Used by the [Save Panel](#gui-panels-persistence-save-panel)

- slotText: (optional) Slot text will be shown here if there is slot text.
- dateTimeText: (optional) DateTime text. Last time this slot was saved to.
- thumb: (optional) Thumbnail of the save screenshot will be shown here.

##### GUI/Panels/Persistence/Elements/Load Slot Button

Used by the [Load Panel](#gui-panels-persistence-load-panel)

- slotText: (optional) Slot text will be shown here if there is slot text.
- dateTimeText: (optional) DateTime text. Last time this slot was saved to.
- thumb: (optional) Thumbnail of the save screenshot will be shown here.
- selectedIndicator: (optional) This object will be set active for the 'selected' slot button. This can be a frame to highlight which slot is selected.

-----------------------------------------------------------------------------------------------------------------------------

#### Settings

##### GUI/Elements/Settings/Fullscreen Toggle

Place on a toggle in your settings panel to allow the player to change between Fullscreen and Windowed mode.

##### GUI/Elements/Settings/Quality Dropdown

Place on a TMPro Dropdown to allow a player to change quality settings.

##### GUI/Elements/Settings/Resolution Dropdown

Place on a TMPro Dropdown to allow a player to change resolution.

##### GUI/Elements/Settings/Sound Volume Slider

Place on a slider, allowing player to change a volume type's value.

-----------------------------------------------------------------------------------------------------------------------------

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

