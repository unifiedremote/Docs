# Dialogs

## List Dialog
````lua
local items = {
	{ type = "item", text = "item 1" },
	{ type = "item", text = "item 2" },
	{ type = "item", text = "item 3" }
};

server.update({ id = "list", ontap = "mydialog", children = items });

actions.mydialog = function(i)
        -- if (i == 0) then item 1 ...
end

````

## Message Dialog

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

## Input Dialog

````lua
server.update({
	id = "myinputdialog",
	type = "input",
	title = "Write something!", 
	ontap = "myinputdialog_done"
});

actions.myinputdialog_done = function(txt)
        if (is_valid(txt)) then 
		fancy_stuff(txt) ...
	end
end

````
