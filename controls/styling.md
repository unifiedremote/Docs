
# Styling
* [Overview](#overview)
* [Properties](#properties)
	* [color](#color)
	* [lightcolor / darkcolor](#lightcolor--darkcolor)
	* [light / dark](#light--dark)
* [Theme](#theme)
* [Colors](#colors)



## Overview
Styling properties can be used to change to look of controls.

````xml
<button color="red" />
````

Styling is inherited from grids to controls, so setting the style of a container control will set the style of the child controls.

````xml
<grid color="green" />
    <button text="green!" />
    <button text="also green!" />
</grid>
````
If you like to color a row do the following. 
````xml
<row>
    <grid color="green">
	    <button text="green!" />
	    <button text="also green!" />
    </grid>
</row>
````



## Properties



### color
Set the base [standard color](#colors). Automatically calculates color variations for themes and states.

````xml
<button color="blue" />
````




### lightcolor / darkcolor
For custom colors in hex, set the base color for when the app is in the respective theme. Automatically calculates color variations for states.

````xml
<button lightcolor="#cccccc" darkcolor="#444444" />
````



### light / dark
For completely custom themes, create a theme specifier.

````xml
<button light="color:#aaa;focus:#bbb;active:#ccc" />
````



## Theme
Theme specifiers are formatted like CSS:

````
normal:#aaa;focus:#bbb;active:#ccc;color:#abcdef
````

The following properties can be used:

Property | Use
-------- | ---
normal   | default color
focus    | pressed/focused color
active   | toggled/activated color
color    | text/entry color




## Colors
List of standard colors that can be used:

* red
* grey
* blue
* green
* orange
* purple
* pink
* yellow
* transparent
