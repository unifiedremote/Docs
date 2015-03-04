
# List
* [Overview](#overview)
* [Properties](#properties)
	* [id](#id)
	* [visibility](#visibility)
	* [text](#text)
	* [icon](#icon)
	* [image](#image)
* [Events](#events)
	* [ontap](#ontap)
	* [onhold](#onhold)



## Overview
The list control provides an easy way of showing larger amounts of data.

````xml
<layout>
    <list>
        <item text="item 1" />
        <item text="item 2" />
        <item text="item 3" />
        ...
    </list>
</layout>
````



## Properties



### id
Set the ID for this control so that it can be updated later. See [layout library](/libs/layout.md).

````xml
<list id="my_toggle">
    ...
</list>
````



### visibility
Set the visibility state using ``visible`` or ``invisible`` or ``gone``.

````xml
<list visibility="gone">
    ...
</list>
````



### text
Set the text to be shown in an item.

````xml
<list>
    <item text="foo" />
    <item text="bar" />
</list>
````

Items can also show sub-text using the ``\n`` delimiter.

````xml
<list>
    <item text="foo\nbar" />
    <item text="hello\nworld" />
</list>
````



### icon
Set the icon to be shown in an item. See [icons list](/res/icons.md) of available icons.

````xml
<list>
    <item icon="select" text="foo" />
    <item icon="select" text="bar" />
</list>
````



### image
Set a custom image to be shown in an item. Should be a path relative to the layout file.

````xml
<list>
    <item image="img.png" text="foo" />
    <item image="img.png" text="bar" />
</list>
````



## Events



### ontap
Occurs when an item is tapped.

````xml
<list ontap="tapped">
    ...
</list>
````

````lua
actions.tapped = function (index)
    ...
end
````



### onhold
Occurs when an item is held down.

````xml
<list onhold="held">
    ...
</list>
````

````lua
actions.held = function (index)
    ...
end
````


