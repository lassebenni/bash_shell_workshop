# Bash presentation

Introduction into Shells and Bash

#### Key takeaways:

1. Why should I care?
2. What is a shell, what is bash?
3. Why is bash widely ingrained into modern day computing?
4. How do I access a shell?
5. What are the most used programs and how do I use them ?
6. Where can I learn more?



## Why should I care?

Bash is used in almost every facet of software development, from handling low level processes, automating simple jobs, creating complex networking operations, interacting with the filesystem on your computer, installing programs that install other programs that install other programs. The possibilities are endless. 

Examples:

https://github.com/torvalds/linux

https://packages.ubuntu.com/bionic/admin/

##  What the shell?

> Bash is an extremely popular terminal shell for a variety of *NIX and other systems. Unfortunately, its use and operation is often very unclear. Documentation, both commercial and on the web are often extremely lacking, confusing and misleading. ~ Maarten Billemont

#### Terminals

> But terminals are not always physically connected to the machine. There may be some application that "emulates" terminal accepting keystrokes from user and sending them somewhere (xterm and ssh are good examples). There is an API in Kernel called **pseudo terminal** for that. So your **tty** may really be connected to some application instead of real terminal

#### TTY

>  'tty' is short for 'teletype', which was an actual physical device that had a printer that printed on paper combined with a keyboard. The model the the abstract 'tty' device presents to programs that are using it is basically that there is a teletype on the other end. You send it characters and those characters appear on the teletype. When you read characters from it, those characters represent keys that were typed on a keyboard. ~ Stackoverflow

> A TTY is essentially a pseudo device, call it a kernel resource, which is used by processes to access a specific terminals.

TTYs are basically emulated nowadays, purely software.

![img](http://osr507doc.sco.com/en/OSTut/graphics/kernel.gif)

#### Other shells

> There are many different unix shells. Popular shells for interactive use include [Bash](http://en.wikipedia.org/wiki/Bash_(Unix_shell)) (the default on most Linux installations), [zsh](http://en.wikipedia.org/wiki/Zsh) (which emphasizes power and customizability) and [fish](http://en.wikipedia.org/wiki/Friendly_interactive_shell) (which emphasizes simplicity).



#### Metaphor for it all

> A console is the telephone, a shell is the minion on the other end of the line that you command to do things, and the language they speak is the equivalent of what kind of shell they are (bash, ksh, powershell, etc). By way of example: If want your minion to give you a list of files, you would say "dir" to a Powershell speaker, and "ls" to a bash or ksh speaker. Like many languages that overlap, all three understand that "cd" means "change directory".

So input = tty/terminal/console, orchestrator = shell, language = bash/sh/ksh/powershell/fish/myzsh.



![The terminal program runs in the GUI, the bash program runs in the terminal.](https://guide.bash.academy/img/terminal-bash.png)



### Popular commands
#### ommands to discuss

- Sort
- cat
- read
- for-loop
- grep 
- sed
- if-then
- xargs
- top
- watch
- diff
- comm
- find
- source
- uniq
- man
- apropos
- awk
- cut
- less
- tree
- shuf 

### REMEMBER THESE

- Bash read commands line per name, and spaces matter.

- Files start with a shebang which tell the shell which interpeter to use.

- SPACES MATTER, bash reads arguments one at a time, separated by spaces.

- Bash isn't like many other programming languages: it is very lax and hardly performs any
  code checking so the burden of writing good bash code lies with you.

- You can define functions in bash:

  function(){}

- The execution path of a bash scripts is important, it will be the "living space" of the program and the point from where it interacts with the file system.

- PATH are all user programs that can be run without specifying the absolute path. Linux has a lot of default programs added to the PATH, which means you can type `bash`  instead of `/bin/bash` .

- `~/.bashrc` is the startup script for your user account.

- Programs can be fed with arguments (also called words). Sometimes arguments are prefixed with a dash (-) to specify they are expected arguments or settings.

- Quoting words/arguments in bash is very important, because bash might misinterpret arguments otherwise or expand them into other arguments when you do not want that.

- Variables can be created in bash by using the `NAME=$(command)`  structure. This starts a subshell that performs the command and returns the result for the variable, in this case "NAME".

- Use double quotes when using variables e.g. `echo "${NAME}"` otherwise bash mind expand the argument into multiple.

> Quoting issues are at the core of at least nine out of ten bash problems, and the vast majority of causes for issues people seek help with. Seeing as quoting is actually very easy, a disciplined quoter has that much less to worry about. ~ bash.academy.

It's a simple win.

- Bash is for simple programs, not a replacement for a high-level language such as python.

- Use control+L to clear the terminal

- Use control+C to clear the line or stop a program.

- Control+z to pause a program. Combine with `fg` to commence it, use `bg` to run it in the background.

- control+r to search for commands in the history

- `history` for all the commands you ran.

- `uname` to lookup the build of linux distro

- `tr -c "[:digit:]" " " < /dev/urandom | dd cbs=$COLUMNS conv=unblock | GREP_COLOR="1;32" grep --color "[^ ]"` for the matrix

- ESCAPE + dot to copy the last word of your previous command

- fc to open the previous command on your editor

- special chars:

  ```bash
  $1, $2, $3, ... are the positional parameters.
  "$@" is an array-like construct of all positional parameters, {$1, $2, $3 ...}.
  "$*" is the IFS expansion of all positional parameters, $1 $2 $3 ....
  $# is the number of positional parameters.
  $- current options set for the shell.
  $$ pid of the current shell (not subshell).
  $_ most recent parameter (or the abs path of the command to start the current shell immediately after startup).
  $IFS is the (input) field separator.
  $? is the most recent foreground pipeline exit status.
  $! is the PID of the most recent background command.
  $0 is the name of the shell or shell script.
  ```

  