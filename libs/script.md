
# Script
* [script](#script-1)
* [batch](#)
* [powershell](#)
* [applescript](#)
* [shell](#)
* [default](#)



## script
The ``script`` library makes it easy to execute system scripts from a remote.

````lua
local script = libs.script;
````

All script functions accept one or more lines to make it easy to write longer scripts.

````lua
output = script.apple(
	"tell application \"Spotify\"",
		"set out to player state",
	"end tell"
);
````

The script functions return 3 values:

````lua
out,err,res = script.default(...);
````

You can easily execute scripts from file using the ``fs`` library:

````lua
local src = libs.fs.read("foo.bat");
script.batch(src);
````



### script.batch( [...] )
Execute a Windows Batch script.

````lua
cd = script.batch("echo %cd%");
````



### script.powershell( [...] )
Execute a Windows PowerShell script.

````lua
process_list = script.powershell(
	"ps | Where-Object { $_.Name -eq \"svchost\" }"
);
````



### script.apple( [...] )
Execute an AppleScript.

````lua
path = script.apple("set out to (path to me)");
````



### script.shell( [...] )
Execute a shell script using the default interpreter (typically ``sh``).
 
 ````lua
foo = script.shell("echo $PWD");
````


You can specify a different interpreter with a shebang line:

````lua
foo = script.shell(
	"#!/bin/bash",
	"echo $PWD"
);
````


Note that on Windows the ``shell`` function creates a Batch file.

````lua
foo = script.shell("echo %USERNAME%");
````



### script.default( line, [...] )
Execute the default script depending on platform.

* Windows: ``script.batch``.
* Mac OS X: ``script.apple``.
* Linux/Unix: ``script.shell``.

