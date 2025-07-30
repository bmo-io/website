---
title: GNU
weight: 1
---

GCC stands for “GNU Compiler Collection”. GCC is an integrated distribution of
compilers for several major programming languages. These languages currently
include C, C++, Objective-C, Objective-C++, Java, Fortran, Ada, and Go. Most of
the compilers for languages other than C have their own names. The C++ compiler
is G++, the Ada compiler is GNAT, and so on. When we talk about compiling one of
those languages, we might refer to that compiler by its own name, or as GCC.
Either is correct.

## Command Options

When you invoke GCC, it normally does preprocessing, compilation, assembly and
linking. The “overall options” allow you to stop this process at an intermediate
stage. For example, the -c option says not to run the linker. Then the output
consists of object files output by the assembler.
[file suffix](https://gcc.gnu.org/onlinedocs/gcc-6.5.0/gcc/Overall-Options.html#Overall-Options)
The gcc program accepts options and file names as operands. Many options have
multi-letter names; therefore multiple single-letter options may not be grouped:
-dv is very different from ‘-d -v’.
