
# Touch

* [Overview](#overview)
* [Properties](#properties)
	* [text](#text)
	* [image](#image)
* [Events](#events)
	* [ontap](#ontap)
	* [onhold](#onhold)
	* [ondoubletap](#ondoubletap)
	* [ondown](#ondown)
	* [onup](#onup)
	* [ontouchsize](#ontouchsize)
	* [ontouchstart](#ontouchstart)
	* [ontouchdelta](#ontouchstart)
	* [ontouchabs](#ontouchstart)
	* [ontouchend](#ontouchstart)
	* [onmultitap](#onmultitap)


## Overview
The ``touch`` control can be used for receiving multi-touch events.

	<touch text="touch here!" ontouchabs="moved" />

<ct>layout.xml</ct>

	actions.moved = function (id, x, y)
		print("touch point " .. id .. " at " .. x .. " " .. y);
	end

<ct>remote.lua</ct>



## Properties

### id
Specifies the ID for this control so that it can be updated later. See [layout library](/libs/layout).

	<touch id="my_touch" />

### visibility
Specifies the visibility state using ``visible`` or ``invisible`` or ``gone``.

	<touch visibility="gone" />

### text
Specifies the text to be shown in the background.

	<touch text="hello world" />

### image
Specifies the background image.

	<touch image="bg.png" />



## Events

### ontap
Occurs when the touch area is tapped.

	<touch ontap="tapped" />

<ct>layout.xml</ct>

	actions.tapped = function ()
		...
	end

<ct>remote.lua</ct>

### onhold
Occurs when the touch area is held down.

	<touch onhold="held" />

<ct>layout.xml</ct>

	actions.held = function ()
		...
	end

<ct>remote.lua</ct>

### ondoubletap
Occurs when the touch area is double tapped.

	<touch ondoubletap="double" />

<ct>layout.xml</ct>

	actions.double = function ()
		...
	end

<ct>remote.lua</ct>

### ondown
Occurs when touch begins.

	<touch ondown="down" />

<ct>layout.xml</ct>

	actions.down = function ()
		...
	end

<ct>remote.lua</ct>

### onup
Occurs when touch ends.

	<touch onup="up" />

<ct>layout.xml</ct>

	actions.up = function ()
		...
	end

<ct>remote.lua</ct>

### ontouchsize
Occurs when the touch area changes size.

	<touch ontouchsize="touch_size" />

<ct>layout.xml</ct>

	actions.touch_size = function (w, h, oldw, oldh)
		...
	end

<ct>remote.lua</ct>

### ontouchstart
Occurs when a multi-touch event starts (id is the pointer id).

	<touch ontouchstart="touch_start" />

<ct>layout.xml</ct>

	actions.touch_start = function (id, x, y)
		...
	end

<ct>remote.lua</ct>

### ontouchdelta
Occurs on multi-touch movement (id is the pointer id).

	<touch ontouchdelta="touch_delta" />

<ct>layout.xml</ct>

	actions.touch_delta = function (id, deltax, deltay)
		...
	end

<ct>remote.lua</ct>

### ontouchabs
Occurs on multi-touch movement (id is the pointer id).

	<touch ontouchabs="touch_abs" />

<ct>layout.xml</ct>

	actions.touch_abs = function (id, absx, absy)
		...
	end

<ct>remote.lua</ct>

### ontouchend
Occurs when a multi-touch event ends (id is the pointer id).

	<touch ontouchend="touch_end" />

<ct>layout.xml</ct>

	actions.touch_end = function (id, x, y)
		...
	end

<ct>remote.lua</ct>

### onmultitap
Occurs on a multi-touch tap occurs with n fingers.

	<touch onmultitap="multitap" />

<ct>layout.xml</ct>

	actions.multitap = function (n)
		...
	end

<ct>remote.lua</ct>
