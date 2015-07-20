
# FS
* [`fs` library](#fs-library)
* [Context](#context)
    * [remotefile](#fs_remotefile)
    * [remotedir](#fs_remotedir)
    * [workingdir](#fs_workingdir)
* [Directories](#directories)
    * [homedir](#fs_homedir)
    * [appdir](#fs_appdir)
    * [special( csidl )](#fsspecial-csidl-)
* [Common](#common)
    * [name( path )](#fsname-path-)
    * [fullname( path )](#fsfullname-path-)
    * [extension( path )](#fsextension-path-)
    * [exists( path )](#fsexists-path-)
    * [copy( source, destination )](#fscopy-source-destination-)
    * [move( source, destination )](#fsmove-source-destination-)
    * [rename( source, destination )](#fsrename-source-destination-)
    * [delete( path, [recursive = false] )](#fsdelete-path-recursive--false-)
* [Path](#path)
    * [parent( path )](#fsparent-path-)
    * [expand( path )](#fsexpand-path-)
    * [path( str )](#fspath-str-)
    * [combine( a, b )](#fscombine-a-b-)
    * [absolute( rel )](#fsabsolute-rel-)
    * [temp()](#fstemp)
* [Tree](#tree)
    * [roots](#fsroots)
    * [files( path, [hidden] )](#fsfiles-path-hidden-)
    * [dirs( path, [hidden] )](#fsdirs-path-hidden-)
    * [list( path, [hidden] )](#fslist-path-hidden-)
* [Create](#create)
    * [createdir( path )](#fscreatedir-path-)
    * [createdirs( path )](#fscreatedirs-path-)
    * [createfile( path )](#fscreatefile-path-)
* [Read & Write](#read--write)
    * [write( path, content )](#fswrite-path-content-)
    * [writelines( path, lines )](#fswritelines-path-lines-)
    * [append( path, content )](#fsappend-path-content-)
    * [appendlines( path, lines )](#fsappendlines-path-lines-)
    * [read( path )](#fsread-path-)
    * [readlines( path )](#fsreadlines-path-)
* [Attributes](#attributes)
    * [isfile( path )](#fsisfile-path-)
    * [isdir( path )](#fsisdir-path-)
    * [ishidden( path )](#fsishidden-path-)
    * [size( path )](#fssize-path-)
    * [created( path )](#fscreated-path-)
    * [modified( path )](#fsmodified-path-)



## `fs` library
The ``fs`` library provides essential file system functiuons for files and folders.

````lua
local fs = require("fs");
````



## Context



### fs.remotefile
Returns the path to the current remote file.

````lua
path = fs.remotefile();
````



### fs.remotedir
Returns the path to the current remote directory.

````lua
path = fs.remotedir();
````



### fs.workingdir
Returns path to the working directory.

````lua
path = fs.workingdir();
````



## Directories



### fs.homedir
Returns the path to the users home directory.

````lua
path = fs.homedir();
````



### fs.appdir
Returns the path to the server directory.

````lua
path = fs.appdir();
````



### fs.special( csidl )
Returns the path for the special folder specified by ``csidl`` (integer or string).

````lua
path = fs.special("startmenu");
path = fs.special("csidl_startmenu");
````

Refer to [MSDN](http://msdn.microsoft.com/en-us/library/windows/desktop/bb762494.aspx) for a list of CSIDL values.



## Common



### fs.name( path )
Returns the name (excluding extanstion) of the specified ``path``. 

````lua
--name will be "log"
name = fs.name("c:\\temp\\log.txt");
````



### fs.fullname( path )
Returns the full name (including extanstion) of the specified ``path``. 

````lua
--fullname will be "log.txt"
fullname = fs.fullname("c:\\temp\\log.txt");
````


### fs.extension( path )
Returns the extension of the specified ``path``.

````lua
--ext will be "txt"
ext = fs.extension("c:\\temp\\log.txt");
````



### fs.exists( path )
Returns true if ``path`` exists.

````lua
exists = fs.exists();
````



### fs.copy( source, destination )
Copys file or folder from ``source`` to ``destination``.

````lua
fs.copy("c:\\temp\\log.txt", "c:\\temp2\\log.txt");
````



### fs.move( source, destination )
Moves file or folder from ``source`` to ``destination``.

````lua
fs.move("c:\\temp\\log.txt", "c:\\temp2\\log.txt");
````



### fs.rename( source, destination )
Renames file or folder from ``source`` to ``destination``.

````lua
fs.rename("c:\\temp\\log.txt", "c:\\temp\\log2.txt");
````



### fs.delete( path, [recursive = false] )
Deletes file or folder localted at ``path`` set ``recursive`` to true if all files and folders in at the path should be deleted. If folder contains files or sub-folders and ``recursive`` set to false the folder will not be deleted

````lua
--deletes the file log.txt
fs.delete("c:\\temp\\log.txt");
--deletes all files and folders located in temp
fs.delete("c:\\temp\\", true);
````



## Path



### fs.parent( path )
Returns path of the parent directory located ath the specified ``path``.

````lua
parent = fs.parent("c:\\temp");
````



### fs.expand( path )
Expands a ``path``.

````lua
fs.expand("c:\\temp\\newfile.txt");
````



### fs.path( str )
Converts a string ``str`` to a valid path.

````lua
--returns "c:\\temp\\log.txt" on windows.
path = fs.path("c:\\temp/log.txt");
````



### fs.combine( a, b )
Combines path ``a`` with path ``b`` handles missing slash between paths.

````lua
--combined will be "c:\\temp\\log.txt"
combined = fs.fullname("c:\\temp", "log.txt");
````



### fs.absolute( rel )
Given a relative path ``rel`` the absolut path is returned

````lua
--abs will be "c:\\temp\\log.txt" if remote is located at "c:\\temp"
abs = fs.absolute("log.txt");
````



### fs.temp()
Returns a unique path name for a temporary file in the system's scratch directory.

````lua
path = fs.temp();
````



## Tree



### fs.roots
Returns a array of all the avalible root directories.

````lua
roots = fs.roots();
````



### fs.files( path, [hidden] )
Returns an array of file located at the specified ``path``.

````lua
files = fs.files("c:\\");

--Print out paths to all files in the directory
for i = 1, #files do
    print(files[i]);
end
````



### fs.dirs( path, [hidden] )
Returns an array of sub-directories located at the specified ``path``.

````lua
dirs = fs.dirs("c:\\");

--Print out paths to all sub-directories in the directory
for i = 1, #dirs do
    print(dirs[i]);
end
````



### fs.list( path, [hidden] )
Returns an array of sub-directories and files located at the specified ``path``.

````lua
items = fs.list("c:\\");

--Print out paths to all sub-directories and files in the directory
for i = 1, #items do
    print(items[i]);
end
````



## Create



### fs.createdir( path )
Create the directory ``path``.

````lua
--if c:\temp\ exists then "newdir" is created.
fs.createdir("c:\\temp\\newdir");
````



### fs.createdirs( path )
Create the directory ``path`` and all requierd parents.

````lua
--if c:\temp\ exists then "newdir" and "anotherdir" is created.
fs.createdirs("c:\\temp\\newdir\\anotherdir");
````



### fs.createfile( path )
Creates a file ``path``.

````lua
--a file "newfile.txt" is created.
fs.createdirs("c:\\temp\\newfile.txt");
````



## Read & Write



### fs.write( path, content )
Write to a file. ``path`` the file to write to and ``content`` the information to write to file. 

````lua
fs.write("c:\\temp\\log.txt", "This is some content");
````



### fs.writelines( path, lines )
Writes a list of ``lines`` to a file located at ``path``. 

````lua
fs.write("c:\\temp\\log.txt", {"Line 1", "Line 2"});
````



### fs.append( path, content )
Appends a string containing ``content`` to a file located at ``path`` 

````lua
fs.append("c:\\temp\\log.txt", "new content");
````



### fs.appendlines( path, lines )
Appends a list of ``lines`` to a file located at ``path`` 

````lua
fs.appendlines("c:\\temp\\log.txt", {"line3", "line4"});
````



### fs.read( path )
Read the entire content from file. ``path`` the file to read from. 

````lua
content = fs.read("c:\\temp\\log.txt");
````



### fs.readlines( path )
Returns a list of lines in the file located at  ``path``

````lua
lines = fs.readlines("c:\\temp\\log.txt");
````



## Attributes



### fs.isfile( path )
Check if a ``path`` is a file or not. Returns true if ``path`` is a file.

````lua
--returns true since "newfile.txt" is a file
res = fs.isfile("c:\\temp\\newfile.txt");
--returns false since "c:\\temp\\" is not a file
res = fs.isfile("c:\\temp\\");
````



### fs.isdir( path )
Check if a ``path`` is a directory or not. Returns true if ``path`` is a directory. 

````lua
--returns false since "newfile.txt" is not a directory
res = fs.isdir("c:\\temp\\newfile.txt");
--returns true since "c:\\temp\\" is a directory
res = fs.isdir("c:\\temp\\");
````



### fs.ishidden( path )
Check if file or directory located at ``path`` is hidden by the filesystem. 

````lua
--returns true if file is hidden.
res = fs.ishidden("c:\\temp\\newfile.txt");
````



### fs.size( path )
Returns the size of a file or directory located at ``path``.

````lua
size = fs.size("c:\\temp\\newfile.txt");
````



### fs.created( path )
Returns the time when the file or directory located at ``path`` was created.

````lua
time = fs.created("c:\\temp\\newfile.txt");
````



### fs.modified( path )
Returns the time when the file or directory located at ``path`` was modified.

````lua
time = fs.modified("c:\\temp\\newfile.txt");
````


