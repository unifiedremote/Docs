
# Toggle
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
Toggles are buttons that can have two states (on or off).

````xml
<toggle text="change me!" checked="true" onchange="foobar" />
````

````lua
actions.changed = function (checked)
    print("you changed the toggle state to " .. checked);
end
````



## Properties



### id
Set the ID for this control so that it can be updated later. See [layout library](/libs/layout.md).

````xml
<toggle id="my_toggle" />
````



### visibility
Set the visibility state using ``visible`` or ``invisible`` or ``gone``.

````xml
<toggle visibility="gone" />
````



### text
Set the text to be shown.

````xml
<toggle text="hello world" />
````



### textalign
Set horizontal text alignment using ``left`` or ``center`` or ``right``.

````xml
<toggle text="foo" textalign="right" />
````



### icon
Set a standard control icon. See [icons list](/res/icons.md) of available icons.

````xml
<toggle icon="select" />
````



### image
Set a custom image to use. Should be a path relative to the layout file.

````xml
<toggle image="img.png" />
````



### checked
Set whether the toggle is on (``true``) or off (``false``).

````xml
<toggle checked="true" />
````



## Styling
See the [styling](styling.md) page for more details.



## Events



### onchange
Occurs when the toggle changes state.

````xml
<toggle onchange="changed" />
````

````lua
actions.changed = function (checked)
    ...
end
````



### ontap
Occurs when the control is tapped.

````xml
<toggle text="foo" ontap="foo_tapped" />
````

````lua
actions.foo_tapped = function ()
    ...
end
````



### onhold
Occurs when the control is held down.

````xml
<toggle text="bar" onhold="bar_held" />
````

````lua
actions.bar_held = function ()
    ...
end
````



### ondown
Occurs when the control is pressed down.

````xml
<toggle text="hello" ondown="hello_down" />
````

````lua
actions.hello_down = function ()
    ...
end
````



### onup
Occurs when the control released.

````xml
<toggle text="world" onup="world_up" />
````

````lua
actions.world_up = function ()
    ...
end
````


