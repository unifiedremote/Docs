
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
Theme specifiers have the following properties:

* color
* focus
* active



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
