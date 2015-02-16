
# Layout
* [Updating](#layout_updating)
* [Example](#layout_example)
* [Advanced](#layout_advanced)
	


## layout
The ``layout`` library can be used to modify the properties of controls. It is a global library and does not need to be imported.



### Updating
Controls can easily be modified using the following syntax.

	layout.{id}.{property} = {value};


### Example
	
	<layout>
		<row>
			<toggle id="my_toggle" text="foo" />
		</row>
		<row>
			<label id="my_label" text="foo" />
		</row>
		<row>
			<slider id="my_slider" progress="0" progressmax="100" />
		</row>
	</layout>
	
<ct>layout.xml</ct>

	layout.my_toggle.checked = true;
	layout.my_label.text = "bar";
	layout.my_slider.progress = 50;

<ct>remote.lua</ct>



### Advanced
For advanced layout updates (e.g. lists or dialogs), use [``libs.server.update``](/api/libs/server#server_update) instead.