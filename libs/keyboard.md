
# Keyboard
* [press](#keyboard_press)
* [stroke](#keyboard_stroke)
* [text](#keyboard_text)
* [down](#keyboard_down)
* [up](#keyboard_up)
* [character](#keyboard_character)
* [modifier](#keyboard_modifier)



## keyboard
The keyboard library provides actions for simulating key strokes and sending text. Refer to the [keys list](/api/res/keys).

	local kb = libs.keyboard;



### keyboard.press( key, [...] )
Performs one or more **consequtive** key presses.

	kb.press("down", "down", "return");
	kb.press("return");

	

### keyboard.stroke( key, [...] )
Performs a key stroke using one or more keys.

	kb.stroke("ctrl", "shift", "return");
	kb.stroke("win");



### keyboard.text( text )
Types the specified text, including unicode and special characters.

	kb.text("hello world!");
	kb.text("åäö");



### keyboard.down( key, [...] )
Presses one or more **consequtive** keys until ``up`` is called.

	kb.down("return");



### keyboard.up( key, [...] )
Releases one or more **consequtive** keys that have been pressed.

	kb.up("return");


### keyboard.character( chr )
Types the specified character code (UTF8 integer character code).

	kb.character(0x123);



### keyboard.modifier( key )
Returns a bool specifying whether or not the key is a modifier (e.g. ctrl, shift, alt).

	mod = kb.modifier("ctrl");			--> true
	mod = kb.modifier("return");		--> false