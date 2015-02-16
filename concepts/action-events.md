
# Action Events

Action events can be used to perform some functionality before and after an action is executed. This is useful for
executing common functionality for many actions, logging, setup and tear down, filtering actions etc.

	events.preaction = function (name, extras)
		-- Do something before actions are executed...
		return true;
	end

	events.postaction = function (name, extras)
		-- Do something after actions are executed...
	end

	actions.foo = function ()
		-- My foo bar function...
	end

Note that the preaction event should return a boolean value indicating whether or not the action should be executed.
If preaction returns true then the action and consequently the postaction event will be triggered. Otherwise, they won't.
If a preaction event isn't available, then actions will always be triggered.

	events.preaction = function (name, extras)
		-- Ignore all actions named "foo"
		if (name == "foo") then
			return false;
		end
		return true;
	end

It is also possible to implement a catch-all (or fallback) event for actions. This event is used for catching actions
that have not been explicitly defined. This is particularily useful for remotes that may need to use dynamically generated
or variably named actions (where the action names are not know ahead of time). Note that it is executed if and only if an
action is not explicitly implemented.

	events.action = function (name, extras)
		-- Catch undefined actions here...
	end
	