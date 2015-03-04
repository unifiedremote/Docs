
# Text

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
The ``text`` control is used for editing text input.

	<text hint="enter value" onchange="update" />

<ct>layout.xml</ct>

	actions.update = function (text)
		
	end

<ct>remote.lua</ct>



## Properties

### id
Specifies the ID for this control so that it can be updated later. See [layout library](/libs/layout).

	<text id="my_txt" />

### visibility
Specifies the visibility state using ``visible`` or ``invisible`` or ``gone``.

	<text visibility="gone" />

### text
Specifies the current text to be shown.

	<text text="hello world" />

### textalign
Specifies horizontal text alignment using ``left`` or ``center`` or ``right``.

	<text textalign="right" />

### hint
Specifies the placeholder hint (text to be shown when empty).

	<text hint="enter here" />

### multiline
Specifies whether or not the control accepts multiline input (default ``false``).

	<text multiline="true" />



## Events

### onchange
Occurs when the text changes.

	<text onchange="changed" />

<ct>layout.xml</ct>

	actions.changed = function (text)
		...
	end

<ct>remote.lua</ct>

### ondone
Occurs when editing ends.

	<text ondone="done" />

<ct>layout.xml</ct>

	actions.done = function (text)
		...
	end

<ct>remote.lua</ct>
