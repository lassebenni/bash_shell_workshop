# Bash workshop
By Lasse Benninga 26-03-2020

Table of contents:

[TOC]

---



#### Keywords

#bash #shell #terminal #scripting



#### Key takeaways:

1. Why should I care about bash and where is it used?
2. What is a shell, what is bash?
3. How do I use bash?
4. What are the most used programs and how do I use them ?
5. Where can I learn more?




  ####  Why should I care?

  Bash is used in almost every facet of software development, from handling low level processes, automating simple jobs, creating complex networking operations, interacting with the filesystem on your computer, installing programs that install other programs that install other programs. The possibilities are endless. 

 Most developers will encounter **bash** for the first time when they encounter Linux, where the command line is seen as far less scary than on Windows. For me, the first time I used bash was when I had to use a Linux laptop. Nowadays I use it as standard workflow for interacting with Docker, Linux machines and even my Windows machine. 

  It can do impressive things like find a certain word in all the files on your computer, change 1000 of lines across multiple files, control another computer over the internet (or on your network). You can use it to quickly compare files, create or remove them.

  You can do a lot of these things on Windows with Powershell, but I  (and many others ) personally find that it not as user-friendly as bash.

  I see Bash as the glue that can intuitively paste different programs together to do what you want. It's ideal for scripting, which a nice way to say "hacking stuff together without consideration". But just like other programming languages, it is used to power most of the internet as we know it.

  

  As user "microspino" put it on 20th of may 2010 at 08:22

  > Question: "Is there any use for Bash scripting anymore?"
  >
  > microspino: "Bash is incredibly useful in system administration, web application deployment, data crunching, sutomated backups, even [getting-things-done day by day management](http://smarterware.org/1471/happy-birthday-todotxt-cli) just to name really few of them. I think It's too early for you to judge a "veteran IT soldier" like BASH."

  I salute you, Bash.





