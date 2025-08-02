---
title: Process
cascade:
  type: docs
---

Today’s computer users rarely run just one program. From browsing in Chrome or
gaming in CS:GO and streaming music on Spotify, multitasking is the norm. To
support this, the system creates the illusion of multiple CPUs — a concept known
as CPU virtualization. This is achieved through a technique called
[time-sharing](https://www.geeksforgeeks.org/operating-systems/time-sharing-operating-system/),
where the CPU rapidly switches between tasks to give each the appearance of
running simultaneously. Each of these running programs is known as a process.

#### What is process?

A process is made up of the program code and the machine state necessary for
execution — including the stack, heap, registers, and other essential
componentss

#### Process API:

The Process API provides essential functionality for managing processes,
including:

- Creating a new process
- Terminating an existing process
- Waiting for a process to complete
- Suspending the current process
- Accessing metadata such as status and performance metrics

We'll define Three simples state for each process.

- **Running** – Actively executing on the CPU
- **Ready** - Prepared to run, waiting to be scheduled by the CPU
- **Blocked** - Waiting for an external event or resource (e.g., I/O operation)
  before it can proceed

As explained above, the state of each process must be saved and restored when it
is paused and resumed. The act of stopping one process, saving its state, and
loading the state of another process to run on the CPU is known as a
[context switch](https://en.wikipedia.org/wiki/Context_switch).

> More information of process state can be find [here](TODO).

The operating system allows us to create and manage processes using the
following system calls:

**Fork**: Creates a new process by duplicating the current one.
[more details](https://man7.org/linux/man-pages/man2/fork.2.html)

**Wait**: Delays the parent’s execution until the child process finishes or
terminates.[more details](https://man7.org/linux/man-pages/man2/wait.2.html)

**Exec**: Calling aother process from this process. (does no't create new one
but load the other process code into current process and run it).
[more details](https://man7.org/linux/man-pages/man3/exec.3.html)

**Pipe**: Create a queue, a uniderctional data channel to be used for
interprocess. [more details](https://man7.org/linux/man-pages/man2/pipe.2.html)

##### Question

After reading these system calls, how can one create a simple prompt using
fork() and wait()?

When one type `> echo "Hello World"` what happends?

> Try to define which is the parent and which is the child. In addition, when
> running a CLI command, are we allowed to type a new command before the last
> one finishes?

When one type `wc "Hello World" > example.txt` what happends?

> When wc is run unix stystem is looking for free file descriptor at 0.

When one type `echo "Hello World" | wc` what happends?

> Try to think of the order of execution and which should wait to another.

Other importent syscall is
[kill](https://man7.org/linux/man-pages/man2/kill.2.html), allowing to send
signals to process.
