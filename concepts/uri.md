
# URI
This document describes the syntax for the app URIs. These URIs are used for Widgets, Quick Actions, and for controlling
the Unified Remote app from other apps (for example Tasker). It is available for Android and iOS at the moment.

* [Syntax](#syntax)
* [Show](#show-in-app)
* [Remotes and Actions](#remotes-and-actions)
* [Device Actions](#device-actions)
* [Chaning Server](#changing-server)


## Syntax

The scheme used for Unified Remote URIs is ``ur`` and the first segment must be ``intent``. This is followed by one or more key-value pairs,
which defines what the URI command should do.

	ur://intent/key1:value1/key2:value2/...


## Show in App
The ``show`` command can be used to open the app, or open specific screens in the app.

	ur://intent/show:home
	ur://intent/show:status
	ur://intent/show:preferences
	ur://intent/show:servers
	ur://intent/show:remotes


## Remotes and Actions
The ``remote`` command can be used to open a remote.

	ur://intent/remote:Unified.Power

The ``action`` command can be used as well to run a specific action.

	ur://intent/remote:Unified.Power/action:lock

Extras can be specified with the ``extra`` command.

	ur://intent/remote:Core.Input/action:text/extra:foobar



## Device Actions
The ``device`` command can be used to run device actions.

	ur://intent/device:wol
	ur://intent/device:keyboard
	ur://intent/device:keyboard
	ur://intent/device:mouse
	ur://intent/device:switch/extra:Unified.Chrome
	ur://intent/device:vibrate
	ur://intent/device:toast/extra:<message-here>
	ur://intent/device:irsend/extra:<ir-code-here>


## Changing Server
The ``server`` command can be used to switch to a different server.

	ur://intent/server:Test-PC

It can also be used with other commands.

	ur://intent/server:Test-PC/remote:Unified.Power/action:lock