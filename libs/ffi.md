
# FFI
* [Declaring Functions](#ffi_declare)
* [Standard System Funtions](#ffi_std)
* [External Functions](#ffi_external)
* [Examples](#ex)
	* [Windows Typedefs](#ex_typedefs)
	* [Passing Structs](#ex_structs)
	* [Passing Strings](#ex_strings)
	* [Accessing Structs](#ex_access_struct)
	* [Example Remotes](#ex_remotes)


## ffi
The ``ffi`` library provides foreign function interface calling.

	local ffi = require("ffi");

Refer to the [official documentation from LuaJIT](http://luajit.org/ext_ffi.html) for more details.



### Declaring Functions
You must first declare the functions you wish to use. Refer to the headers or documentation for the library you wish to access.

	ffi.cdef[[
	void foo(int bar);
	]]


### Standard System Functions
To call standard system functions you use ``ffi.C``. On Windows this includes functions in common DLLs such as User32 and Kernel32.

	ffi.cdef[[
	void Sleep(int ms);
	]]

	ffi.C.Sleep(1000);


### External Functions
To call external library functions you must first load the library.

	ffi.cdef[[
	bool SetSuspendState(bool hibernate, bool forceCritical, bool disableWakeEvent);
	]]

	local pp = ffi.load("PowrProf");

	pp.SetSuspendState(true, true, false);


## Examples

### Windows Typedefs
Note that standard Windows typedefs need to be declared explicitly.

	ffi.cdef[[
	typedef void* HWND;
	HWND GetDesktopWindow();
	]]

	local hwnd = ffi.C.GetDesktopWindow();


### Passing Structs
The following example shows how to create a struct and pass it as a pointer.

	ffi.cdef[[
	typedef void* HWND;
	typedef long LONG;
	typedef struct {
		LONG x;
		LONG y;
	} POINT;
	HWND WindowFromPoint(POINT Point);
	]]

	local pos = ffi.new("POINT", 123, 456);
	local hwnd = ffi.C.WindowFromPoint(pos);


### Passing Strings
The following example shows how to create a string and pass it as a pointer.

	ffi.cdef[[
	typedef void* HWND;
	int GetWindowTextA(HWND hwnd, char* text, int maxCount);
	]]

	local hwnd = 12345;
	local text = ffi.new("char[255]");
	ffi.C.GetWindowTextA(hwnd, text, 255);
	text = ffi.string(text, 255);


### Accessing Structs
The following example shows how to access struct members.

	ffi.cdef[[
	typedef void* HWND;
	typedef long LONG;
	typedef struct {
		LONG left;
		LONG top;
		LONG right;
		LONG bottom;
	} RECT;
	bool GetWindowRect(LONG hwnd, RECT* rect);
	]]

	local hwnd = 12345;
	local rect = ffi.new("RECT", 0, 0, 0, 0);
	ffi.C.GetWindowRect(hwnd, rect);

	local width = rect.right - rect.left;
	local height = rect.bottom - rect.top;


### Example Remotes
Some example remotes using the FFI library:

* [Pixel](https://github.com/unifiedremote/Remotes/tree/master/Main/Pixel)
* [Power](https://github.com/unifiedremote/Remotes/tree/master/Main/Power)
* [Spy](https://github.com/unifiedremote/Remotes/tree/master/Main/Spy)
* [Spotify Advanced](https://github.com/unifiedremote/Remotes/tree/master/Main/Spotify%20Advanced)
* [TellStick](https://github.com/unifiedremote/Remotes/tree/master/Main/TellStick)
* [USB-UIRT](https://github.com/unifiedremote/Remotes/tree/master/Main/USB-UIRT)
