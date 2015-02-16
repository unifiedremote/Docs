
# Structure

Remotes are organized into directories:

	Remotes/
	├── Foo/
	│   ├── meta.prop
	│   ├── remote.lua
	│   ├── layout.xml
	│   ├── icon.png
	├── Bar/
	│   ├── meta.prop
	│   ├── remote.lua
	│   ├── layout.xml
	│   ├── icon.png
	...

On start-up, the server scans a set of configured remote directories. The server looks for directories containing ``meta.prop`` files.

The file names shown above are the default names that the server looks for. However, they can also be overriden in the meta file.

