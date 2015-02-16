
#Device
* [wol](#device_wol)
* [irsend](#device_irsend)
* [keyboard](#device_keyboard)
* [mouse](#device_mouse)
* [switch](#device_switch)
* [vibrate](#device_vibrate)
* [listen](#device_listen)
* [toast](#device_toast)
	

## device
The ``device`` library provides actions that can be performed on the controlling device.

	local dev = libs.device;



### device.wol
In most cases WOL (Wake On LAN) needs to be sent without being connected to a server (i.e if the server is sleeping and you wish to wake it up).
Therefore WOL actions should be specified in the layout.

	<layout>
		<button text="WOL" onclick="@wol" />
	</layout>


### device.irsend( code )
Send an IR code (pronto format) using the device's built-in IR blaster (if available).

	dev.irsend("0000 0000 0000 0000");


### device.keyboard()
Opens the keyboard remote on the device.

	dev.keyboard();


### device.mouse()
Opens the mouse remote on the device.

	dev.mouse();


### device.switch( id )
Opens the remote with the specified ``id`` on the device.

	dev.switch("Unified.Chrome");


### device.vibrate()
Tells the device to perform haptic feedback.

	dev.vibrate();


### device.listen()
Tells the device to start listening for voice control (if available).

	dev.listen();


### device.toast( message )
Shows a quick message (toast) on the device.

	dev.toast("foobar");

