
# Cross-Platform

## Metadata

Some remotes can be implemented to work on all OS (Windows, Linux, Mac OS X). However some remotes may only
work for a specific OS. This can be controlled by specifying the ``meta.platform`` field in the meta file for the remote:

	# only for windows
	meta.platform: windows

It can also specify multiple allowed operating systems.

	# for windows and linux
	meta.platform: windows linux


## Qualifiers

Another scenario is where you may want to support multiple OS, but need different implementations for some OS.
This can be controlled by using qualifiers in the file names for the remote. The following example shows how you
could have a default implementation plus a specific implementation for Mac OS X.

	Remotes/
		Example/
			meta.prop
			remote.lua
			remote_osx.lua
			layout.xml
			icon.png

You could also specify a different implementation for each OS:

	Remotes/
		Example/
			meta.prop
			remote_win.lua
			remote_osx.lua
			remote_linux.lua
			layout.xml
			icon.png

File qualifiers can also be applied to layout, property, and icon files.