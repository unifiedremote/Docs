
# HTTP
* [get](#http_get)
* [post](#http_post)
* [encode](#http_encode)
* [decode](#http_decode)
* [urlencode](#http_urlencode)
* [urldecode](#http_urldecode)
* [request](#http_request)
* [discover](#http_discover)



## http
The ``http`` library can be used for sending HTTP(S) requests.

	local http = libs.http;



### http.get( url )
Create a simple HTTP GET request and returns the response.

	local resp = http.get("http://www.google.com");

Returns ``nil`` if the request failed, otherwise contains the raw response.



### http.post( url, content )
Create a simple HTTP POST request and returns the response.

	local resp = http.post("http://some.web.site/api/do", "foobar");

Returns ``nil`` if the request failed, otherwise contains the raw response.



### http.encode( value )
HTML encode the specified value (escapes &<>"').

	http.encode("&<>\"\'");				--> "&amp;&lt;&gt;&quot;&apos;"



### http.decode( value )
Decodes all HTML entities (named and numbered dec/hex) in the specified value.

	http.decode("&amp;&#39;&#x27;");	-->	&''



### http.urlencode( value )
URL encodes the specified ``value``.

	http.urlencode("foo bar");			--> "foo%20bar"



### http.urldecode( value )
URL decodes the specified ``value``.

	http.urldecode("foo%20bar");		--> "foo bar"


### http.request( request )
Creates a custom HTTP request specified by the ``request`` table:

	local headers = { "key" = "value",
	                  "foo" = "bar" };

	local req = { method = "post",
			      url = "http://foo.bar/api/do",
			      mime = "text/plain",
			      headers = headers,
			      content = "foobar" };

	local resp = http.request(req);

The response table looks like this:

	{ status = "200",
	  reason = "ok",
	  length = "12345",
	  mime = "text/plain",
	  headers = {...},
	  content = "..." };



### http.discover( options )
Scans the network for HTTP servers filtered by the specified ``options``.

	-- Find all HTTP servers listening on port 81
	local result = http.discover({ port = 81 });

Where result is an array of IP addresses:

	{ "192.168.1.23",
	  "192.168.1.128" };

The options table supports the following values:

	{ mask = "...",			-- IP mask, default: 255.255.255.0
	  min = 123,			-- min address, default: 0
	  max = 128,			-- max address, default: 254
	  port = 81,			-- port number, default: 80
	  timeout = 5 };		-- timeout, default: 1 (sec)
	
