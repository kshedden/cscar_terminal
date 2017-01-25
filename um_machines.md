Connecting to UM Linux hosts
============================

Here are the main U-M Linux serves that are (relatively) open for
login access:

```
login.itd.umich.edu

scs.itd.umich.edu (forward to mario/luigi)

mario.dsc.umich.edu

luigi.dsc.umich.edu

flux-login.arc-ts.umich.edu (requires two-factor authentication)
```

If you do not have an AFS/IFS allocation you will not be able to
connect to these machines.  You can get an allocation from the
following page:

[https://ifsprovisioning.its.umich.edu/ifs_storage/request]

(note that the allocation will not be created immediately, you may
need to wait 1-2 hours for it to become available)

If you have an AFS allocation you should be able to connect to any of
the machines named above using SSH.  The way you do this depends on
the machine you are using:

* *On MacOS*: Launch the "Terminal" application which should be
  located under Applications/Utilities, or use Spotlight and search
  for "Terminal".

* *On a Linux laptop/desktop*: depends on the distribution, but
   "ctrl-alt-t" wil work on many systems, or find "terminal" or
   "shell" in one of the menus.

* *On a Windows machine*: Use a SSH client.  There are several, but
   Putty [www.chiark.greenend.org.uk/~sgtatham/putty/download.html] is
   free and well-maintained.  You will need to use the menus to set up
   the session.

For Max/Linux once the terminal is open you should be able to connect
using the ssh command, e.g.

```
ssh mario.dsc.umich.edu
```

If your username on your local machine does not match your UM
uniquname, you will need to provide the username, e.g.

```
ssh kshedden@mario.dsc.umich.edu
```

The first time you connect to a machine, you will be asked to accept
and store the machine's host key.

Learning about the machine you have connected to
================================================

General system information:

```
uname -a
```

CPU information:

```
lscpu
```

Disk information:

```
lsblk
```

Current processes:

```
top
```