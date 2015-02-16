
# COM
* [luacom](#com-1)
* [luacom.CreateObject](#luacomcreateobject-id-)
* [luacom.GetObject](#luacomgetobject-id-)
* [Releasing](#releasing)



## luacom
The ``com`` library can be used to create and access COM instances on Windows. It is accessed using the global ``luacom`` variable.

````lua
obj = luacom.CreateObject("PowerPoint.Application");
````

For a complete reference, see refer to the [LuaCOM User Manual](http://www.tecgraf.puc-rio.br/~rcerq/luacom/pub/1.3/luacom-htmldoc/).



## luacom.CreateObject( id )
Creates an instance of the object with the specified id.

````lua
obj = luacom.CreateObject("PowerPoint.Application");
````



## luacom.GetObject( id )
Finds a running instance of the object with the specified id.

````lua
obj = luacom.GetObject("PowerPoint.Application");
````



## Releasing
It is very important to release all COM objects when they are no longer in use.

````lua
obj = nil;
collectgarbage();
````


