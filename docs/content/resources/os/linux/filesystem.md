---
title: File System
cascade:
  type: docs
---

The term `filesystem` means a way to organize files. Everything in linux is a
file, from screen, sockets, commands, mouse, keyboard etc. Linux everything
under the `root filesystem`, The folder include `.etc` file that is mounted on
computer when start runnning.

## /bin

Represent binaries and include most of the os binaries. some of the you might
know: `ls`,`mv`,`cp`,`pwd` and more commmands. Most of the tools that install
system application mount there binaries in this folder, `apt`, `wget`, `yum`.

**/user/bin:** A representation of a disk. In the past large amount of pc
devices where low in memory, by adding new disk now linux could add new
bineraies. Today pc devices as a large amount of disk space, in other word the
solution is not needed, to fix the double bin folder linux new version linked
`/bin` into `/usr/bin`.

## /boot

Hold boot realated stuff. On system start the files inside this folder are
mounted into RAM. In addition hold the kernel version.

## /dev

No its not short of development but devices. The files inside the folder are
interfaces for the diffrent devices.

## /etc

Include all of the configuration files.

## /home
