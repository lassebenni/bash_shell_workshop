 Programs are executed and then "live inside a process".  These processes are connected to "file descriptors", which are connectors from these process to other concepts on the system, like files, devices, other processed.

What are programs?

> Programs are pre-written instructions that are executed by the system's kernel.

So a program is seen as as a bunch instructions packaged to serve some purpose and can be executed by your computer's main program: the kernel.

Whenever a program's instructions are being run, this active state that the program is in, is called a *process*. The process is said to be "alive" as long as the program continues to run. 

A process can also communicate outside of their own scope, for instance to interact with the computer's filesystem, hardware, or other processes. To perform these interactions, it uses *file descriptors*. The easiest way to think of these, are as streams of input and output in and out the process. File descriptors are numbered, and refer to specific systems.

There are three "default" file descriptors, which are named:

1. "Standard Input" or file descriptor 0.
> This is where most processes receive their input from. By default, processes in your terminal will have their standard input "connected" to your keyboard. More specifically, to the input your terminal program receives.

2. "Standard Output"  or file descriptor 1.
> This is where most processes send their output to. By default, processes in your terminal will have their standard output "connected" to your display. More specifically, your terminal program will display this output in its window.

3. "Standard Error" or file descriptor 2.
>  This is where most processes send their error and informational messages to. By default, processes in your terminal will have their standard error "connected" to your display, just like standard output.

The "Standard Error" filedescriptor isn't "special" in any way, it happens to be chosen for displaying error information but it can be used to display messages.

> Q: Why would a program need file descriptors?

Whenever a program needs to send its output to another programs input, or any place other than the computer display it needs to specify this with a file descriptor. This information flow (of bytes) is called a *stream*.

> Q: Can you replay the output of a program?

No, the programs output stream is ephemeral, and is lost after processing by another program. Streams can be forwarded, not replayed.


# What is a file really?
> It may be useful to explain how files work at the lowest level:
A file is a stream of bytes, zero or more in length. A byte is 8 bits. Since there are 256 combinations of 8 bits, that means a byte is any number from 0 to 255. So every file is, at its lowest level, a big hunk of numbers ranging from 0 to 255.
>
>It is completely up to programs and users to decide what the numbers "mean." If we want to store text, then it's probably a good idea to use the numbers as code, where each number is assigned a letter. That's what ASCII and Unicode do. If we want to display text, then it's probably a good idea to build a device or write a program that can take these numbers and display a bitmap looking like the corresponding ASCII/Unicode code. That's what terminals and terminal emulators do.
>
>Of course, for graphics, we probably want the numbers to represent pixels and their colors. Then we'll need a program that goes through the file, reads all the bytes, and renders the picture accordingly. A terminal emulator is expecting the bytes to be ASCII/Unicode numbers and is going to behave differently, for the same chunk of bytes (or file).
