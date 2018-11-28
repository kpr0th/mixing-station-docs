# Custom layout

This feature allows you to fully customize the mixer view to match your workflow
and create new views for different purposes (e.g. fixed installations).

## Structure
In the app you can create an unlimited number of layouts, each of them has a set of UI elements.

- Layout Overview
	- Add/edit Layout
		- Add/edit UI items
			- One or more [actions](custom-actions.md) per UI item

## Quickstart

1. Open the menu of the main view
2. `Menu->Setup ->Layouts`
3. Press the `+` menu entry to add a new layout
	1. Enter the name of the layout - the first layout will replace your default mixer view.
4. Add and move UI items to your taste
	1. Note: `Channel Strip` is only for fixed channels. Use `Mixer` to get the channel strips which match the currently selected layer.
6. Make sure to save your layout (if autosave is disabled)
	1. Goto step 2.
	2. Press the folder icon in the menu

## UI items
This section describes all available UI items and their configuration parameters

### General
These settings are available for all UI items

#### Settings: Visibility
This settings controls under which conditions the UI will be visible.

| Visibility | Description
| -- | -- |
| Always | Item will always be visible |
| Only SoF | Item will only be visible if SoF is active |
| Not SoF | Item will only be visible if SoF is not active |

### Mixer 
Shows a container which displays all channels of the currently active layer.
This also includes the meterbridge (if enabled in the app settings).

![Mixer](img/layouts/mixer.png)

### Channel strip
A single channel strip which can be assigned to a fixed channel,
or a dynamic channel source like the `Bus master`.
Do **NOT** use this if you want "something that follows the layer" - use the `Mixer` instead.


### SoF list
List of buttons for controlling the sends on fader, fine and mute enable status

![Sof list](img/layouts/sof-list.png)

### Layer list
List of buttons for selecting a layer

![Layer list](img/layouts/layer-list.png)


### Button
A button can be used to toggle the status of an action

![Button](img/layouts/buttons.png)

#### Settings: Label
Defines the text that will be shown on the button. It is possible to write multiple lines of text.
See [Label Tags](##Label-tags) for more information.

#### Settings: Touch mode
It is possible to change the touch behavior of the button.
This can be useful when you want to control a mute group, but only when the button was long pressed.

### Knob
A knob can be used to control a numeric value (like a send level or pan).

![Knob](img/layouts/knob.png)

### Label
A label can be used to show values like the current scene or just for showing text.

![Label](img/layouts/label.png)

#### Settings: Text position
Changes how the text will be aligned on screen.


## Label tags
It is possible to use dynamic text as a label for the UI items.
To do so use one of the following tags:

| Tag | Action | Description |
| -- | -- | -- |
| `[label]` | Any | Shows a short description of the action |
| `[value]` | Any | Shows the current value of the action |
| `[bpm]` | FX | BPM for 1/4 notes |
| `[sofname]` | Sends on fader | Name of the current bus master |
| `[chname]` | Channel actions | Name of the channel of the action |


## Example: Tap delay button
1. Open the mixer layer setup
2. Add a button
3. Add a new action to the button
4. Select the FX action and select the Effect which you want to control
5. Select the time parameter of the FX
6. Go back to the mixer