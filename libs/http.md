
# HTTP
* [http](#http-1)
* [get](#httpget-url-callback-)
* [post](#httppost-url-content-callback-)
* [request](#httprequest-request-callback-)
* [discover](#httpdiscover-options)
* [encodedecode](#encode-decode)
	* [encode](#httpencode-value-)
	* [decode](#httpdecode-value-)
	* [urlencode](#httpurlencode-value-)
	* [urlcomponentencode](#httpurlencode-value-)
	* [urldecode](#httpurldecode-value-)



## http
The ``http`` library can be used for sending HTTP(S) requests.

````lua
local http = require("http");
````



### http.get( url, callback )
Create a simple asynchronous HTTP(S) GET request.

````lua
local url = "http://www.unifiedremote.com/whats-my-ip";
http.get(url, function (err, resp)
	if (err) then return; end
	print(resp);
end);
````



### http.post( url, content, callback )
Create a simple asynchronous HTTP(S) POST request.

````lua
local url = "http://some.web.site/api/do";
local content = "some content to post";
http.post(url, content, function (err, resp)
	if (err) then return; end
	print(resp);	
end);
````



### http.request( request, callback )
Creates a custom HTTP(S) request specified by the ``request`` table.

````lua
local headers = { "key" = "value",
                  "foo" = "bar" };

local req = { method = "post",
		      url = "http://foo.bar/api/do",
		      mime = "text/plain",
		      headers = headers,
		      content = "foobar" };

http.request(req, function (err, resp)
	if (err) then return; end
	print(resp);		
end);
````

The response table looks like this:

````lua
{ status = "200",
  reason = "ok",
  length = "12345",
  mime = "text/plain",
  headers = {...},
  content = "..." };
````



### http.discover( options )
Scans the network for HTTP servers filtered by the specified ``options``.

````lua
-- Find all HTTP servers listening on port 81
local result = http.discover({ port = 81 });
````

Where result is an array of IP addresses:

````lua
{ "192.168.1.23",
  "192.168.1.128" };
````

The options table supports the following values:

````lua
{ mask = "...",			-- IP mask, default: 255.255.255.0
  min = 123,			-- min address, default: 0
  max = 128,			-- max address, default: 254
  port = 81,			-- port number, default: 80
  timeout = 5 };		-- test timeout, default: 1 (sec)
````



## encode/decode



### http.encode( value )
HTML encode the specified value (escapes &<>"').

````lua
http.encode("&<>\"\'");				--> "&amp;&lt;&gt;&quot;&apos;"
````



### http.decode( value )
Decodes all HTML entities (named and numbered dec/hex) in the specified value.

````lua
http.decode("&amp;&#39;&#x27;");	-->	&''
````



### http.urlencode( value )
URL encodes the specified ``value``.

````lua
http.urlencode("foo bar");			--> "foo%20bar"
````



### http.urlcomponentencode( value )
Encodes URL component characters: ?#/=&:

````lua
http.urlcomponentencode("...");
````



### http.urldecode( value )
URL decodes the specified ``value``.

````lua
http.urldecode("foo%20bar");		--> "foo bar"
````


