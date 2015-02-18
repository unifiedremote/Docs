
# Settings
* [settings](#settings-1)
* [get](#get)
* [set](#set)
	


## settings
The ``settings`` library can be used to get and set data that you wish to store. 

The ``settings`` library is global and does not need to be imported.



### get
settings are easily read using the ``settings`` global.

````lua
print("the port is " .. settings.port);
````

For keys containing spaces or other invalid names/characters:

````lua
settings["foo bar 123"];
````



### set
settings can just as easily be changed.

````lua
settings.port = 8080;
````

For keys containing spaces or other invalid names/characters:

````lua
settings["foo bar 123"] = "hello world!";
````
