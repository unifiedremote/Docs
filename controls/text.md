
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

````xml
<text hint="enter value" onchange="update" />
````

````lua
actions.update = function (text)

end
````



## Properties



### id
Set the ID for this control so that it can be updated later. See [layout library](/libs/layout.md).

````xml
<text id="my_txt" />
````



### visibility
Set the visibility state using ``visible`` or ``invisible`` or ``gone``.

````xml
<text visibility="gone" />
````



### text
Set the current text to be shown.

````xml
<text text="hello world" />
````



### textalign
Set horizontal text alignment using ``left`` or ``center`` or ``right``.

````xml
<text textalign="right" />
````



### hint
Set the placeholder hint (text to be shown when empty).

````xml
<text hint="enter here" />
````



### multiline
Set whether or not the control accepts multiline input (default ``false``).

````xml
<text multiline="true" />
````



## Styling
See the [styling](styling.md) page for more details.



## Events



### onchange
Occurs when the text changes.

````xml
<text onchange="changed" />
````

````lua
actions.changed = function (text)
    ...
end
````



### ondone
Occurs when editing ends.

````xml
<text ondone="done" />
````

````lua
actions.done = function (text)
    ...
end
````


