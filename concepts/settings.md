
# Settings

Remotes can also have a settings file that provide configuration settings the remote's implementation.
This makes it easier to configure parameters such as for example login details required for a remote to work. It can
also be used for storage (for example cached values or previous state).


## Format

The format is ``key: value``.

    key1: value1
	key2: value2
	key3: value3


## Location

Settings should be stored in a file called ``settings.prop`` in the directory of the remote.

	Remotes/
	├── Foo/
	│   ├── meta.prop
	│   ├── remote.lua
	│   ├── layout.xml
	│   ├── icon.png
	│   ├── settings.prop


## Using

It is automatically generated if you set settings from your remote.

    actions.foo = function ()
        local foo = settings.foo;
        settings.foo = "bar";
    end

Refer to the [settings](../libs/settings.md) library for more details.


## Defaults

The server manager detects if a settings file is available for a remote. This makes it possible to change
remote settings from the manager. To enable this, default settings must be specified for the remote (the values
can be empty though).

    username:
    password:
    port: 5432

