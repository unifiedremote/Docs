
# UTF8
* [startwith](#utf8_startwith)
* [endswith](#utf8_endswith)
* [iequals](#utf8_iequals)
* [equals](#utf8_equals)
* [sub](#utf8_sub)
* [char](#utf8_char)
* [len](#utf8_len)
* [indexof](#utf8_indexof)
* [lastindexof](#utf8_lastindexof)
* [replace](#utf8_replace)
* [contains](#utf8_contains)
* [trim](#utf8_trim)
* [tolower](#utf8_tolower)
* [toupper](#utf8_toupper)
* [empty](#utf8_empty)



## UTF8
The ``utf8`` library provides essential string manipulation functions for UTF8 encoded text. 
For best performance, create a UTF8 string instance and re-use it when possible.

	-- Create new utf8 string instance
	local str = libs.utf8.new("hello world!");
	local space = str:indexof(" ");

	-- Create new utf8 string with a specified length
	-- This will truncate strings that are longer than the length
	local str = libs.utf8.new("hello world .......", 5);

	-- Use the global functions for quick use
	local space = libs.utf8.indexof("hello world!", " ");

All of the UTF8 library functions listed below can be used both on instances or as global functions. The first ``string`` argument is omitted when using the instance functions as shown in the example above.

### utf8.startswith( string, find )
Checks if ``string`` start with the text ``find``.

	utf8.startswith("This is a text string", "This is ");		--> true
	utf8.startswith("This is a text string", "The");			--> false

### utf8.endswith( string, find )
Checks if ``string`` ends with the text ``find``.

	utf8.endswith("This is a text string", "text string");		--> true
	utf8.endswith("This is a text string", "The");				--> false

### utf8.iequals( a, b )
Check if string ``a`` equals string ``b`` in a case-insensitive way
	
	utf8.iequals("foobar", "foobar");							--> true
	utf8.iequals("foobar", "FOOBAR");							--> true

### utf8.equals( a, b )
Check if string ``a`` equals string ``b`` in a case-sensitive way

	--return false since equals is case-sensitive
	res = utf8.iequals("This is a text string", "tHIS IS A TEXT STRING");
	--return true since the first string equals the second sting in a case-sensitive way
	res = utf8.iequals("This is a text string", "This is a text string");

### utf8.sub( string, start, [length] )
Gets a part of a ``string`` from the ``start`` position to the end of the string or if ``lenght`` is set to the set length.

	--returns "his i"
	res = utf8.sub("This is a text string", 2, 5);
	--returns "his is a text string"
	res = utf8.sub("This is a text string", 2);

### utf8.char( string, index )
Returns the character at a specific ``index`` in the ``string``

	--returns 'i'
	res = utf8.char("This is a text string", 2);

### utf8.len( string )
Returns the length of a ``string``.

	--returns 21
	res = utf8.len("This is a text string");

### utf8.indexof( string, find )
Returns the index of ``find`` in the ``string``.

	--returns 11
	res = utf8.indexof("This is a text string", "text");

### utf8.indexoflast( string, find )
Returns the the last index of ``find`` in the ``string``.

	--returns 17
	res = utf8.indexoflast("This is a text string", "t");	

### utf8.replace( string, old, new )
Replaces the string ``old`` with the string ``new`` in the ``string``.

	--returns "This is a utf8 string"
	res = utf8.replace("This is a text string", "text", "utf8");

### utf8.contains( string, find )
Returns true if ``string`` contains the string ``find``.

	--returns true since "This is a text string" contains "text".
	res = utf8.contains("This is a text string", "text");

### utf8.trim( string )
Removes spaces from the start and end of the ``string``. 

	--returns "This is a text string"
	res = utf8.trim("     This is a text string     ");

### utf8.tolower( string )
Returns a transformed version of the ``string`` where all letters are in lower-case

	--returns "this is a text string"
	res = utf8.tolower("ThiS iS A teXt stRiNg");

### utf8.toupper( string )
Returns a transformed version of the ``string`` where all letters are in upper-case

	--returns "THIS IS A TEXT STRING"
	res = utf8.toupper("ThiS iS A teXt stRiNg");

### utf8.empty( string )
Checkes if the ``string`` is empty.

	--returns false
	res = utf8.empty("ThiS iS A teXt stRiNg");
	--returns true
	res = utf8.empty("");
