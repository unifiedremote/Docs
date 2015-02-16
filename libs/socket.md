
# Socket
* [new](#socketnew)
* [onconnect](#socketonconnect)
* [ondata](#socketondata-data)
* [onclose](#socketonclose)
* [onerror](#socketonerror-err)
* [connect](#socketconnect-host-port)
* [connected](#socketconnected)
* [write](#socketwrite-data)
* [close](#socketclose)



## socket
The ``socket`` library provides a way to easily read and write binary data.

	-- Create a new socket
	local socket = require("socket").new();
	
	-- Attach event handler
	s:onconnect(function ()
		s:write("foo");
	end);
	
	-- Connect socket
	s:connect("localhost", 1234);



### socket.new( )
Creates a new socket.



### socket:onconnect( )
Callback to invoke when connection is established.

	local s = require("socket").new();
	s:onconnect(function ()
	
	end);



### socket:ondata( data )
Callback to invoke when raw ``data`` is received. Use a buffer for easy data handling.

	local s = require("socket").new();
	s:ondata(function (data)
		print(data);
		
		-- read data to buffer
		local b = require("buffer").new("utf8");
		b:write(data);
		print(b:readstring());
	end);



### socket:onclose( )
Callback to invoke when connection is broken.

	local s = require("socket").new();
	s:onconnect(function ()
	
	end);



### socket:onerror( err )
Callback to invoke when an error occurs.

	local s = require("socket").new();
	s:onerror(function ( err )
		print(err);
	end);
	s:connect("asdf", 1234);



### socket:connect( host, port )
Connects to the specifed host and port. Invokes ``onconnect``.

	local s = require("socket").new();
	s:connect("localhost", 1234);



### socket:connected( )
Checks if the socket is currently connected.

	local s = require("socket").new();
	print(s:connected()); -- false



### socket:write( data )
Writes raw data to the socket. Use a buffer for easy data handling.

	local s = require("socket").new();
	s:onconnect(function ()
		-- write raw data
		s:write("abc");
		
		-- write data from buffer
		local b = require("buffer").new("utf8");
		b:writestring("i support unicode åäö");
		s:write(b:read());
	end);



### socket:close( )
Closes the socket if it is connected. Invokes ``onclose``.

	local s = require("socket").new();
	s:onconnect(function ()
		s:close();
	end);


