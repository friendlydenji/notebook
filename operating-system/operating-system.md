---
title: Operating System
description: Operating system basic
---
# 5. Operating System

## 5.1. OS Definition
**Operating System** is software or it can be seem as the intermediate between user and hardware that runs on a computing device and manages the hardware and software components that make up a functional computing system 

## 5.2. OS Functions
Hardware management \
Provide interface for users \
Application installation \
Connect hardware \
Interaction between application and hardware \
CPU scheduling \
Process coordination and synchronization \
Resource management \
Access control and protect system \
Integrity maintenance, error control and recovery

## 5.3. OS Types
Base on processing:
* Uniprogramming OS
* Multiprogramming OS
* Time-sharing OS
* Parallel/multiprocessor/tightly-coupled OS
* Clustered/distributed/loosely-coupled  OS
* RTOS

## 5.4. OS Components
Process/thread management \
Primary memory management \
File management \
I/O system management \
Secondary memory management \
Protect system \
Command line interpreter system 

## 5.5. Process
**Process** is the active *application* instant, *application* become *process* when *executable file* loaded into memory (called *process image*) \
**Process layout** is as same as [Memory Layout In C Program](#13-memory-layout) \
**Process initialization step**: allocate identifier, allocate memory for process load, initialize *Process Control Block* (PCB), setup necessary relation (e.g. arrange PCB to queue) \
**PCB** is one of the most important data structure in OS to manage and control the execution of processes, it typically contains the following components:
* ***Process ID*** (PID): unique identifier assigned to each process by the operating system
* ***Program counter*** (PC): address of the next instruction to be executed by the process
* ***Process state***: current state of the process, includes new, ready, running, waiting, terminated, suspended
* ***CPU registers***: values of the processor registers that are being used by the process
* ***Memory management information***: information about the process’s memory allocation, such as the base and limit registers
* ***I/O status information***: information about the process's I/O operations, such as open files and network connections 
* ***Accounting information***: information about the resources used by the process, such as CPU time and memory usage
* ***CPU scheduling information***: information about the process’s priority and scheduling requirements

**Thread** is a segment of a process or a lightweight process, threads share memory, data, resources together \
There are 3 *thread mapping model*
* Multi user thread mapping to single kernel thread: any user thread blocked cause all user thread blocked, user threads can't run parallel because only one user thread can use kernel at one time
* Single user thread mapping to single kernel thread: create a user thread also create a kernel thread, better concurrency because any user thread blocked don't affect to other threads, limited number of threads
* Multi user thread mapping to multi kernel threads: solve the disavantages of the two below but hard to setting

## OS Scheduling
**Scheduling in OS** is **process scheduling** with PCB: *process scheduling* is a crucial function in OS and PCB in OS plays a vital role in this function \
**Scheduler** include several types:
* **Long-term scheduler** used to schedule *job* (or *process*), decide which program accepted to load into system to run, control system's multiprogramming, maintain both CPU-bound and I/O-bound process
* **Short-term scheduler** used to schedule CPU, decide which process in ready queue will take CPU to run next, trigger events: clock interrupt, I/O interrupt, OS call, signal, ...
* **Mid-term scheduler** (in time-sharing system) used to adjust system's multiprogramming (swap in - move process from memory to disk and swap out - move process from disk to memory)
*Scheduler* will change the CPU control permit for the choosen process, includes:
* Context change 
* User mode change
* Jump to the position in process to running proccess again
*Scheduling* cause time consumption called dispatch latency, time that scheduler stop current process and start another process
**Scheduling criteria** 
* User-oriented: response time - time since process receive request to first request is responsed (time-sharing, interactive system) minimum, turnaround time: time since process loaded into system to process terminated minimum, waiting time: sum of process waiting time in ready queue minumum
* System-oriented: process utilization - schedule to make the CPU busiest maximum, fairness - all process treated peer, throughput - number of done process in a time maximum
**Scheduling features**
* Selection function: used to choose which process in ready queue run usually based on priority, resources request, process 
* Desicion mode: used to choose time to choose selection function for scheduling, there are two desicion mode: non-preemptive - when running process will run until end or blocked by I/O request and preemtive - running process can be interrupt to ready state, more cost but more better response time because no case that a process take CPU too long
**service time** is the time process need CPU in a CPU-I/O period, processes have large service time are CPU-bound processes

## Scheduling algorimth
