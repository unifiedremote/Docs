
# UTF8
* [utf8](#utf8-1)
* [startwith](#utf8startwith-string-find-)
* [endswith](#utf8endswith-string-find-)
* [iequals](#utf8iequals-a-b-)
* [equals](#utf8equals-a-b-)
* [sub](#utf8sub-string-start-length-)
* [char](#utf8char-string-index)
* [len](#utf8len-string)
* [indexof](#utf8indexof-string-find-)
* [lastindexof](#utf8lastindexof-string-find-)
* [replace](#utf8replace-string-old-new-)
* [contains](#utf8contains-string-find-)
* [trim](#utf8trim-string-)
* [tolower](#utf8tolower-string-)
* [toupper](#utf8toupper-string-)
* [empty](#utf8empty-string-)
* [split](#utf8split-string-delim-)
* [join (table)](#utf8join-delim-table)
* [join (...)](#utf8join-delim-part1-part2-)



## utf8
The ``utf8`` library provides essential string manipulation functions for UTF8 encoded text. 
For best performance, create a UTF8 string instance and re-use it when possible.

````lua
local utf8 = require("utf8");

-- Create new utf8 string instance
local str = utf8.new("hello world!");
local space = str:indexof(" ");

-- Create new utf8 string with a specified length
-- This will truncate strings that are longer than the length
local str = utf8.new("hello world .......", 5);

-- Use the global functions for quick use
local space = utf8.indexof("hello world!", " ");
````

All of the UTF8 library functions listed below can be used both on instances or as global functions. The first ``string`` argument is omitted when using the instance functions as shown in the example above.



### utf8.startswith( string, find )
Checks if ``string`` start with the text ``find``.

````lua
print(utf8.startswith("foo bar", "foo")); -- true
print(utf8.startswith("foo bar", "bar")); -- false
````



### utf8.endswith( string, find )
Checks if ``string`` ends with the text ``find``.

````lua
print(utf8.endswith("foo bar", "foo")); -- false
print(utf8.endswith("foo bar", "bar")); -- true
````



### utf8.iequals( a, b )
Performs a case-insensitive equality check.

````lua
print(utf8.iequals("foo", "FOO")); -- true
print(utf8.iequals("foo", "foo")); -- true
````



### utf8.equals( a, b )
Performs a case-sensitive equality check.

````lua
print(utf8.equals("foo", "FOO")); -- false
print(utf8.equals("foo", "foo")); -- true
````



### utf8.sub( string, start, [length] )
Gets a part of a ``string`` from the ``start`` position to the end of the string or if ``length`` is set to the set length.

````lua
print(utf8.sub("This is a text string", 2, 5);  -- "his i"
print(utf8.sub("This is a text string", 2));    -- "his is a text string"
````



### utf8.char( string, index )
Returns the character at a specific ``index`` in the ``string``

````lua
print(utf8.char("This is a text string", 2)); -- 'i'
````



### utf8.len( string )
Returns the length of a ``string``.

````lua
print(utf8.len("This is a text string")); -- 21
````



### utf8.indexof( string, find )
Returns the first index of ``find`` in the ``string``.

````lua
print(utf8.indexof("This is a text string", "text")); -- 11
````



### utf8.indexoflast( string, find )
Returns the last index of ``find`` in the ``string``.

````lua
print(utf8.indexoflast("This is a text string", "t"));	-- 17
````



### utf8.replace( string, old, new )
Replaces the string ``old`` with the string ``new`` in the ``string``.

````lua
print(utf8.replace("foo bar", "foo", "hello")); -- "hello bar"
````



### utf8.contains( string, find )
Returns true if ``string`` contains the string ``find``.

````lua
print(utf8.contains("foo bar", "bar"));	-- true
print(utf8.contains("foo bar", "xyz"));	-- false
````



### utf8.trim( string )
Removes spaces from the start and end of the ``string``. 

````lua
print(utf8.trim("   foo   "));	-- "foo"
````



### utf8.tolower( string )
Returns a transformed version of the ``string`` where all letters are in lower-case

````lua
print(utf8.tolower("FOO"));	-- "foo"
````



### utf8.toupper( string )
Returns a transformed version of the ``string`` where all letters are in upper-case

````lua
print(utf8.toupper("foo"));	-- "FOO"
````



### utf8.empty( string )
Checkes if the ``string`` is empty.

````lua
print(utf8.empty("foo")); 	-- false
print(utf8.empty("")); 		-- true
print(utf8.empty(" "));		-- false
````



### utf8.split( string, delim )
Splits the ``subject`` string using the specified ``delim``.

````lua
print(utf8.split("foo bar hello world", " ")); -- { "foo", "bar", "hello", "world" }
````



### utf8.join( delim, table )
Joins the items in ``table`` using ``delim``.

````lua
local items = { "foo", "bar" };
print(utf8.join(" ", items)); -- "foo bar";
````



### utf8.join( delim, part1, part2, ... )
Joins all parts using ``delim``.

````lua
print(utf8.join(" ", "foo", "bar")); -- "foo bar";
````


