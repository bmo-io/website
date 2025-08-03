---
title: Direct Execution
cascade:
  type: docs
---

#### Direct Execution

One approach to running a program is to grant it complete access to the hardware
and direct use of system calls. This gives rise to two key challenges:

##### Restriction

To prevent misuse of hardware and operating system resources, the OS separates
execution into two modes: **user mode** and **kernel mode**.

In user mode, a program cannot directly access sensitive resources like the disk
or memory-mapped devices. Instead, if it needs to perform operations such as
I/O, it must request the operating system to do so. One naive way to achieve
this would be to create a new process to handle the request and make the
original (parent) process wait. However, this is inefficient due to the overhead
of frequent process switching. The more efficient solution is the use of a
**trap**, Instead of launching a separate process, the user program sets up the
necessary context (e.g., registers and stack) and issues a trap instruction.
This instruction causes a controlled switch from user mode to kernel mode,
allowing the OS to safely execute the requested operation.

**But how do we connect a trap to the correct system call code?**

Direct memory jumps are dangerous and unreliable. The solution is the use of a
trap table (also called a system call table). When the operating system boots,
it initializes this table with mappings between system call numbers and their
corresponding kernel-mode handler functions. When a trap is triggered with a
specific number, the OS uses the table to determine and safely execute the
correct kernel routine

##### Running multiple processes

Until now, we’ve relied on each process to voluntarily finish before starting
another. However, this approach limits us to running only one process at a time.

To overcome this, we introduce an interface where the operating system can take
control — either when a process makes a system call or after a set amount of
time has passed (via a timer interrupt, storingthe register and calling trap).
At these points, the OS can save the current process’s machine state — including
its registers and stack — into memory. This saved state allows the OS to perform
a context switch, enabling multitasking by switching between processes
efficiently.
