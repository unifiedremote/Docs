
#Device
* [device](#device-1)
* [wol](#device_wol)
* [irsend](#device_irsend)
* [keyboard](#device_keyboard)
* [mouse](#device_mouse)
* [switch](#device_switch)
* [vibrate](#device_vibrate)
* [listen](#device_listen)
* [toast](#device_toast)
	

## device
The ``device`` library provides actions that can be performed on the client device.

	local dev = libs.device;



### device.wol
In most cases WOL (Wake On LAN) needs to be sent without being connected to a server (i.e if the server is sleeping and you wish to wake it up). Therefore WOL actions should be specified in the layout. See [Inline Actions](../concepts/layout.md) to learn more about this syntax.

````xml
<layout>
	<button text="WOL" onclick="@wol" />
</layout>
````



### device.irsend( code )
Send an IR code (pronto format) using the device's built-in IR blaster (if available).

````lua
dev.irsend("0000 0000 0000 0000");
````



### device.keyboard()
Opens the keyboard remote on the device.

````lua
dev.keyboard();
````



### device.mouse()
Opens the mouse remote on the device.

````lua
dev.mouse();
````



### device.switch( id )
Opens the remote with the specified ``id`` on the device.

````lua
dev.switch("Unified.Chrome");
````



### device.vibrate()
Tells the device to perform haptic feedback.

````lua
dev.vibrate();
````



### device.listen()
Tells the device to start listening for voice control (if available).

````lua
dev.listen();
````



### device.toast( message )
Shows a quick message (toast) on the device.

````lua
dev.toast("foobar");
````


