
# Server
* [load](#server_load)
* [unload](#server_unload)
* [run](#server_run)
* [update](#server_update)
	


## server
The ``server`` library provides helper functions.

	local server = libs.server;



### server.load( id )
Tells the server to load (create) the specified remote.

	server.load("Unified.Chrome");



### server.unload( id )
Tells the server to unload (destroy) the specified remote.

	server.unload("Unified.Chrome");



### server.run( id, action [,extra, ...] )
Tells the server to run an action for the specified remote.

	server.run("Unified.Chrome", "back");
	server.run("Unified.Command", execute", "echo foobar");

The server will automatically load (create) the remote.



### server.update( update [,update, ...] )
Perform one or more layout updates for the active remote.

	server.update(
		{ id = "info", text = "foobar" },
		{ id = "tgl", checked = true }
	);

This function should be used to perform advanced updates such as lists.

	local items = {
		{ type = "item", text = "item 1" },
		{ type = "item", text = "item 2" },
		{ type = "item", text = "item 3" }
	};

	server.update({ id = "list", children = items });

As well as creating dialogs:

	server.update({ 
		type = "dialog", 
		text = "Hello World!", 
		children = {
			{ type = "button", text = "Foo" },
			{ type = "button", text = "Bar" }
		}
	});
		