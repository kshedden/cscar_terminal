UNIX/Linux background
=====================

Brief history
-------------

1970's: [UNIX](https://en.wikipedia.org/wiki/Unix) is an [operating
system](https://en.wikipedia.org/wiki/Operating_system) developed at
Bell Labs.  It supports multiple users working on a single physical
machine via
[multi-tasking](https://en.wikipedia.org/wiki/Computer_multitasking)
and other means of time-sharing.

1980's: Many commercial versions of UNIX are developed by hardware
vendors.  The [POSIX](https://en.wikipedia.org/wiki/POSIX) effort aims
to standardize some aspects of the OS.

1990's: Two major open-source UNIX "clones" emerge:
[BSD](https://en.wikipedia.org/wiki/Berkeley_Software_Distribution)
and the [Linux kernel](https://en.wikipedia.org/wiki/Linux).
Combining Linux with the tools produced by the [GNU
project](https://en.wikipedia.org/wiki/GNU_Project) results in a
usable UNIX-like system.  Apple adopts a UNIX foundation for
[MacOS](https://en.wikipedia.org/wiki/MacOS).

By 2010 UNIX variants became the main OS running the cloud (search,
web applications) as well as commercial information systems
(databases, etc.).

What's in store for late 2010's and beyond?  [Virtual
machines](https://en.wikipedia.org/wiki/Operating-system-level_virtualization),
container-based architectures, OS support for hardware innovation
(increasing number of cores, flash memory), ...  Almost 50 years from
its origins, UNIX continues to be highly adaptable and relevant OS
framework.

Main components/functionality of an operating system
-----------------------------------------------------

* File system

* Process management

* Networking

* Security/access management

* User interface, shells

* Utility programs

Some terminology
----------------

Terms related to terminals/text interfaces:

* "Text terminal" / "Character oriented terminal"

* [Command line
  interface](https://en.wikipedia.org/wiki/Command-line_interface) --
  a style of user interface that is line-oriented and text-based,
  usually with only basic mouse support (for copy/paste).

* [Text user
  interface](https://en.wikipedia.org/wiki/Text-based_user_interface)
  -- a text-based interface that incorporates some features of
  graphical user interfaces such as menus and buttons, and may support
  a broader range of mouse-driven actions.

* [Shell](https://en.wikipedia.org/wiki/Shell_(computing)) -- a
  program for giving a user access to operating system services,
  traditionally text-based.

Terms related to computer networks:

* [Host](https://en.wikipedia.org/wiki/Host_(network))


Key UNIX principles
-------------------

[UNIX philosophy](https://en.wikipedia.org/wiki/Unix_philosophy)

* Everything is a file

* Hide filesytem implementation details (no named drives)

* C is the central implementation language

* Each program should do one thing well

* Programs should work together and be composable

* Text streams are the universal interface between tools

* "...the power of a system comes more from the relationships among
  programs than from the programs themselves" (Rob Pike)

* "(The) style [of using UNIX is] based on the use of tools: using
  programs separately or in combination to get a job done, rather than
  doing it by hand, by monolithic self-sufficient subsystems, or by
  special-purpose, one-time programs" (Kernighan, Ritchie)