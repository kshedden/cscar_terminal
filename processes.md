Working with processes and jobs
===============================

A *process* is a program that is currently running on a system.  Most
UNIX servers support multiple users, so a machine may be running a
number of proceses launched by various users, and will also be running
dozens of system processes.  These processes run "simultaneously" and
share system resources through the multi-tasking capabilities of the
OS.

Modern computers have multiple cores, so multi-tasking may involve
running programs on different cores, or having several proceses share
a single core.  If a single program is capable of making use of
multiple cores, it may run on several cores.

A multi-core process utilizes several cores for computing, but has a
single memory allocation.  There are also ways to share memory between
processes, or to coordinate the actions of processes running on
different machines (distributed computing).

A *job* is a related but distinct concept from a process.  A job is a
concept used by the shell, whereas a process is handled by the base
operating system.  Jobs are groups of one or more processes that are
handled by the shell as a unit.  Jobs and processes both have numeric
id's, but they are not the same, and it can be confusing to know when
a tool requires a process id or a job id.

Obtaining process and job information
-------------------------------------

The main command for obtaining process information from the system is
`ps`.  Below are some examples of using `ps`:

```
ps -e  # list all processes

ps -u kshedden # list processes for one user
```

Another useful tool is `top`, which shows information about the
current processes in real time.

The main command for obtaining information about jobs is `jobs`.  We
will discuss this further below.

Foreground and background execution
-----------------------------------

When we launch a program from the command line, it normally runs in
the *foreground*. This means that the command line is blocked and we
cannot use it until the program completes.  Usually, but not always,
you can kill a foreground job using `ctrl-c`.  We will discuss other
ways to kill jobs below.  Here is a job running in the foreground:

```
sleep 5s
```

Alternatively, you can launch a program in the background by placing
an ampersand (&) at the end of the command.  In this case the process
continues running and you are immediately able to continue using the
command line.  Here is a job running in the background:

```
sleep 5s&
```

If you have a job running in the foreground, you can usually suspend
it using `ctrl-z`.  Suspended jobs are not actively running, but they
can be restarted from where they left off.  To practice this, type
`sleep 30s<enter>`, then `ctrl-z`, then `jobs<enter>`.  At this point
you will see the job number for your sleep process.  You can restart
it in the background using `bg #<enter>`, and you can restart it in
the foreground using `fg #<enter>`.

Killing processes
-----------------

As noted above, a foreground process can usually be killed with
`ctrl-c`.  Killing a non-foreground job involves working with the
process id rather than the job id.  If you have a suspended or running
process that you want to kill, first use `ps` to get the process id,
then enter `kill -9 #<enter>` to attempt to kill the process with the
given id (this usually, but not always, will successfully kill the
job).

Background jobs will generally terminate once you log out of the
shell.  To keep a background job running after you exit the shell, use
a terminal multiplexer like
[screen](https://en.wikipedia.org/wiki/GNU_Screen) or
[tmux](https://en.wikipedia.org/wiki/Tmux).
