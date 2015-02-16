
# Metadata

Every remote must have a meta file. A typical meta file example is shown below

	meta.name: Foo Bar Remote
	meta.author: Awesome Remote Developer
	meta.description: A fantastic remote for foo bar.
	meta.url: http://awesome-remote-developer.com/

The meta file can also override the default file names for the script, layout, settings, and icon files:

	meta.remote: foo.lua
	meta.layout: foo.xml
	meta.icon: foo.png
	meta.settings: foo.prop

Other meta fields include:

	meta.platform: windows linux mac
	meta.enabled: true/false
	meta.hidden: true/false
	meta.version: 1
	meta.friendly: a voice friendly name
	meta.instance: single/multi
	meta.start: auto/manual
