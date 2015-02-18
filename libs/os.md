
# OS
* [os](#os-1)
* [extensions](#extensions)
  * [sleep](#ossleep-time-)
  * [open](#osopen-path-)
  * [openall](#osopenall-path-)
  * [start](#osstart-command-arg1-arg2-)
  * [script](#osscript-script-)
  * [throw](#osthrow-message-)



## os
The ``os`` library is a standard Lua library. It is a global library and does not need to be imported. 

Refer to the [official Lua documentation](http://www.lua.org/manual/5.1/) for more details.

```lua
os.clock();
```



## extensions

The ``os`` library has been extended with some additional functions.



### os.sleep( time )
Sleep execution for ``time`` milliseconds.

```lua
os.sleep(1000);
```


### os.open( path )
Open the specified file using the default program.

```lua
os.open("C:\\file.txt");
```

It can also be used to open folder on your desktop.

```lua
os.open("C:\\foo\\");
```


### os.openall( path )
Open all of the files using the default program in the specified folder (e.g. all music files in a folder).

```lua
os.openall("C:\\foo\\");
```


### os.start( command, [arg1], [arg2], [...] )
Start the process or program specified by ``command``. It fires and forgets, namely, it does not wait for the process to end nor does it capture the output or result code. For that, use the standard ``os.execute`` function instead.

```lua
os.start("foobar.exe");
```

On Windows ``command`` is also matched against installed applications.

```lua
os.start("spotify");
```

Arguments can also be passed:

```lua
os.start("ipconfig", "/all");
```



### os.script( script )
Alias for [script.default](script.md#scriptdefault-).

```lua
os.script("echo \"foo\"");
```



### os.throw( message )
Generates an error and stops the current action.

```lua
os.throw("something bad happened >.<");
```


