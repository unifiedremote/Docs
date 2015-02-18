
# Screen
* [screen](#screen-1)
* [capture](#screencapture-)
* [capture](#screencapture-x-y-w-h-update-)
* [size](#screensize-)



## screen
The ``screen`` library provides a way of easily capturing screenshots.

````lua
-- Create a new buffer
local screen = require("screen").new();
````



### screen.capture( )
Capture the entire screen area.

````lua
x,y,w,h,img = screen.capture();
````



### screen.capture( x, y, w, h, [update]  )
Capture the specified screen area. Optionally return only the area that has changed since the previous call. If no pixels have changed since the previous then the image will be ``nil``.

````lua
x,y,w,h,img = screen.capture(0, 0, 400, 400, true);
if (img) then
  print("area changed");
else
  print("area same");
end
````



### screen.size( )
Get the screen size.

````lua
w,h = screen.size();
````


