
# Data
* [tojson](#data_tojson)
* [tojsonpretty](#data_tojsonpretty)
* [fromjson](#data_fromjson)
* [fromxml](#data_fromxml)
* [tobase64](#data_tobase64)
* [frombase64](#data_frombase64)
* [tobase32](#data_frombase32)
* [frombase32](#data_frombase32)
* [sec2span](#data_sec2span)
* [span2sec](#data_span2sec)



## data
The ``data`` library provides parsers and converts for various data forms.

	local data = libs.data;



### data.tojson( table )
Converts the Lua table to JSON.

	tbl = { foo = 123, bar = "hello world" };
	json = data.tojson(tbl);


### data.tojsonpretty( table )
Converts the Lua table to nicely formatted JSON.

	tbl = { foo = 123, bar = "hello world" };
	json = data.tojsonpretty(tbl);


### data.fromjson( json )

	json = "{ \"foo\" = 123, \"bar\" = \"hello world\" }";
	tbl = data.fromjson(json);


### data.fromxml( xml )

	xml = "<foo><bar>hello world</bar></foo>";
	root = data.fromxml(xml);
	
An XML element is represented by an object that looks like this:

	{ name = "bar",
	  text = "hello world",
	  attributes = { ... },
	  children = { ... } }

The number of child elements can be retreived like this:

	#root.children;

A child element is retreived like this:

	root.children[1];

Attributes are retreived like this:

	root.attributes["foo"];



### data.tobase64( data )
Converts the specified ``data`` to a base-64 encoded string.

	b64str = data.tobase64(...);


### data.frombase64( str )
Converts ``str`` from a base-64 encoded string.

	data = data.frombase64("...");


### data.tobase32( data )
Converts the specified ``data`` to a base-32 encoded string.

	b32str = data.tobase64(...);


### data.frombase32( str )
Converts ``str`` from a base-32 encoded string.

	data = data.frombase32("...");


### data.sec2span( seconds )
Converts ``seconds`` to a time span string with the following format: [HH:]MM:SS.

	sec = 1234;
	span = data.sec2span(sec);


### data.span2sec( span )
Converts a time span string to the number of seconds that it represents.

	span = "12:34";
	sec = data.span2sec(span);