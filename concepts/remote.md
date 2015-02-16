
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