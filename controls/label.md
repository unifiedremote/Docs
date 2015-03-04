
# Label

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

Labels show text but can also be pressed.

	<label text="press me!" ontap="foobar" />

<ct>layout.xml</ct>

	actions.foobar = function ()
		print("you pressed a label!");
	end

<ct>remote.lua</ct>



## Properties

### id
Specifies the ID for this control so that it can be updated later. See [layout library](/libs/layout).

	<label id="my_lbl" text="foo" />

### visibility
Specifies the visibility state using ``visible`` or ``invisible`` or ``gone``.

	<label visibility="gone" />

### text
Specifies the text to be shown.

	<label text="hello world" />

### textalign
Specifies horizontal text alignment using ``left`` or ``center`` or ``right``.

	<label text="foo" textalign="right" />



## Events

### ontap
Occurs when the control is tapped.

	<label text="foo" ontap="foo_tapped" />

<ct>layout.xml</ct>

	actions.foo_tapped = function ()
		...
	end

<ct>remote.lua</ct>

### onhold
Occurs when the control is held down.

	<label text="bar" onhold="bar_held" />

<ct>layout.xml</ct>

	actions.bar_held = function ()
		...
	end

<ct>remote.lua</ct>

### ondown
Occurs when the control is released.

	<label text="hello" ondown="hello_down" />

<ct>layout.xml</ct>

	actions.hello_down = function ()
		...
	end

<ct>remote.lua</ct>

### onup
Occurs when the control pressed down.

	<label text="world" onup="world_up" />

<ct>layout.xml</ct>

	actions.world_up = function ()
		...
	end

<ct>remote.lua</ct>