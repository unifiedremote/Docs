
# Keyboard
* [keyboard](#keyboard-1)
* [press](#keyboardpress-key--)
* [stroke](#keyboardstroke-key--)
* [text](#keyboardtext-text-)
* [down](#keyboarddown-key--)
* [up](#keyboardup-key--)
* [character](#keyboardcharacter-chr-)
* [modifier](#keyboardmodifier-key-)



## keyboard
The keyboard library provides actions for simulating key strokes and sending text. Refer to the [keys list](/res/keys.md).

````lua
local kb = require("keyboard");
````



### keyboard.press( key, [...] )
Performs one or more **consequtive** key presses.

````lua
kb.press("down", "down", "return");
kb.press("return");
````

	

### keyboard.stroke( key, [...] )
Performs a key stroke using one or more keys.

````lua
kb.stroke("ctrl", "shift", "return");
kb.stroke("win");
````



### keyboard.text( text )
Types the specified text, including unicode and special characters.

````lua
kb.text("hello world!");
kb.text("åäö");
````



### keyboard.down( key, [...] )
Presses one or more **consequtive** keys until ``up`` is called.

````lua
kb.down("return");
````



### keyboard.up( key, [...] )
Releases one or more **consequtive** keys that have been pressed.

````lua
kb.up("return");
````


### keyboard.character( chr )
Types the specified character code (UTF8 integer character code).

````lua
kb.character(0x123);
````



### keyboard.modifier( key )
Returns a bool specifying whether or not the key is a modifier (e.g. ctrl, shift, alt).

````lua
print(kb.modifier("ctrl"));    -- true
print(kb.modifier("return"));  -- false
````


