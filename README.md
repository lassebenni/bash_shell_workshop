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

You can do a lot of these things on Windows with Powershell, but I  personally find that it not as user-friendly as bash.

I see Bash as the glue that can intuitively paste different programs together to do what you want. It's ideal for scripting, which a nice way to say "hacking stuff together without consideration". But just like other programming languages, it is used to power most of the internet as we know it.

  

  As user "microspino" put it on 20th of may 2010 at 08:22

  > Question: "Is there any use for Bash scripting anymore?"
  >
  > microspino: "Bash is incredibly useful in system administration, web application deployment, data crunching, sutomated backups, even [getting-things-done day by day management](http://smarterware.org/1471/happy-birthday-todotxt-cli) just to name really few of them. I think It's too early for you to judge a "veteran IT soldier" like BASH."

  I salute you, Bash.

---
How to continue?

1. [Read the theory](theory.md)

    The theory behind using a shell, a sprinkle of UNIX and a something ominous called "terminal".

2. Follow the [tutorials](tutorials): 

- [Tutorial Part One](tutorial_part_one.ipynb)

    The notebook contains the basics step-by-step examples for learning bash commands on the computer.

### Tip MyBinder
You can use [MyBinder](https://mybinder.org) to run this repository in the cloud and learn all the commands in the browser by running the notebook (`ipynb` file)!


## Learning by playing:

>  https://web.mit.edu/mprat/Public/web/Terminus/Web/main.html
>
>A interactive web-browser game with bash commands
---

>https://overthewire.org/wargames/bandit/bandit1.html
>
>Game where you "hack" into a remote computer using `ssh`, with detailed steps.
--- 
>  https://github.com/veltman/clmystery/tree/master
>
>A murder mystery, where you, the detective, solve it by pure reasoning and bash skills.

---
>  https://gitlab.com/slackermedia/bashcrawl
>
>"Crawler" game where you traverse the world (directories) with bash.

## Guides:

>  http://mywiki.wooledge.org/BashGuide
>
> Quintessential, most extensive and up to date guide for learning bash. Also has a insanely long FAQ
for all kinds of problems.


--- 
>  https://github.com/denysdovhan/bash-handbook
> Very extensive repository for learning bash.
--- 
>  https://guide.bash.academy/
>
>  Awesome, very extensive guide with practical and human-readable examples. Unfortunately seems to have been abandoned and only the first three chapters have been finished, still worth it.
---
>  https://linuxconfig.org/bash-scripting-tutorial-for-beginners
>
>  Very compact guide with nice videos (using asciinema.org) covering the essentials.
---
> https://zachgoll.github.io/blog/2019/bash-essentials/
>
> Detailed and recent guide on often-used programs.

## Sites to mention:

>  https://tldr.ostera.io/
>
>Hands down, the best bash snippets/examples website I have found.
---
>https://linux.die.net/man/
>
>The `man` pages, online. Enough said.
--- 
> https://devhints.io/bash
>
> Detailed cheat sheet for bash
---
> https://gist.github.com/raineorshine/6927510
>
> Minimal cheat sheet/gist
