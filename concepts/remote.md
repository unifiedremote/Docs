
# Remote

The remote script file contains the implementation of the remote's functionality written using the Lua scripting language.
The remote script file contains the handlers for events that occur.
For example, when the remote is created or destroyed, or when it gains or loses focus.

	-- Events
	events.create = function ()
		-- load some resource...
	end

	events.focus = function ()
		-- start some timers...
	end

	events.blur = function ()
		-- stop some timers...
	end

	events.destroy = function ()
		-- unload some resources...
	end

The script file also contains the handlers for actions. These implement the functionality that the remotes can perform,
and the functionality that other remotes (or Widgets or Quick Actions in the app) can link to.

	-- Actions
	actions.foo = function ()
		-- My foo function...
	end

	actions.bar = function ()
		-- My bar function...
	end

	actions.foo_bar = function ()
		-- My foo bar function...
	end

You can have as many actions as you want, and you can name them whatever you want (as long as they are legal Lua literals).
We recommend that you use lower case names with underscore (_) to separate words

## Help Metadata
To make it possible for the app to know what an action do it is important that you add some metadata to each action. There is two different types of meta data that can be sent to the app. The first is a description of what an action do. 
```lua
--@help <Description of action>
```
The second type is what kind of parameters the action accept and an description for each parameter. There can be many different parameters.
```lua
--@param <parameter name>:<type> <description of the parameter>
--@param <parameter name>:<type2> <description 2 of the parameter>
```
There are 10 different types of parameters. 
```
string:   one string
strings:  array of strings
button:   one mouse button
buttons:  array of mouse buttons
key:	  one keyboard key
keys: 	  array of keyboard keys
enum(item1,item2): one value from an enum
enums(item1,item2): array values from an enum
number:   one numeric value
numbers:  array of numeric values
```

Example of all help information used in the remote file:
```lua
--@help string test
--@param s:string this is a string
actions.string = function(s)
end

--@help strings test
--@param ss:strings thease are strings
actions.strings = function(ss)
end

--@help button test
--@param bt:button this is a button
actions.button = function(bt)
end

--@help buttons test
--@param bts:buttons thease are buttons
actions.buttons = function(bts)
end

--@help key test
--@param k:key this is a key
actions.key = function(k)
end

--@help keys test
--@param ks:keys thease are keys
actions.keys = function(ks)
end

--@help enum(hello,hi) test
--@param e:enum(hello,hi) this is a enum
actions.enum = function(e)
end

--@help enums(hello,hi) test
--@param es:enums(hello,hi) thease are enums
actions.enums = function(es)
end

--@help number test
--@param n:number this is a number
actions.number = function(n)
end

--@help numbers test
--@param ns:numbers thease are numbers
actions.numbers = function(ns)
end
```
