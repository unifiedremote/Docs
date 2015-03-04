
# Text
* [Overview](#overview)
* [Properties](#properties)
	* [id](#id)
	* [visibility](#visibility)
	* [text](#text)
	* [textalign](#textalign)
	* [icon](#icon)
	* [image](#image)
* [Styling](#styling)
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
Set the ID for this control so that it can be updated later. See [layout library](/libs/layout.md).

	<text id="my_txt" />



### visibility
Set the visibility state using ``visible`` or ``invisible`` or ``gone``.

	<text visibility="gone" />



### text
Set the current text to be shown.

	<text text="hello world" />



### textalign
Set horizontal text alignment using ``left`` or ``center`` or ``right``.

	<text textalign="right" />



### hint
Set the placeholder hint (text to be shown when empty).

	<text hint="enter here" />



### multiline
Set whether or not the control accepts multiline input (default ``false``).

	<text multiline="true" />



## Styling
See the [styling](styling.md) page for more details.



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
