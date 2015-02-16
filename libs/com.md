
# COM
* [com](#com-1)
* [Creating Objects](#Creating-Objects)
* [Finding Objects](#Finding-Objects)
* [Releasing Objects](#Releasing-Objects)



## com
The ``com`` library can be used to create and access COM instances on Windows. It is accessed using the global ``luacom`` variable.

````lua
obj = luacom.CreateObject("PowerPoint.Application");
````

For a complete reference, see refer to the [LuaCOM User Manual](http://www.tecgraf.puc-rio.br/~rcerq/luacom/pub/1.3/luacom-htmldoc/).



## Creating Objects
Creates an instance of the object with the specified id.

````lua
obj = luacom.CreateObject("PowerPoint.Application");
````



## Finding Objects
Finds a running instance of the object with the specified id.

````lua
obj = luacom.GetObject("PowerPoint.Application");
````



## Releasing Objects
It is very important to release all COM objects when they are no longer in use.

````lua
obj = nil;
collectgarbage();
````


