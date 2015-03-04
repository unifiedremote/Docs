
# Tabs
* [Overview](#overview)
* [Properties](#properties)
	* [id](#id)
	* [visibility](#visibility)
	* [text](#text)
	* [index](#index)
* [Styling](#styling)
* [Events](#events)
	* [onchange](#onchange)


## Overview
The tabs control works like a grid except that it can have several tab pages.
Each tab page can have a title and is a grid control, so you can add rows directly.

````xml
<layout>
    <tabs>
        <tab text="Page 1">
            <row>
                <button />
            </row>
        </tab>
        <tab text="Page 2">
            <row>
                <button />
            </row>
        </tab>
        <tab text="Page 3">
            <row>
                <button />
            </row>
        </tab>
    </tabs>
</layout>
````



## Properties



### id
Set the ID for this control so that it can be updated later. See [layout library](/libs/layout.md).

````xml
<tabs id="my_toggle">
    ...
</tabs>
````



### visibility
Set the visibility state using ``visible`` or ``invisible`` or ``gone``.

````xml
<tabs visibility="gone">
    ...
</tabs>
````



### text
Set the title of a tab page.

````xml
<tabs>
    <tab text="foo">
        ...
    </tab>
</tabs>
````



### index
Set active tab number (zero-based).

````xml
<tabs index="1">
    <tab>...</tab>
    <tab>...</tab>
    <tab>...</tab>
</tabs>
````



## Styling
See the [styling](styling.md) page for more details.



## Events



### onchange
Occurs when the active tab page changes.

````xml
<tabs onchange="update">
    ...
</tabs>
````

````lua
actions.update = function (index)
    ...
end
````


