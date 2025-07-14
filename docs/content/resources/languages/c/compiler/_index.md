---
title: Compiler
weight: 1
---

## 🎯 Introduction

A compiler is a program that translates human-readable source code into machine
code a computer can execute. It typically works in several stages: it parses
your code to build an internal representation called an Abstract Syntax Tree
(AST), performs optimizations to improve performance, and finally generates
binary instructions for the target architecture. Popular compilers like GCC (GNU
Compiler Collection) and Clang (part of the LLVM project) both support C, C++,
and other languages. GCC is known for its maturity and wide platform support,
while Clang offers modular design, faster compilation, and helpful error
messages. Together, these tools power much of modern software development, from
low-level system code to high-performance applications

## GCC Compiler

When you run `gcc main.c`, GCC performs **four main steps**, each transforming
your code closer to an executable program:

### 📝 1. Preprocessing (`cpp`)
