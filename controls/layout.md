
# Layout
* [Overview](#overview)
* [Properties](#properties)
	* [orientation](#orientation)
	* [scroll](#scroll)
	* [error](#error)
* [Styling](#styling)
* [Events](#events)
	* [onlaunch](#onlaunch)
	* [onvolumedown](#onvolumedown)
	* [onvolumeup](#onvolumeup)
	* [onresume](#onresume)
	* [onpause](#onpause)



## Overview
The layout file describes the visual components of a remote.



## Properties



### orientation
Lock the orientation of the layout using ``portrait`` or ``landscape``.

````xml
<layout orientation="portrait">

</layout>
````



### scroll
Set the scroll mode using ``none``, ``vertical``, ``horizontal``, and ``both``.

````xml
<layout scroll="vertical">

</layout>
````



### error
Display an error message instead of a proper layout.

````xml
<layout error="Could not find required data.">

</layout>
````



## Styling
See the [styling](styling.md) page for more details.



## Events



### onlaunch
Occurs when the "launch" button is pressed in a remote.

````xml
<layout onlaunch="launch">

</layout>
````

````lua
actions.launch = function ()
    ...
end
````



### onvolumedown
Occurs when the "volume down" button is pressed on the client device.

````xml
<layout onvolumedown="volume_down">

</layout>
````

````lua
actions.volume_down = function ()
    ...
end
````



### onvolumeup
Occurs when the "volume up" button is pressed on the client device.

````xml
<layout onvolumeup="volume_up">

</layout>
````

````lua
actions.volume_up = function ()
    ...
end
````



### onpause
Occurs when the client device wishes to pause (for example phone call received).

````xml
<layout onpause="pause">

</layout>
````

````lua
actions.pause = function ()
    ...
end
````



### onresume
Occurs when the client device wishes to resume (for example phone call finished).

````xml
<layout onresume="resume">

</layout>
````

````lua
actions.resume = function ()
    ...
end
````


