# Changes
* [Server](#server)
* [App](#app)


## Server

### 3.2.5
* Fixed autostart quotes
* Fixed GOMPlayer buttons
* Fixed KMPlayer buttons
* Tweaked MediaMonkey volume

### 3.2.3
* Fixed file manager remote showing hidden files.
* Added fs.list/fs.dirs/fs.files hidden parameter.
* Added Beamer remotes (http://beamer-app.com/)
* Fixed crash when logging disabled.
* Fixed [os.start](/libs/os.md#osstart-command-arg1-arg2--) issue.
* Fixed Spotify Advanced broken due to Spotify update.
* Added [device.server](/libs/device.md#deviceserver-name-) for changing server.
* Added Server Manager remote.

### 3.2
* Fixed server starting as admin after install.
* Fixed hide notification icon not working on Windows.
* Added first version of [web-client](http://localhost:9510/client).
* Fixed [os.start](/libs/os.md#osstart-command-arg1-arg2--) and [os.open](/libs/os.md#osopen-path-args-) issues.
* Fixed web-client authentication.
* Fixed socket crash.
* Added support for [oauth authentication](http://localhost:9510/web/#/status/connect).
* Fixed [os.start](/libs/os.md#osstart-command-arg1-arg2--) on OSX.
* Fixed exe path detection from registry permissions.
* Fixed Linux super key mapping.
* Fixed sluggish mouse issue.
* Fixed Mac tray icon color (white and black).
* Fixed Linux server not stopping.
* Improved manager not to show WAN IP in plain sight.
* Fixed web-client error if no layout groups.
* Fixed slow stopping of HTTP interface.
* Improved manager [log screen](http://localhost:9510/web/#/log).
* Fixed web-client keeps loading if no remotes.
* Fixed function keyboard special characters.
* Renamed keyboard.modifier to [keyboard.ismodifier](/libs/keyboard.md#keyboardismodifier-key-).
* Added [keyboard.iskey](/libs/keyboard.md#keyboardiskey-key-).
* Removed layout parser control ID validation.
* Added automatic backup of old remotes when updating.

### 3.1
* Added async HTTP requests.
* Added Kodi remote.
* Fixed Spotify Advanced issues.
* Fixed foobar200 not always working.
* Improved manager enable/disable remotes.
* Fixed PotPlayer for 64-bit.
* Re-added WMC record button.

## App

### 3.2.3
* Fixed IR compatibility
* Fixed Android Wear voice crash
* Fixed notification crash
* Changed Quick Actions prio
* Fixed various crashes
* Fixed LG IR popup
* Added device action for chaning server

### 3.2
* Fixed license checking issues.
* Added WAN field in manual server screen.
* Added NFC promo code.
* Fixed WOL not working from Widgets.
* Improved Wear notification behavior.

### 3.1
* Added support for LG IR
* Fixed Android Wear crash.
* Fixed performance/battery issue.
* Fixed app starting itself.
* Added support for Wake-on-WAN.
* Various bug fixes and improvements.
