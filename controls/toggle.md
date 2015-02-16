
# Toggle

* [Overview](#overview)
* [Properties](#properties)
	* [text](#text)
	* [textalign](#textalign)
	* [icon](#icon)
	* [image](#image)
* [Events](#events)
	* [ontap](#ontap)
	* [onhold](#onhold)
	* [ondown](#ondown)
	* [onup](#onup)


## Overview
Toggles are buttons that can have two states (on or off).

	<toggle text="change me!" checked="true" onchange="foobar" />

<ct>layout.xml</ct>

	actions.changed = function (checked)
		print("you changed the toggle state to " .. checked);
	end

<ct>remote.lua</ct>



## Properties

### id
Specifies the ID for this control so that it can be updated later. See [layout library](/api/libs/layout).

	<toggle id="my_toggle" />

### visibility
Specifies the visibility state using ``visible`` or ``invisible`` or ``gone``.

	<toggle visibility="gone" />

### text
Specifies the text to be shown.

	<toggle text="hello world" />

### textalign
Specifies horizontal text alignment using ``left`` or ``center`` or ``right``.

	<toggle text="foo" textalign="right" />

### icon
Specifies a standard control icon. See [icons list](/api/res/icons) of available icons.

	<toggle icon="select" />

### image
Specifies a custom image to use. Should be a path relative to the layout file.

	<toggle image="img.png" />

### checked
Specifies whether the toggle is on (``true``) or off (``false``).

	<toggle checked="true" />



## Events

### onchange
Occurs when the toggle changes state.

	<toggle onchange="changed" />

<ct>layout.xml</ct>

	actions.changed = function (checked)
		...
	end

### ontap
Occurs when the control is tapped.

	<toggle text="foo" ontap="foo_tapped" />

<ct>layout.xml</ct>

	actions.foo_tapped = function ()
		...
	end

<ct>remote.lua</ct>

### onhold
Occurs when the control is held down.

	<toggle text="bar" onhold="bar_held" />

<ct>layout.xml</ct>

	actions.bar_held = function ()
		...
	end

<ct>remote.lua</ct>

### ondown
Occurs when the control is pressed down.

	<toggle text="hello" ondown="hello_down" />

<ct>layout.xml</ct>

	actions.hello_down = function ()
		...
	end

<ct>remote.lua</ct>

### onup
Occurs when the control released.

	<toggle text="world" onup="world_up" />

<ct>layout.xml</ct>

	actions.world_up = function ()
		...
	end

<ct>remote.lua</ct>
