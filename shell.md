Working with the shell
======================

The [shell](https://en.wikipedia.org/wiki/Unix_shell) is the main user
interface layer for the UNIX command line.  There are several shells
available, but
[bash](https://en.wikipedia.org/wiki/Bash_(Unix_shell)) is probably
the most common.

You can determine what shell you are using by typing `echo $SHELL`.
If you want to try another shell just type the name of it into your
current shell, e.g. `csh`, `tcsh`, `dash`, or `sh`.  To exit out of a
shell, you can use the `exit` command or (in some cases) type
`ctrl-d`.

We will focus on the bash shell here and we will only scratch the
surface of what it can do.  Some of what we disuss below is not
strictly speaking part of the shell (e.g. pipes) but since these
features are used through the shell and interact heavily with other
shell features, we discuss these topics here.

Command line history and tab completion
---------------------------------------

Use the up and down arrow keys (or ctrl-p, ctrl-n) to scroll through
your command line history.

Use `!xyz` to rerun the last command that begins with `xyz`.  Add `:p`
to the end, e.g. `!xyz:p` to print the command without executing it.

Type the first few characters of a command or local file and then
"tab" to complete the command if the completion is unique.  If the
completion is not unique, type "tab" twice to list all possible
matches.

Redirect output to a file
-------------------------

The `>` operator sends the output of a command to a file (rather than
to the terminal), for example:

```
lst -lat  > files
cat *.txt > everything.txt
```

If you also want to redirect the "standard error stream" use `>&`
instead of `>`, e.g.

```
python script.py >&output
```

Pipes
-----

Pipes are used to treat the output of one command as the input to
another.  For now we will give two simple examples, and we will see
more complex examples when we discuss using OS tools:

List the directory contents and view the results in the viewer
[less](https://www.gnu.org/software/less):

```
ls -laht | less
```

List the directory contents, but only display the first 10 lines:

```
ls -laht | head -n10
```

Note that stricty speaking, these are "anonymous pipes".  "Named
pipes" (or FIFOs) are different, and are not discussed here.