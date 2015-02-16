
# OS
* [os](#os)
* [Extensions](#ext)
	* [sleep](#os_sleep)
	* [open](#os_open)
	* [openall](#os_openall)
	* [start](#os_start)
	* [script](#os_script)
	* [throw](#os_throw)


## os
The ``os`` library is a standard Lua library. It is a global library and does not need to be imported.

	os.clock();

Refer to the [official Lua documentation](http://www.lua.org/manual/5.1/) for more details.





## Extensions
Some additional os functions have been added.


### os.sleep( time )
Sleep execution for ``time`` milliseconds.

	os.sleep(1000);


### os.open( path )
Open the specified file using the default program.

	os.open("C:\file.txt");

It can also be used to open folder on your desktop.

	os.open("C:\foo\");


### os.openall( path )
Open all of the files using the default program in the specified folder (e.g. all music files in a folder).

	os.openall("C:\foo\");


### os.start( command, [arg1], [arg2], [...] )
Start the process or program specified by ``command``

	os.start("foobar.exe");

On Windows ``command`` is also matched against installed applications.

	os.start("spotify");

Arguments can also be passed:

	os.start("ipconfig", "/all");



### os.script( script )
Alias for [libs.script.default](/api/libs/script#script_default).



### os.throw( message )
Generates an error and stops the current action.

	os.throw("something bad happened >.<");
