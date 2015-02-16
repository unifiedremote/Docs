
# Basic Template

Create a folder for your remote and add 3 files: ``meta.prop`` file, a ``layout.xml`` file, and a ``remote.lua`` file.

	Foo/
	├── meta.prop
	├── remote.lua
	├── layout.xml

<h3>meta.prop</h3>

The meta file describes some basic information about the remote.

	meta.name: <remote name>
	meta.author: <your name>
	meta.description: <write your description here>

<ct>meta.prop</ct>

<h3>layout.xml</h3>

The layout file defines how the remote will look. Typically this will be some rows of controls.

	<?xml version="1.0" encoding="utf-8"?>
	<layout onlaunch="launch">
		<row>
			<button icon="favorite" ontap="open" />
		</row>
		<row>
			<button text="Do it!" ontap="doit" />
		</row>
		<row>
			<button icon="home" ontap="myhome" />
		</row>
	</layout>

<ct>layout.xml</ct>

<h3>remote.lua</h3>

The remote file defines what each control should do. Note how the value in the ``ontap`` fields correspond to action names.

	kb = libs.keyboard;
	script = libs.script;

	--@help Launch application
	actions.launch = function ()
		os.start("foo.exe");
	end

	--@help Example open file
	actions.open = function ()
		os.open("data.txt");
	end

	--@help Example shell script
	actions.doit = function ()
		script.shell("echo foobar");
	end

	--@help Example key stroke
	actions.home = function ()
		kb.stroke("ctrl", "h");
	end

<ct>remote.lua</ct>