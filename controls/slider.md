
# Slider

* [Overview](#overview)
* [Properties](#properties)
	* [text](#text)
	* [progress](#progress)
	* [progressmax](#progressmax)
* [Events](#events)
	* [ontap](#ontap)
	* [onhold](#onhold)
	* [ondown](#ondown)
	* [onup](#onup)



## Overview
Sliders can be used to show or get progress.

	<slider text="position" progress="50" progressmax="100" onchange="update" />

<ct>layout.xml</ct>

	actions.update = function (progress)
		print("progress was changed to " .. progress);
	end

<ct>remote.lua</ct>



## Properties

### id
Specifies the ID for this control so that it can be updated later. See [layout library](/libs/layout).

	<slider id="my_slider" text="foo" />

### visibility
Specifies the visibility state using ``visible`` or ``invisible`` or ``gone``.

	<slider visibility="gone" />

### text
Specifies additional text to be shown in the slider.

	<slider text="hello world" progress="50" progressmax="100" />

will show:
	
	hello world - 50%

If you don't specify a ``text`` only the percentage will be shown:

	50%

### progress
Specifies the current progress value of the slider.

	<slider progress="99" />

### progressmax
Specifies the maximum progress value of the slider (default ``100``).

	<slider progressmax="200" />



## Events

### onchange
Occurs when the slider progress is changing.

	<slider onchange="changing" />

<ct>layout.xml</ct>

	actions.changing = function (value)
		...
	end

<ct>remote.lua</ct>

### ondone
Occurs when the slider has finished changing value.

	<slider ondone="finish" />

<ct>layout.xml</ct>

	actions.finish = function (value)
		...
	end

<ct>remote.lua</ct>

### ondown
Occurs when the slider is pressed (i.e. starts sliding).

	<slider ondown="start" />

<ct>layout.xml</ct>

	actions.start = function (value)
		...
	end

<ct>remote.lua</ct>

### onup
Occurs when the slider is released (i.e. stops sliding).

	<slider onup="stop" />

<ct>layout.xml</ct>

	actions.stop = function (value)
		...
	end

<ct>remote.lua</ct>
