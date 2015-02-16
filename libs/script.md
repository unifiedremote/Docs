
# Script
* [Batch](#script_batch)
* [PowerShell](#script_powershell)
* [AppleScript](#script_apple)
* [Shell](#script_shell)
* [Default](#script_default)
	


## script
The ``script`` library makes it easy to execute system scripts from a remote.

	local script = libs.script;

All script functions accept one or more lines to make it easy to write longer scripts.

	output = script.apple(
		"tell application \"Spotify\"",
			"set out to player state",
		"end tell"
	);

The script functions return 3 values:

	out,err,res = script.default(...);

You can easily execute scripts from file using the ``fs`` library:

	local src = libs.fs.read("foo.bat");
	script.batch(src);


### script.batch( [...] )
Execute a Windows Batch script.

	cd = script.batch("echo %cd%");


### script.powershell( [...] )
Execute a Windows PowerShell script.

	process_list = script.powershell(
		"ps | Where-Object { $_.Name -eq \"svchost\" }"
	);


### script.apple( [...] )
Execute an AppleScript.

	path = script.apple("set out to (path to me)");



### script.shell( [...] )
Execute a shell script using the default interpreter (typically ``sh``).
 
	foo = script.shell("echo $PWD");

You can specify a different interpreter with a shebang line:

	foo = script.shell(
		"#!/bin/bash",
		"echo $PWD"
	);

Note that on Windows the ``shell`` function creates a Batch file.

	foo = script.shell("echo %USERNAME%");



### script.default( line, [...] )
Execute the default script depending on platform.

* Windows: ``script.batch``.
* Mac OS X: ``script.apple``.
* Linux/Unix: ``script.shell``.

