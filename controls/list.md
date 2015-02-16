
# List

* [Overview](#overview)



## Overview

The list control provides an easy way of showing larger amounts of data.

	<layout>
		<list>
			<item text="item 1" />
			<item text="item 2" />
			<item text="item 3" />
			...
		</list>
	</layout>



## Properties

### id
Specifies the ID for this control so that it can be updated later. See [layout library](/api/libs/layout).

	<list id="my_toggle">
		...
	</list>

### visibility
Specifies the visibility state using ``visible`` or ``invisible`` or ``gone``.

	<list visibility="gone">
		...
	</list>

### text
Specifies the text to be shown in an item.

	<list>
		<item text="foo" />
		<item text="bar" />
	</list>

Items can also show sub-text using the ``\n`` delimiter.

	<list>
		<item text="foo\nbar" />
		<item text="hello\nworld" />
	</list>

### icon
Specifies the icon to be shown in an item. See [icons list](/api/res/icons) of available icons.

	<list>
		<item icon="select" text="foo" />
		<item icon="select" text="bar" />
	</list>

### image
Specifies a custom image to be shown in an item. Should be a path relative to the layout file.

	<list>
		<item image="img.png" text="foo" />
		<item image="img.png" text="bar" />
	</list>



## Events

### ontap
Occurs when an item is tapped.

	<list ontap="tapped">
		...
	</list>

<ct>layout.xml</ct>

	actions.tapped = function (index)
		...
	end

<ct>remote.lua</ct>

### onhold
Occurs when an item is held down.

	<list onhold="held">
		...
	</list>

<ct>layout.xml</ct>

	actions.held = function (index)
		...
	end

<ct>remote.lua</ct>