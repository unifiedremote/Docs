
# Layout

The layout file describes the visual components of a remote. For example, the buttons, lists, sliders, etc that the user
sees when they open a remote in the app. The layout is described using XML.

	<?xml version="1.0" encoding="utf-8"?>
	<layout>
		<row>
			<label id="my_label" text="this is a label" />
		</row>
		<row>
			<toggle id="my_toggle" text="this is a toggle button" />
		</row>
		<row>
			<slider id="my_slider" text="this is a slider" />
		</row>
		<row>
			<button text="foo" ontap="foo" />
			<button text="bar" ontap="bar" />
		</row>
	</layout>


## Inline Actions

Actions are either specified by referring to the name of an action in the ``remote.lua`` file, or they can be defined
inline. Inline actions are especially important for actions that should work even if the client isn't connected to a
server (for example Wake On LAN).

    <!-- Inline Action -->
    <button text="foo" ontap="core.mouse.click" />

    <!-- Inline Action with Extras -->
    <button text="foo" ontap="core.keyboard.press,wlin" />

    <!-- Inline Device Action -->
    <button text="foo" ontap="@wol" />
    
    <!-- Inline Send IR -->
    <button text="Volume Up" ontap="@irsend,0000 0000 0000 ... 0000 0000 0000" />
    
