# Exercise - 5
Write a C program, compile it as module, insert into kernel, check message in log, remove module from kernel.
# Overview
We have implemented hello.c program which will be compiled as a kernel module. This module will print a message when we load the module and will also print a message when we unload the module.
```
krishna@krishna:~/Module$ make
```
This commmand is used to compile the souce code hello.c to create a module called hello.ko