---


  # Theory

  ## What the shell?

  > Bash is an extremely popular terminal shell for a variety of *NIX and other systems. Unfortunately, its use and operation is often very unclear. Documentation, both commercial and on the web are often extremely lacking, confusing and misleading. ~ Maarten Billemont

  So evidently bash is a "shell", whatever that means. And the documentation is a mess, perfect.

  Bash is probably the most popular shell used in Linux distributions today.

  > Bash is the shell, or command language interpreter, for the GNU operating system. The name is an acronym for the ‘Bourne-Again SHell’, a pun on Stephen Bourne, the author of the direct ancestor of the current Unix shell `sh`,s

  Ok, so a shell is a command language interpreter? That still doesn't *really* tell me much. I understand a command, and a a language, but what is an interpreter?  Also, what the heck is a "GNU"? Cute about the name, he must've felt honored, unless he came up with it himself, then it's a bit tacky like naming your kid after yourself and adding "JR". GNU is the brainchild of crazed scientist Richard Stallman to create a fully free, free as in beer not free as in idea, Operating System based on UNIX but totally free source code. Neat huh. The idea was to create a own OS kernel based on UNIX, but when the Linux kernel showed up, it was deemed the chosen one. What is  a Kernel you ask? For a moment there, I thought you wouldn't!

  #### Kernel

 A kernel is the most central piece of software in the Operating System. The core, the big small one, the general, the kernel. It directs the rest of the system and should at least perform the following duties: talking to the hardware, controlling the software so it doesn't perform illegal actions. Everything is built around the kernel.

  

  #### But really, what the hell is a Kernel?

  > "So back in the day, everybody who wanted to do anything with a computer had to start from scratch. [...] It was really annoying. Really. Annoying. And so error prone. 
  >
  > […] 
  >
  > So they started making "libraries of code". The libraries would have "include books" for the various things like operating the tape drives and the printers and so on.
  > […]
  >
  > So things got better. But computers weren't all that fast. So it became obvious that even re-building all the drivers for each program was a waste of time. So they started to make "runtime libraries". Basically they'd compile the human-readable code into a machine readable format, then include that. It was much faster. But computer were *really* *really* slow. And it became obvious that "most of the program" you were "loading into memory" was from these libraries. […] 
  > So wouldn't it be cool if we could leave the common stuff in there and just load our unique parts? Basically what if we condensed the stuff we needed to operate the system hardware into one blob that would just always be there? But there were *way* more libraries than there was memory. Like one kilobyte of memory was a *huge* computer.
  >
  > So they paired down only the most common parts. This smallest common part was the "kernel" of the "operating system".
  >
  > So "the kernel" of an operating system is the minimum needed to run the various hardware, the minimum needed to get programs into and out of memory, and the minimum needed to let programs ask the kernel to operate the hardware for them (instead of needing the programs to operate the hardware themselves).

  The kernel is one. One is the kernel.

  

  #### Terminals

  > But terminals are not always physically connected to the machine. There may be some application that "emulates" terminal accepting keystrokes from user and sending them somewhere (xterm and ssh are good examples). There is an API in Kernel called **pseudo terminal** for that. So your **tty** may really be connected to some application instead of real terminal

  Terminals/consoles used to be the physical devices connected to the computer. UNIX-like systems could handle multiple terminal connections in parallel. Nowadays the terminals are almost only virtual: software programs installed on the computer to emulate the terminal and pass user input from the keyboard to the shell.

  

  #### TTY

  >  'tty' is short for 'teletype', which was an actual physical device that had a printer that printed on paper combined with a keyboard. The model the the abstract 'tty' device presents to programs that are using it is basically that there is a teletype on the other end. You send it characters and those characters appear on the teletype. When you read characters from it, those characters represent keys that were typed on a keyboard. ~ Stackoverflow

  So the TTY is abstract concept for a device that connects to the computer and passes commands.

  > A TTY is essentially a pseudo device, call it a kernel resource, which is used by processes to access a specific terminals.

  TTYs are basically emulated nowadays, purely software.

  

  > In its most common meaning, **terminal** is synonymous with tty.

  So often used in conjunction with terminal.

  

  ### What is bash again?

  > Short answer: Bash is a program on your computer like any other, but designed to be easy for you to talk to. Bash was programmed to take commands from you, the user. To do so efficiently, a "language" was created which allows users to "speak" to the bash program and tell it what to do. This language is the bash shell language and you are about to become intimately familiar with it.
  >
  > In essence, a shell program is one that provides users with an interface to interact with other programs. There is a large variety of shell programs, each with their own language. Some popular ones are the C shell (csh), Z shell (zsh), Korn shell (ksh), Bourne shell, Debian's Almquist shell (dash), etc. Bash (also called the Bourne Again shell) is currently the most popular and ubiquitously available shell. Even though all of these shells use seemingly similar syntax, it is important to be fully aware of what shell you're actually writing code for. Often, you'll hear people refer to their code as "shell code", which is about as specific as "source code" is when referring to your Java code. This guide will teach you how to write bash shell code: you should use it only with the bash shell, not any other.
  >
  > Bash uses a method directly counter to the ideas of graphical user interfaces: it runs in a text-only "console" where interaction is mainly limited to displaying characters on your screen and reading them from your keyboard. If you're not yet familiar in this kind of environment, it will feel exceptionally alien, primitive and limiting to you.

  So instead of using the mouse and fancy 256k graphics, we are going back to our roots. The jungle of computing if you will. Where doom lays around every corner (`sudo, not even once.`) but endless riches await in hidden temples (`find / -name "*treasure*"`).

  > Bash is simple, not easy . Or actually not simple at all but you'll be okay if you practice a bit . ~ Lasse



  > It is key that you remember, **bash is a tool**, a single tool in a huge toolbox of programs. Bash alone will only let you do basic things with files and other programs. You will need to understand all the other tools in the toolbox of your system. This knowledge is vast and will come slowly, it is important that you **take the time to learn them well** 

  Get the basics down and you will be set!



  #### The bourn again shell 

  > When the GNU project was formed to create free equivalents of paid-for Unix programs, the shell the GNU developers chose to create was based on the Bourne shell. Because they wanted to (a) fix some of the bugs that were in the Bourne shell and (b) add extra features, they named it the Bourne Again Shell -- a mild pun -- and that name quickly became abbreviated to bash. ~ https://www.reddit.com/r/explainlikeimfive/comments/42ajiq/eli5what_is_gnu_bash/

  So we know about GNU now. We know about the terminal. We know about the shell. Bash is a shell interacting with the kernel by using the terminal, it used to a physical device, called a console, but now its all virtual and run in terminal emulators, get it?

  > A [**shell**](http://en.wikipedia.org/wiki/Shell_(computing)) is the primary interface that users see when they log in, whose primary purpose is to start other programs. (I don't know whether the original metaphor is that the shell is the home environment for the user, or that the shell is what other programs are running in.)

  The shell is the concert hall in which other programs play their music. It sits around the kernel to interact with the user, like a little machine in a box, which I am still convinced a computer, or someone's computer somewhere, is.

  ![img](http://osr507doc.sco.com/en/OSTut/graphics/kernel.gif)

  

  #### Other shells

  > There are many different unix shells. Popular shells for interactive use include [Bash](http://en.wikipedia.org/wiki/Bash_(Unix_shell)) (the default on most Linux installations), [zsh](http://en.wikipedia.org/wiki/Zsh) (which emphasizes power and customizability) and [fish](http://en.wikipedia.org/wiki/Friendly_interactive_shell) (which emphasizes simplicity).

  Alpine images in docker don't have the `bash` shell but use `sh`.

  

  #### Metaphor for it all

  > A console is the telephone, a shell is the minion on the other end of the line that you command to do things, and the language they speak is the equivalent of what kind of shell they are (bash, ksh, powershell, etc). By way of example: If want your minion to give you a list of files, you would say "dir" to a Powershell speaker, and "ls" to a bash or ksh speaker. Like many languages that overlap, all three understand that "cd" means "change directory".

  So input = tty/terminal/console, orchestrator = shell, language = bash/sh/ksh/powershell/fish/myzsh.

  

  ![The terminal program runs in the GUI, the bash program runs in the terminal.](https://guide.bash.academy/img/terminal-bash.png)



----

  # Practical

  ## Starting Bash

  > Assuming that your operating system came with bash installed, you'll find bash as a simple executable program located in one of your system's standard binary directories. A binary is an executable program that contains "binary code" which is executed directly by the system's kernel. 

  So a binary is the executable code, but in what language is that? C? Machine code?

  ### Modes

  > Before we do so, it's important to take note of the two distinct modes of operation that the bash shell supports:

  #### Interactive

  > In interactive mode, the bash shell waits for your commands before performing them. Each command you pass it is executed. While a command is being executed, you cannot interact with the bash shell. As soon as the command is finished, you can interact with bash again while bash awaits your next command.

  So when a program is running, you have to wait until you get control of the shell again.

  

  #### Non-interactive

  > The bash shell can also execute scripts. A script is a pre-written series of commands which bash can execute without needing to ask you what to do next. Scripts are generally saved in files and subsequently used to automate a wide range of tasks.

  This is basically running programs that have either been written by yourself, or someone else (hopefully not someone that has a grudge against you and your peoples, it might be malicious as their temperament).

  #### Terminal

  Bash programs can be run by your computer without direct input, but if you want to directly interact with the bash shell, you should use a terminal.

  >  In the old days, terminals were the hardware devices we used to connect to a computer and interact with it. Nowadays, most terminals are "emulated". That is to say, they are programs on your computer, either graphical or textual, that "emulate" a real terminal in software and create a textual interface for you to use.

  This is actually a interesting point. A terminal used to be a piece of hardware, screen and keyboard that hooked up to a computer system.

  >  Since the 1960s computers have been shared between users. Especially in the early days of computing when computers were extremely expensive the usual paradigm was a central mainframe computer connected to numerous terminals.  ~ https://en.wikipedia.org/wiki/Multiseat_configuration

  Users used to use a terminal, but maybe not even see the computer it was hooked up to.

  

  ## Programs

  What are these craft little things, anyway?

  > In short, a program is a set of pre-written instructions that can be executed by your system's kernel. A program gives instructions to the kernel directly. The kernel is technically also a program, but one that runs constantly and communicates with your hardware instead.

 Programs are executed and then "live inside a process".  These abstract processes are connected to "file descriptors", which are connectors from these process to other concepts on the system, like files, devices, other processed.

  #### STANDARD INPUT or look ma, i'm typing

  > **File descriptor 0** is also called standard input. This is where most processes receive their input from. By default, processes in your terminal will have their standard input "connected" to your keyboard. More specifically, to the input your terminal program receives.

  #### STANDARD OUTPUT or mic check one two

  > **File descriptor 1** is also called standard output. This is where most processes send their output to. By default, processes in your terminal will have their standard output "connected" to your display. More specifically, your terminal program will display this output in its window.



  #### STANDARD ERROR or DAVE, I am afraid I can't do that 

  > **File descriptor 2** is also called standard error. This is where most processes send their error and informational messages to. By default, processes in your terminal will have their standard error "connected" to your display, just like standard output. It's important to understand that standard error is just another plug, just like standard output, which leads to your terminal's display. It isn't dedicated to errors, in fact bash uses it for most of its informational messages as well as your prompt!

 

  

  #### Streams, listen guys its super-duper important

  > If a program needs its output to go to another program's input, as opposed to your display, it will instruct the kernel to connect its standard output to the other program's standard input. Now all the information it sends to its standard output file descriptor will flow into the other program's standard input file descriptor. These flows of information between files, devices and processes are called streams.

**Bytes all the way down**

  > A stream is information (specifically, bytes) flowing through the links between files, devices and processes in a running system. They can transport any kind of bytes, and the receiving end can only consume their bytes in the order they were sent.



**File descriptors are tied to a process and do not share food**

  > It is important to understand that **file descriptors are process specific**: to speak of "standard output" only makes sense when referring to a specific process. In the example above, you'll notice that the first process' standard input is not the same as the second process' standard input. You'll also notice that the first process' FD 1 (standard output) is connected to the second process' FD 0 (standard input). File descriptors do not describe the streams that connect processes, they only describe the process' plugs where these streams can be connected to.

**TLDR:**

>   Each time a program is started, the system creates a running process for it. Processes have plugs, called file descriptors which allow them to connect streams that lead to files, devices or other processes.

----
  # References

  

  ### People 

  Bill Joy - Author of the C shell and co-founder of Sun Microsystems. Author of VI text editor. Developer of BSD (Berkeley Software Distribution) OS based in UNIX. 

  Stephen Bourne - Daddy of the Bourne shell, on which most shells are based. Creator of the `adb` UNIX debugger and master of UNIX.

  

### Quick wins

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
- Difference subshell and child process

  > A subshell environment is a separate shell execution environment created as a duplicate of the parent environment. That execution environment includes things like opened files, umask, working directory, shell variables/functions/aliases... Changes to that subshell environment do not affect the parent environment.

  So subshells are copies that contain the living space of the parent shell, but do not propagate any changes back. Like a identical clone that goes of into the world screaming.

​    

   

  ### Popular programs

  - sort
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

### Bash interactive games/tutorials

  Games:

  https://web.mit.edu/mprat/Public/web/Terminus/Web/main.html

  https://overthewire.org/wargames/bandit/bandit1.html

  https://github.com/veltman/clmystery/tree/master

  https://gitlab.com/slackermedia/bashcrawl

  Guide:

  https://github.com/denysdovhan/bash-handbook

  https://guide.bash.academy/

  

  ### Sites to mention:

  https://tldr.ostera.io/

  https://linux.die.net/man/

  http://mywiki.wooledge.org/BashGuide

  https://guide.bash.academy/

  https://www.youtube.com/watch?v=tc4ROCJYbm0 - AT&T Archives: The UNIX Operating System
