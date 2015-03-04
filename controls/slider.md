
# Slider
* [Overview](#overview)
* [Properties](#properties)
	* [id](#id)
	* [visibility](#visibility)
	* [text](#text)
	* [progress](#progress)
	* [progressmax](#progressmax)
* [Styling](#styling)
* [Events](#events)
	* [ontap](#ontap)
	* [onhold](#onhold)
	* [ondown](#ondown)
	* [onup](#onup)



## Overview
Sliders can be used to show or get progress.

````xml
<slider text="position" progress="50" progressmax="100" onchange="update" />
````

````lua
actions.update = function (progress)
    print("progress was changed to " .. progress);
end
````



## Properties



### id
Set the ID for this control so that it can be updated later. See [layout library](/libs/layout.md).

````xml
<slider id="my_slider" text="foo" />
````



### visibility
Set the visibility state using ``visible`` or ``invisible`` or ``gone``.

````xml
<slider visibility="gone" />
````



### text
Set additional text to be shown in the slider.

````xml
<slider text="hello world" progress="50" progressmax="100" />
````

will show:

hello world - 50%

If you don't specify a ``text`` only the percentage will be shown:

50%



### progress
Set the current progress value of the slider.

````xml
<slider progress="99" />
````



### progressmax
Set the maximum progress value of the slider (default ``100``).

````xml
<slider progressmax="200" />
````



## Styling
See the [styling](styling.md) page for more details.



## Events



### onchange
Occurs when the slider progress is changing.

````xml
<slider onchange="changing" />
````

````lua
actions.changing = function (value)
    ...
end
````



### ondone
Occurs when the slider has finished changing value.

````xml
<slider ondone="finish" />
````

````lua
actions.finish = function (value)
    ...
end
````



### ondown
Occurs when the slider is pressed (i.e. starts sliding).

````xml
<slider ondown="start" />
````

````lua
actions.start = function (value)
    ...
end
````



### onup
Occurs when the slider is released (i.e. stops sliding).

````xml
<slider onup="stop" />
````

````lua
actions.stop = function (value)
    ...
end
````


