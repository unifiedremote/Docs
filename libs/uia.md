
# UIA
* [root](#uia_root)
* [desktop](#uia_desktop)
* [focused](#uia_focused)
* [frompoint](#uia_frompoint)
* [fromhandle](#uia_fromhandle)
* [find](#uia_find)
* [findby](#uia_findby)
* [child](#uia_child)
* [children](#uia_children)
* [property](#uia_property)
* [name](#uia_name)
* [properties](#uia_properties)
* [firstchild](#uia_firstchild)
* [lastchild](#uia_lastchild)
* [nextsibling](#uia_nextsibling)
* [previoussibling](#uia_previoussibling)
* [setvalue](#uia_setvalue)
* [dodefaultaction](#uia_dodefaultaction)
* [toggle](#uia_toggle)
* [rangesetvalue](#uia_rangesetvalue)


## uia
The ``uia`` library provides access to the Windows Automation API.

	local uia = libs.uia;

Tip: Inspect Objects is a useful utility (included in the Windows SDK).


### uia.root()
Returns the root automation element.

	root = uia.root();



### uia.desktop()
Returns the desktop automation element.

	desktop = uia.desktop();



### uia.focused()
Returns the current focused automation element.

	focused = uia.focused();



### uia.frompoint( x, y )
Returns the automation element at the specified screen coordinates.

	element = uia.frompoint(123, 456);



### uia.fromhandle( hwnd )
Returns the automation element for the specified window handle.

	hwnd = win.find("some_class_name", nil);
	element = uia.fromhandle(hwnd);



### uia.find( element, name [, scope] )
Finds the first element with the given name. Default scope is children.

	-- Finds the first child of desktop named "Netflix".
	desktop = uia.desktop();
	netflix = uia.find(desktop, "Netflix");

Valid scopes are: ``ancestors``, ``children``, ``descendants``, ``element``, ``parent``, ``subtree``.

	-- Finds the first element in the entire subtree of netflix named "PauseResume"
	uia.find(netflix, "PauseResume", "subtree");

Warning: Avoid using subtree on large hierarchies as it can take a long time to complete.



### uia.findby( element, property, type, value [, scope] )
Finds the first element with the given value for the given property name. Default scope is children.

	desktop = uia.desktop();
	foo = uia.findby(desktop, "ProcessId", "int", 3196);

Supported types are: ``string``, ``double``, ``float``, ``int``, ``bool``, ``long``.



### uia.child( parent, index )
Returns the child element at the given index (note 0-index).

	desktop = uia.desktop();
	first = uia.child(desktop, 0);



### uia.children( parent )
Returns an array of all child elements for the given parent.

	desktop = uia.desktop();
	children = uia.children(desktop);



### uia.property( element, name )
Returns the value of the specified property name.

	desktop = uia.desktop();
	name = uia.property(name);



### uia.name( element )
Returns the name of the given element.

	desktop = uia.desktop();
	name = uia.name(desktop);



### uia.properties( e )
Returns a table of properties for the given element.

	desktop = uia.desktop();
	props = uia.properties(desktop);



### uia.firstchild( element )
Returns the first child (or nil) of the specified element.

	desktop = uia.desktop();
	first = uia.firstchild(desktop);



### uia.lastchild( element )
Returns the last child (or nil) of the specified element.

	desktop = uia.desktop();
	last = uia.lastchild(desktop);



### uia.nextsibling( element )
Returns the next sibling (or nil) of the specified element.

	desktop = uia.desktop();
	next = uia.nextsibling(desktop);



### uia.previoussibling( element )
Returns the previous sibling (or nil) of the specified element.

	desktop = uia.desktop();
	previous = uia.previoussibling(desktop);


	
### uia.setvalue( element, value )
Sets the value of an element that implements the ValuePattern.

	element = ...;
	uia.setvalue(element, 50);



### uia.dodefaultaction( element )
Perform the default action of an element that implements the LegacyAccessibilityPattern.

	element = ...;
	uia.dodefaultaction(element);



### uia.toggle( element )
Toggles the state of an element that implements the TogglePattern.

	element = ...;
	uia.toggle(element);



### uia.rangesetvalue( element, value )
Sets the range value of an element that implements the RangeValuePattern.

	element = ...;
	uia.setrangevalue(element, 50);











