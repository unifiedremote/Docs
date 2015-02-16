
# Includes

The ``include`` function can be used to simplify reuse of common functionality shared between multiple remotes.
For example you may have a set of actions or functions that you want to use in multiple variations of a remote.
You could place this in a file called ``common.lua``.

	Remotes/
		Example/
			common.lua
			Foo/
				meta.prop
				remote.lua
			Bar/
				meta.prop
				remote.lua

In the implementation for each remote you could then include the common file and use whatever you placed in there.
For example, in the ``remote.lua`` file for the ``Foo`` remote:

	include("../common.lua")

	actions.foo = function ()
		func_from_common("foo");
	end
