
# Mouse
* [mouse](#mouse-1)
* [click](#mouseclick-button-)
* [moveto](#mousemoveto-x-y-)
* [moveby](#mousemoveby-x-y-)
* [moveraw](#mousemoveraw-x-y-)
* [double](#mousedouble-button-)
* [down](#mousedown-button-)
* [up](#mouseup-button-)
* [vscroll](#mousevscroll-amount-)
* [hscroll](#mousehscroll-amount-)
* [position](#mouseposition)



## mouse
The mouse library provides actions for simulating mouse input. Refer to the [buttons list](/res/buttons.md).

````lua
local ms = libs.mouse;
````



### mouse.click( [button] )
Performs a single click (default left button).

````lua
ms.click();
ms.click("right");
````



### mouse.moveto( x, y )
Moves the mouse cursor to the specified location (screen coordinates).

````lua
ms.moveto(100, 200);
````



### mouse.moveby( dx, dy )
Moves the mouse cursor by the specified amount (screen coordinates).

````lua
ms.moveby(50, -50);
````



### mouse.moveraw( dx, dy )
Moves the mouse cursor by the specified amount (raw input).

````lua
ms.moveraw(-10, 5);
````



### mouse.double( [button] )
Performs a double click (default left button).

````lua
ms.double();
ms.double("right");
````



### mouse.down( [button] )
Presses the mouse button until ``mouse.up`` is called (default left button).

````lua
ms.down();
ms.down("right");
````



### mouse.up( [button] )
Releases the mouse button (default left button).

````lua
ms.up();
ms.up("right");
````



### mouse.vscroll( amount )
Scroll vertically by the specified amount.

````lua
ms.vscroll(10);
ms.vscroll(-10);
````



### mouse.hscroll( amount )
Scroll horizontally by the specified amount.

````lua
ms.hscroll(10);
ms.hscroll(-10);
````



### mouse.position()
Returns the current position of the mouse cursor.

````lua
x,y = ms.position();
````


