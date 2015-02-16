
# FS
* [remotefile](#fs_remotefile)
* [remotedir](#fs_remotedir)
* [workingdir](#fs_workingdir)
* [homedir](#fs_homedir)
* [appdir](#fs_appdir)
* [files](#fs_files)
* [dirs](#fs_dirs)
* [list](#fs_list)
* [parent](#fs_parent)
* [name](#fs_name)
* [fullname](#fs_fullname)
* [extension](#fs_extension)
* [combine](#fs_combine)
* [absolute](#fs_absolute)
* [temp](#fs_temp)
* [exists](#fs_exists)
* [copy](#fs_copy)
* [move](#fs_move)
* [rename](#fs_rename)
* [delete](#fs_delete)
* [write](#fs_write)
* [writelines](#fs_writelines)
* [append](#fs_append)
* [appendlines](#fs_appendlines)
* [read](#fs_read)
* [readlines](#fs_readlines)
* [path](#fs_path)
* [createdir](#fs_createdir)
* [createdirs](#fs_createdirs)
* [createfile](#fs_createfile)
* [expand](#fs_expand)
* [roots](#fs_roots)
* [isfile](#fs_isfile)
* [isdir](#fs_isdir)
* [ishidden](#fs_ishidden)
* [size](#fs_size)
* [created](#fs_created)
* [modified](#fs_modified)
* [special](#fs_special)

	


## fs
The ``fs`` library provides essential file system functiuons for files and folders.

	local fs = libs.fs;

### fs.remotefile
Returns the path to the current remote file.

	path = fs.remotefile();

### fs.remotedir
Returns the path to the current remote directory.

	path = fs.remotedir();

### fs.workingdir
Returns path to the working directory.

	path = fs.workingdir();

### fs.homedir
Returns the path to the users home directory.

	path = fs.homedir();

### fs.appdir
Returns the path to the server directory.

	path = fs.appdir();

### fs.files( path )
Returns an array of file located at the specified ``path``.

	files = fs.files("c:\\");

	--Print out paths to all files in the directory
	for i = 1, #files do
		print(files[i]);
	end

### fs.dirs( path )
Returns an array of sub-directories located at the specified ``path``.

	dirs = fs.dirs("c:\\");

	--Print out paths to all sub-directories in the directory
	for i = 1, #dirs do
		print(dirs[i]);
	end

### fs.list( path )
Returns an array of sub-directories and files located at the specified ``path``.

	items = fs.list("c:\\");

	--Print out paths to all sub-directories and files in the directory
	for i = 1, #items do
		print(items[i]);
	end

### fs.parent( path )
Returns path of the parent directory located ath the specified ``path``.

	parent = fs.parent("c:\\temp");

### fs.name( path )
Returns the name (excluding extanstion) of the specified ``path``. 

	--name will be "log"
	name = fs.name("c:\\temp\\log.txt");

### fs.fullname( path )
Returns the full name (including extanstion) of the specified ``path``. 

	--fullname will be "log.txt"
	fullname = fs.fullname("c:\\temp\\log.txt");

### fs.extension( path )
Returns the extension of the specified ``path``. 

	--ext will be "txt"
	ext = fs.extension("c:\\temp\\log.txt");

### fs.combine( a, b )
Combines path ``a`` with path ``b`` handles missing slash between paths.

	--combined will be "c:\\temp\\log.txt"
	combined = fs.fullname("c:\\temp", "log.txt");

### fs.absolute( rel )
Given a relative path ``rel`` the absolut path is returned

	--abs will be "c:\\temp\\log.txt" if remote is located at "c:\\temp"
	abs = fs.absolute("log.txt");

### fs.temp()
Returns a unique path name for a temporary file in the system's scratch directory.

	path = fs.temp();

### fs.exists( path )
Returns true if ``path`` exists.

	exists = fs.exists();

### fs.copy( source, destination )
Copys file or folder from ``source`` to ``destination``.

	fs.copy("c:\\temp\\log.txt", "c:\\temp2\\log.txt");

### fs.move( source, destination )
Moves file or folder from ``source`` to ``destination``.

	fs.move("c:\\temp\\log.txt", "c:\\temp2\\log.txt");

### fs.rename( source, destination )
Renames file or folder from ``source`` to ``destination``.

	fs.rename("c:\\temp\\log.txt", "c:\\temp\\log2.txt");

### fs.delete( path, [recursive = false] )
Deletes file or folder localted at ``path`` set ``recursive`` to true if all files and folders in at the path should be deleted. If folder contains files or sub-folders and ``recursive`` set to false the folder will not be deleted

	--deletes the file log.txt
	fs.delete("c:\\temp\\log.txt");
	--deletes all files and folders located in temp
	fs.delete("c:\\temp\\", true);

### fs.write( path, content )
Write to a file. ``path`` the file to write to and ``content`` the information to write to file. 

	fs.write("c:\\temp\\log.txt", "This is some content");

### fs.writelines( path, lines )
Writes a list of ``lines`` to a file located at ``path``. 

	fs.write("c:\\temp\\log.txt", {"Line 1", "Line 2"});

### fs.append( path, content )
Appends a string containing ``content`` to a file located at ``path`` 

	fs.append("c:\\temp\\log.txt", "new content");

### fs.appendlines( path, lines )
Appends a list of ``lines`` to a file located at ``path`` 

	fs.appendlines("c:\\temp\\log.txt", {"line3", "line4"});

### fs.read( path )
Read the entire content from file. ``path`` the file to read from. 

	content = fs.read("c:\\temp\\log.txt");

### fs.readlines( path )
Returns a list of lines in the file located at  ``path``

	lines = fs.readlines("c:\\temp\\log.txt");


### fs.path( str )
Converts a string ``str`` to a valid path.

	--returns "c:\\temp\\log.txt" on windows. 
	path = fs.path("c:\\temp/log.txt");

### fs.createdir( path )
Create the directory ``path``.

	--if c:\temp\ exists then "newdir" is created.
	fs.createdir("c:\\temp\\newdir");

### fs.createdirs( path )
Create the directory ``path`` and all requierd parents. 

	--if c:\temp\ exists then "newdir" and "anotherdir" is created.
	fs.createdirs("c:\\temp\\newdir\\anotherdir");

### fs.createfile( path )
Creates a file ``path``. 

	--a file "newfile.txt" is created.
	fs.createdirs("c:\\temp\\newfile.txt");

### fs.expand( path )
Expands a ``path``. 

	fs.expand("c:\\temp\\newfile.txt");

### fs.roots
Returns a array of all the avalible root directories.

	roots = fs.roots();

### fs.isfile( path )
Check if a ``path`` is a file or not. Returns true if ``path`` is a file. 

	--returns true since "newfile.txt" is a file
	res = fs.isfile("c:\\temp\\newfile.txt");
	--returns false since "c:\\temp\\" is not a file
	res = fs.isfile("c:\\temp\\");

### fs.isdir( path )
Check if a ``path`` is a directory or not. Returns true if ``path`` is a directory. 

	--returns false since "newfile.txt" is not a directory
	res = fs.isdir("c:\\temp\\newfile.txt");
	--returns true since "c:\\temp\\" is a directory
	res = fs.isdir("c:\\temp\\");

### fs.ishidden( path )
Check if file or directory located at ``path`` is hidden by the filesystem. 

	--returns true if file is hidden.
	res = fs.ishidden("c:\\temp\\newfile.txt");

### fs.size( path )
Returns the size of a file or directory located at ``path``.

	size = fs.size("c:\\temp\\newfile.txt");

### fs.created( path )
Returns the time when the file or directory located at ``path`` was created.

	time = fs.created("c:\\temp\\newfile.txt");

### fs.modified( path )
Returns the time when the file or directory located at ``path`` was modified.

	time = fs.modified("c:\\temp\\newfile.txt");

### fs.special( csidl )
Returns the path for the special folder specified by ``csidl`` (integer or string).

	path = fs.special("startmenu");
	path = fs.special("csidl_startmenu");

Refer to [MSDN](http://msdn.microsoft.com/en-us/library/windows/desktop/bb762494.aspx) for a list of CSIDL values.