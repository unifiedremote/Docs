
# Touch
* [Overview](#overview)
* [Properties](#properties)
	* [id](#id)
	* [visibility](#visibility)
	* [text](#text)
	* [image](#image)
* [Styling](#styling)
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

````xml
<touch text="touch here!" ontouchabs="moved" />
````

````lua
actions.moved = function (id, x, y)
    print("touch point " .. id .. " at " .. x .. " " .. y);
end
````



## Properties



### id
Set the ID for this control so that it can be updated later. See [layout library](/libs/layout.md).

````xml
<touch id="my_touch" />
````



### visibility
Set the visibility state using ``visible`` or ``invisible`` or ``gone``.

````xml
<touch visibility="gone" />
````



### text
Set the text to be shown in the background.

````xml
<touch text="hello world" />
````



### image
Set the background image.

````xml
<touch image="bg.png" />
````


## Styling
See the [styling](styling.md) page for more details.



## Events



### ontap
Occurs when the touch area is tapped.

````xml
<touch ontap="tapped" />
````

````lua
actions.tapped = function ()
    ...
end
````



### onhold
Occurs when the touch area is held down.

````xml
<touch onhold="held" />
````

````lua
actions.held = function ()
    ...
end
````



### ondoubletap
Occurs when the touch area is double tapped.

````xml
<touch ondoubletap="double" />
````

````lua
actions.double = function ()
    ...
end
````



### ondown
Occurs when touch begins.

````xml
<touch ondown="down" />
````

````lua
actions.down = function ()
    ...
end
````



### onup
Occurs when touch ends.

````xml
<touch onup="up" />
````

````lua
actions.up = function ()
    ...
end
````



### ontouchsize
Occurs when the touch area changes size.

````xml
<touch ontouchsize="touch_size" />
````

````lua
actions.touch_size = function (w, h, oldw, oldh)
    ...
end
````



### ontouchstart
Occurs when a multi-touch event starts (id is the pointer id).

````xml
<touch ontouchstart="touch_start" />
````

````lua
actions.touch_start = function (id, x, y)
    ...
end
````



### ontouchdelta
Occurs on multi-touch movement (id is the pointer id).

````xml
<touch ontouchdelta="touch_delta" />
````

````lua
actions.touch_delta = function (id, deltax, deltay)
    ...
end
````



### ontouchabs
Occurs on multi-touch movement (id is the pointer id).

````xml
<touch ontouchabs="touch_abs" />
````

````lua
actions.touch_abs = function (id, absx, absy)
    ...
end
````



### ontouchend
Occurs when a multi-touch event ends (id is the pointer id).

````xml
<touch ontouchend="touch_end" />
````

````lua
actions.touch_end = function (id, x, y)
    ...
end
````



### onmultitap
Occurs on a multi-touch tap occurs with n fingers.

````xml
<touch onmultitap="multitap" />
````

````lua
actions.multitap = function (n)
    ...
end
````


