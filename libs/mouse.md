
# Mouse
* [click](#mouse_click)
* [moveto](#mouse_moveto)
* [moveby](#mouse_moveby)
* [moveraw](#mouse_moveraw)
* [double](#mouse_double)
* [down](#mouse_down)
* [up](#mouse_up)
* [vscroll](#mouse_vscroll)
* [hscroll](#mouse_hscroll)
* [position](#mouse_position)



## mouse
The mouse library provides actions for simulating mouse input. Refer to the [buttons list](/api/res/buttons).

	local ms = libs.mouse;



### mouse.click( [button] )
Performs a single click (default left button).

	ms.click();
	ms.click("right");



### mouse.moveto( x, y )
Moves the mouse cursor to the specified location (screen coordinates).

	ms.moveto(100, 200);



### mouse.moveby( dx, dy )
Moves the mouse cursor by the specified amount (screen coordinates).

	ms.moveby(50, -50);



### mouse.moveraw( dx, dy )
Moves the mouse cursor by the specified amount (raw input).

	ms.moveraw(-10, 5);
	


### mouse.double( [button] )
Performs a double click (default left button).

	ms.double();
	ms.double("right");



### mouse.down( [button] )
Presses the mouse button until ``mouse.up`` is called (default left button).

	ms.down();
	ms.down("right");



### mouse.up( [button] )
Releases the mouse button (default left button).

	ms.up();
	ms.up("right");



### mouse.vscroll( amount )
Scroll vertically by the specified amount.

	ms.vscroll(10);
	ms.vscroll(-10);



### mouse.hscroll( amount )
Scroll horizontally by the specified amount.

	ms.hscroll(10);
	ms.hscroll(-10);



### mouse.position()
Returns the current position of the mouse cursor.

	x,y = mouse.position();