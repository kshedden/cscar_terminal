Working with the filesystem
===========================

Two major UNIX principles:

* "Everything is a file" -- a file can be a program, data, a device;
  "data" files can have any format and the file name does not need to
  convey the format; no metadata conveying how to interpret file
  contents; no locks (in general)

* The filesystem hides the implementation and hardware configuration
  (no C: in UNIX); what we see as the filesystem on one machine may be
  physically stored on multiple disks of different types and on other
  computer


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


View file contents
------------------

* `less` (allows you to page through a file's contents)

* `cat` (dumps file contents to the screen)


AFS commands
------------

* `kinit -l25h` (need to run this roughly once a day if you maintain an
  open terminal)

* `fs lq`