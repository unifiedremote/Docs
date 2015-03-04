
# Label
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
Labels show text but can also be pressed.

````xml
<label text="press me!" ontap="foobar" />
````

````lua
actions.foobar = function ()
    print("you pressed a label!");
end
````



## Properties



### id
Set the ID for this control so that it can be updated later. See [layout library](/libs/layout.md).

````xml
<label id="my_lbl" text="foo" />
````



### visibility
Set the visibility state using ``visible`` or ``invisible`` or ``gone``.

````xml
<label visibility="gone" />
````



### text
Set the text to be shown.

````xml
<label text="hello world" />
````



### textalign
Set horizontal text alignment using ``left`` or ``center`` or ``right``.

````xml
<label text="foo" textalign="right" />
````



## Styling
See the [styling](styling.md) page for more details.



## Events



### ontap
Occurs when the control is tapped.

````xml
<label text="foo" ontap="foo_tapped" />
````

````lua
actions.foo_tapped = function ()
    ...
end
````



### onhold
Occurs when the control is held down.

````xml
<label text="bar" onhold="bar_held" />
````

````lua
actions.bar_held = function ()
    ...
end
````



### ondown
Occurs when the control is released.

````xml
<label text="hello" ondown="hello_down" />
````

````lua
actions.hello_down = function ()
    ...
end
````



### onup
Occurs when the control pressed down.

````xml
<label text="world" onup="world_up" />
````

````lua
actions.world_up = function ()
    ...
end
````


