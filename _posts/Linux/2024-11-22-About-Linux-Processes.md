---
title: About Linux Processes
date: 2024-11-21 10H:16:00 -0300
categories: [Linux, Processes]
tags: [linux, processes, shell-script, bash, shell, users-on-linux]
author: 0
description:
image:
  path: https://upload.wikimedia.org/wikipedia/commons/thumb/b/b1/Htop.png/640px-Htop.png 
  alt: Picture
---

# About Linux Processes

**Fork,  parent  and child process** 
* In the execution of the processes, some are born from others. The processes that give rise to the others are known as parents and those that depend on them are the children.
*A process is commonly referred to by its process identifier "PID"*
The main process for running user programs and services is systemd. In the most current generic Linux kernel, Systemd is invoked by the "init symbolic" (PID 1), link startup process, during early boot.

**Process status**
A process runs on the CPU, the number of concurrent processes in exact real time depends on the number of cores, likewise more processes run simultaneously on threads that take turns at high speed running on the CPU. 
*State list*
* Running (R): process running
* S Interruptible Sleep (S): The process is sleeping waiting for an event.
* D Uninterruptible Sleep (D): mostly expects an input/output operation.
* T Stopped (T): Process that has stopped because it received some signal.
* Z Defunct (Z): Process that terminated but is still in the process table since its parent is still active.
**Daemons**
Processes that run in the background, often without waiting for any user interaction.

## Tool to visualize processes on Linux
* proc is a pseudo file system commonly found at the "/proc" address, it provides an interface to a kernel data structure and process information can be found here.    
* *ps,top,atop,htop l*the most common tools to visualize processes on Linux* 

**HTOP**
Execute: "$>htop"
Form: Process ID:, User:, PRI:, NI:, VIRT:, RES:, SHR:, S:, CPU:, MEM:.
*Meaning of Fields:*
* PRI: Process priority.
* NI: Priority level
* VIRT: Amount of virtual memory used (swap).
* RES: Memoria RAM
* SHR: Shared Memory
* S: process status {R,S,D,T,Z}
* CPU: % CPU used
* MEM: % RAM used 
* TIME: life time
* Command: command that launched the process

*Keyboard shortcuts*:*
  * F3: Search process by word
  * F4: Filter process by text
  * F5: tree view
  * F6: Sort columns
  * F7: Decrease Process Priority
  * F8: Aumentar prioridad de proceso
  * F9: Kill a process
  * F10: Close htop   
