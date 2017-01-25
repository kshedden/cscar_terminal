Working with the filesystem
===========================

Two major UNIX principles:

* "Everything is a file" -- a file can be a program, data, a device;
  "data" files can have any format and the file name does not need to
  convey the format; no metadata conveying how to interpret file
  contents; no locks (in general)

* The filesystem hides the implementation and hardware configuration;
  what we see as the filesystem on one machine may be physically
  stored on multiple disks of different types and on other computers
  accessible via the network


Basic filesystem commands
-------------------------

The general format of most commands is [command name] [arguments] [flags].

You cam usually obtain documentation for command `cmd` using `cmd
--help` or `man cmd`.

* `pwd` (print working directory)

```
pwd
```

* `ls` (list contents of current directory)

```
ls -a     # don't hide "dot files"
ls -la    # more details
ls -lat   # sort by time
ls -lah   # file sizes in "human readable" form
ls prog*  # wildcard (more below)
```

* `cd` (change directory)

```
cd
cd ..
cd ../../../
cd /
```

* `mv` (move a file)

```
mv data.txt Data_backup.csv
mv * ../newproject
```

* `rm` (remove file)

```
rm filename  # remove a named file
rm *.txt     # remove all files with txt suffix
rm -rf .     # dangerous!
```

UM currently shapshots your home directly roughly every 24 hours and
places the snapshot in `.oldfiles`.

* rmdir (remove directory)

```
rmdir projectdata # directory must be empty
```

* `which` (find the location of a program)

```
which ls
which which
```

* `find` (finds files based on name)

```
find . -name pattern
```

Wildcards
---------

Most commands expand *wildcards* as follows

* `*` matches anything

* `?` matches a single character

* `[...]` matches a range of characters, e.g. `[ax]*` matches all
  files beginning with a or b.


View file contents
------------------

* `less` (allows you to page through a file's contents)

* `cat` (dumps file contents to the screen)


AFS commands
------------

* Your AFS home directory is located at `/afs/umich.edu/user/...`

* `kinit -l25h` (need to run this followed by `aklog` roughly once a
  day if you maintain an open terminal)

* `fs lq`

File permissions
----------------

Files can be readable/writeable/executable (or any combination) by the
"owner", "group", and "others".

Lots of details not covered here.

`chmod u+x` makes a file executable

Executable files
----------------

Call it a "command" or a "program" but it is really "just a file"

You can try to execute a file by typing the file name at the shell
prompt.  First the `PATH` is searched for a file with the given name.

Use `echo $PATH` to see the current PATH value

To execute a file in the current directory use `.\filename`.

Executable files are either native compiled files (binary files), or
text files that are scripts to be executed by an interpreter (first
line must start with a
[shebang](https://en.wikipedia.org/wiki/Shebang_(Unix)) `#!/`