
# Data
* [data](#data-1)
* [json](#json)
	* [tojson](#data_tojson)
	* [tojsonpretty](#data_tojsonpretty)
	* [fromjson](#data_fromjson)
* [xml](#xml)
	* [fromxml](#data_fromxml)
* [base](#base)
	* [tobase64](#data_tobase64)
	* [frombase64](#data_frombase64)
	* [tobase32](#data_frombase32)
	* [frombase32](#data_frombase32)
* [time](#time)
	* [sec2span](#data_sec2span)
	* [span2sec](#data_span2sec)
	* [timestamp](#)
* [security](#security)
	* [nonce](#)
	* [digest](#)
	* [digesthex](#)



## data
The ``data`` library provides parsers and converts for various data forms.

````lua
local data = require("data");
````



## json



### data.tojson( table )
Converts the Lua table to JSON.

````lua
tbl = { foo = 123, bar = "hello world" };
json = data.tojson(tbl);
````



### data.tojsonpretty( table )
Converts the Lua table to nicely formatted JSON.

````lua
tbl = { foo = 123, bar = "hello world" };
json = data.tojsonpretty(tbl);
````



## xml



### data.fromjson( json )

````lua
json = "{ \"foo\" = 123, \"bar\" = \"hello world\" }";
tbl = data.fromjson(json);
````



### data.fromxml( xml )

````lua
xml = "<foo><bar>hello world</bar></foo>";
root = data.fromxml(xml);
````

An XML element is represented by an object that looks like this:

````lua
{ name = "bar",
  text = "hello world",
  attributes = { ... },
  children = { ... } }
````

The number of child elements can be retreived like this:

````lua
#root.children;
````

A child element is retreived like this:

````lua
root.children[1];
````

Attributes are retreived like this:

````lua
root.attributes["foo"];
````



## base



### data.tobase64( data )
Converts the specified ``data`` to a base-64 encoded string.

````lua
b64str = data.tobase64(...);
````



### data.frombase64( str )
Converts ``str`` from a base-64 encoded string.

````lua
data = data.frombase64("...");
````



### data.tobase32( data )
Converts the specified ``data`` to a base-32 encoded string.

````lua
b32str = data.tobase64(...);
````



### data.frombase32( str )
Converts ``str`` from a base-32 encoded string.

````lua
data = data.frombase32("...");
````



## time



### data.sec2span( seconds )
Converts ``seconds`` to a time span string with the following format: [HH:]MM:SS.

````lua
sec = 1234;
span = data.sec2span(sec);
````



### data.span2sec( span )
Converts a time span string to the number of seconds that it represents.

````lua
span = "12:34";
sec = data.span2sec(span);
````

	
	
### data.timestamp( )
Gets the current UNIX timestamp (milliseconds).

````lua
print(data.timestamp()); -- 1424096219
````
	


## security



### data.nonce( )
Generates an unsigned 64-bit integer nonce.

````lua
data.nonce();
````



### data.digest( name, data )
Computes the binary hash of the ``data`` using the specified digest engine.

Supported engines: ``MD5``, ``SHA1``, ``SHA256``, ``SHA512``, etc. See the OpenSSL documentation for a list of supported digest algorithms.

````lua
data.digest("sha1", "foobar");
````



### data.digesthex( name, data )
Computes the hex hash of the ``data`` using the specified digest engine.

Supported engines: ``MD5``, ``SHA1``, ``SHA256``, ``SHA512``, etc. See the OpenSSL documentation for a list of supported digest algorithms.

````lua
data.digesthex("sha1", "foobar");
````


