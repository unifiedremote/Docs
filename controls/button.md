
# Button
* [Overview](#overview)
* [Properties](#properties)
	* [id](#id)
	* [visibility](#visibility)
	* [text](#text)
	* [textalign](#textalign)
	* [icon](#icon)
	* [scale](#scale)
	* [image](#image)
* [Styling](#styling)
* [Events](#events)
	* [ontap](#ontap)
	* [onhold](#onhold)
	* [ondown](#ondown)
	* [onup](#onup)



## Overview
Buttons are simple controls that can be pressed.

````xml
<button text="press me!" ontap="foobar" />
````

````lua
actions.foobar = function ()
	print("you pressed a button!");
end
````



## Properties



### id
Set the ID for this control so that it can be updated later. See [layout library](/libs/layout.md).

````xml
<button id="my_btn" />
````



### visibility
Set the visibility state using ``visible`` or ``invisible`` or ``gone``.

````xml
<button visibility="gone" />
````



### text
Set the text to be shown in the button.

````xml
<button text="hello world" />
````



### textalign
Set horizontal text alignment using ``left`` or ``center`` or ``right``.

````xml
<button text="foo" textalign="right" />
````



### icon
Set a standard control icon. See [icons list](/res/icons.md) of available icons.

````xml
<button icon="select" />
````


### image
Set a custom image to use. Should be an absolute path or relative to the layout file.

````xml
<button image="img.png" />
````



### scale
Sets the scaling used for images. Values: ``icon`` (default), ``fill``, ``fit``, or ``native``.

````xml
<button image="img.png" scale="fit" />
````

<img src="http://s3.amazonaws.com/unifiedremote-community-uploads/6774bef3-d6db-453f-8f10-16af2fdd3d29.png" width="200" />


## Styling
See the [styling](styling.md) page for more details.



## Events



### ontap
Occurs when the button is tapped.

````xml
<button text="foo" ontap="foo_tapped" />
````

````lua
actions.foo_tapped = function ()
    ...
end
````



### onhold
Occurs when the button is held down.

````xml
<button text="bar" onhold="bar_held" />
````

````lua
actions.bar_held = function ()
    ...
end
````



### ondown
Occurs when the button is pressed.

````xml
<button text="hello" ondown="hello_down" />
````

````lua
actions.hello_down = function ()
    ...
end
````



### onup
Occurs when the button released.

````xml
<button text="world" onup="world_up" />
````

````lua
actions.world_up = function ()
    ...
end
````


