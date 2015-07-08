
# Win
* [kill](#win_kill)
* [close](#win_close)
* [quit](#win_quit)
* [active](#win_active)
* [desktop](#win_desktop)
* [process](#win_process)
* [window](#win_window)
* [title](#win_title)
* [switchto](#win_switchto)
* [switchtowait](#win_switchtowait)
* [list](#win_list)
* [find](#win_find)
* [post](#win_post)
* [send](#win_send)
* [Examples](#Examples)
	* [Updating Controls](#Updating_Controls)



## win
The ``win`` library provides essential functions for the Windows platform.
````lua
	local win = libs.win;
````


### win.kill( process )
Kills the process with the specified process name or ID.
````lua
	win.kill(1234);
	win.kill("calc.exe");
````

### win.close( process )
Sends a ``close`` window message to the specified process name or ID.
````lua
	win.close(1234);
	win.close("calc.exe");
````

### win.quit( process )
Sends a ``quit`` application message to the specified process name or ID.
````lua
	win.quit(1234);
	win.quit("calc.exe");
````

### win.active()
Returns the window handle of the active (foreground) window.
````lua
	hwnd = win.active();
````

### win.desktop()
Returns the window handle of the desktop.
````lua
	hwnd = win.desktop();
````

### win.process( name )
Returns the process ID of the process with the specified name.
````lua
	pid = win.process("calc.exe");
````

### win.window( process )
Returns the window handle of the process with the specified name or ID.
````lua
	hwnd = win.window("calc.exe");
````

### win.title( window )
Returns the title of the specified window handle or process name.
````lua
	title = win.title(1234);
	title = win.title("calc.exe");
````

### win.class( target )
Returns the class name of the specified window or process.
````lua
	cls = win.class(1234);
	cls = win.class("calc.exe");
````

### win.switchto( target )
Changes the active window to the specified window or process.
````lua
	win.switchto(1234);
	win.switchto("calc.exe");
````

### win.switchtowait( target, [timeout] )
Changes the active window to the specified window or process and waits until it becomes active.
````lua
	win.switchtowait(1234);
	win.switchtowait("calc.exe");
````
A timeout can also be specified (default 100 ms).
````lua
	win.switchtowait(1234, 500);
	win.switchtowait("calc.exe", 500);
````

### win.list( [all] )
Returns an array of tasks running on the computer.
````lua
	tasks = win.list();
````
Where each task is represented by an object like this:
````js
	{ Handle = 1234,
	  Title = "foobar",
	  Name = "foobar.exe" }
````
All processes can be listed by specifying ``all`` as ``true``.
````lua
	processes = win.list(true);
````

### win.find( class, title )
Finds the window with the specified ``class`` and/or ``title``.
````lua
	hwnd = win.find("ChromeWidgetWin_1", nil);
	hwnd = win.find(nil, "Calculator");
	hwnd = win.find("foobar_class", "foobar");
````

### win.find( parent, after, class, title )
Finds the window with the specified ``class`` and/or ``title`` with the given ``parent`` and the preceeding child ``after``.
````lua
	parent = win.find("ChromeWidgetWin_1", nil);
	hwnd = win.find(parent, 0, "foobar", nil);
````

### win.findall( parent, class, title, [recursive] )
Returns a list of windows with the specified ``class`` and/or ``title`` for the given ``parent``.
````lua
	-- Find handle to Chrome browser
	parent = win.find("ChromeWidgetWin_1", nil);

	-- List all children windows (i.e. all of the tabs)
	tabs = win.findall(parent, "ChromeWidgetWin_1", nil, true);
````

### win.post( window, message, wparam, lparam )
Posts a message to the specified window and returns if it succeeded.
````lua
	hwnd = win.find("ChromeWidgetWin_1", nil);
	success = win.post(hwnd, 0x1234, 0, 0);
````

### win.send( window, message, wparam, lparam )
Sends a message to the specified window and returns the result.
````lua
	hwnd = win.find("ChromeWidgetWin_1", nil);
	result = win.send(hwnd, 0x1234, 0, 0);
````

### win.findimage( image, [window] )
Performs image matching with the specified ``image`` file.
````lua
	x,y = win.findimage("play_button.png");
````
A specific window handle can be specified, otherwise the entire screen is used.
````lua
	hwnd = win.find("ChromeWidgetWin_1", nil);
	x,y = win.findimage("play_button.png", hwnd);
````
	
