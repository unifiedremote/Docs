
# Server
* [server](#server-1)
* [load](#serverload-id-)
* [unload](#serverunload-id-)
* [run](#serverrun-id-action-extra--)
* [update](#serverupdate-update-update--)
	


## server
The ``server`` library provides helper functions for interacting with the server and othe rremotes.

````lua
local server = require("server");
````



### server.load( id )
Tells the server to load (create) the specified remote.

````lua
server.load("Unified.Chrome");
````



### server.unload( id )
Tells the server to unload (destroy) the specified remote.

````lua
server.unload("Unified.Chrome");
````



### server.run( id, action [,extra, ...] )
Tells the server to run an action for the specified remote.

````lua
server.run("Unified.Chrome", "back");
server.run("Unified.Command", execute", "echo foobar");
````

The server will automatically load (create) the remote.



### server.update( update [,update, ...] )
Perform one or more layout updates for the active remote.

````lua
server.update(
	{ id = "info", text = "foobar" },
	{ id = "tgl", checked = true }
);
````

For simple updates, you can use the [layout](#layout.md) helper library instead.

This function should be used to perform advanced updates such as lists.

````lua
local items = {
	{ type = "item", text = "item 1" },
	{ type = "item", text = "item 2" },
	{ type = "item", text = "item 3" }
};

server.update({ id = "list", children = items });
````

##### Creating dialog

````lua
server.update({ 
	type = "dialog", 
	text = "Hello World!", 
	ontap = "mydialog",
	children = {
		{ type = "button", text = "Foo" },
		{ type = "button", text = "Bar" }
	}
});

actions.mydialog = function(i)
        -- if (i == 0) then Foo! ...
end

````


