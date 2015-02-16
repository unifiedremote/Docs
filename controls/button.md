
# Button

* [Overview](#overview)
* [Properties](#properties)
	* [id](#id)
	* [visibility](#visibility)
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

Buttons are simple pressable controls.

    button text="press me!" ontap="foobar" />

<ct>layout.xml</ct>

	actions.foobar = function ()
		print("you pressed a button!");
	end

<ct>remote.lua</ct>



## Properties

### id
Specifies the ID for this control so that it can be updated later. See [layout library](/api/libs/layout).

	<button id="my_btn" text="foo" />

### visibility
Specifies the visibility state using ``visible`` or ``invisible`` or ``gone``.

	<button visibility="gone" />

### text
Specifies the text to be shown in the button.

	<button text="hello world" />

### textalign
Specifies horizontal text alignment using ``left`` or ``center`` or ``right``.

	<button text="foo" textalign="right" />

### icon
Specifies a standard control icon. See [icons list](/api/res/icons) of available icons.

	<button icon="select" />

### image
Specifies a custom image to use. Should be a path relative to the layout file.

	<button image="img.png" />



## Events

### ontap
Occurs when the button is tapped.

	<button text="foo" ontap="foo_tapped" />

<ct>layout.xml</ct>

	actions.foo_tapped = function ()
		...
	end

<ct>remote.lua</ct>

### onhold
Occurs when the button is held down.

	<button text="bar" onhold="bar_held" />

<ct>layout.xml</ct>

	actions.bar_held = function ()
		...
	end

<ct>remote.lua</ct>

### ondown
Occurs when the button is released.

	<button text="hello" ondown="hello_down" />

<ct>layout.xml</ct>

	actions.hello_down = function ()
		...
	end

<ct>remote.lua</ct>

### onup
Occurs when the button pressed down.

	<button text="world" onup="world_up" />

<ct>layout.xml</ct>

	actions.world_up = function ()
		...
	end

<ct>remote.lua</ct>