
# Settings
* [Getting](#settings_get)
* [Setting](#settings_set)
	


## settings
The ``settings`` library can be used to get and set data that you wish to store. 

The ``settings`` library is global and does not need to be imported.



### Getting
settings are easily read using the ``settings`` global.

	print("the port is " .. settings.port);

settings with keys that aren't valid Lua identifiers can also be retreived.

	settings["foo bar 123"];




### Setting
settings can just as easily be changed.

	settings.port = 8080;

Similarily for invalid Lua indentifiers.

	settings["foo bar 123"] = "hello world!";

