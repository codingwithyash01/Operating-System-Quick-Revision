#### System Calls

A system call is a mechanism that allows user programs to request services from the operating system's kernel. When a user-level program needs to perform low-level operations, such as reading from a file, creating a process, or communicating over a network, it cannot do so directly because it doesn’t have the required privileges. Instead, it makes a system call to request the OS to perform the action on its behalf.

#### How System Calls Work

a) Request from User Space: The user program issues a system call, usually by invoking a library function (e.g., read(), write()).

b) Switch to Kernel Mode: The system call triggers a trap or interrupt, switching the CPU from user mode to kernel mode. This gives the OS full access to system resources.

c) Execution in Kernel Space: The OS performs the requested service (e.g., reading from a disk).

d) Return to User Mode: Once completed, the OS returns to user mode, and control goes back to the user program with the result of the system call.

#### Common System Call Categories

a) Process Control: Create, execute, terminate, or manage processes. Examples: fork(), exec(), exit(), wait()

b) File Management: Create, delete, read, write, open, close, and manipulate files. Examples: open(), close(), read(), write(), lseek()

c) Device Management: Request and release device resources, or perform I/O operations. Examples: ioctl(), read(), write()

d) Information Maintenance: Get or set system information, or manage time and date. Examples: getpid(), alarm(), sleep()

e) Communication: Facilitate inter-process communication (IPC) or networking. Examples: pipe(), shmget(), socket(), send()

#### Importance of System Calls

a) Security: By controlling access to hardware, system calls protect critical resources.

b) Abstraction: They provide a higher-level interface, making hardware operations easier for application developers.

c) Resource Management: The OS can manage and allocate resources efficiently by handling all low-level operations.

#### Fork() System Call

The fork() system call in Unix-like operating systems is used to create a new process. When a process calls fork(), it creates a duplicate of itself. This new process is called the child process, while the original process is referred to as the parent process. Both processes continue execution from the point where fork() was called.

#### User Mode vs Kernel Mode

In an operating system, user mode and kernel mode are two distinct operating modes of the CPU that control the level of access a process has to system resources. These modes are part of the OS’s protection mechanism, ensuring system stability and security by controlling which parts of the system can execute critical operations.

1. User Mode

Description: In user mode, applications run with limited privileges. Processes in this mode cannot directly access hardware or modify kernel data.

Access Limitations: Programs running in user mode cannot interact with the hardware directly; they must make system calls to request services from the kernel.

Crash Isolation: Errors or crashes in user mode typically only affect the individual application without impacting the entire system.

Examples: Standard applications like text editors, browsers, and other user-level software operate in user mode.

2. Kernel Mode

Description: Kernel mode has full access to all system resources, including hardware, memory, and CPU.

Full Access: The kernel can execute any CPU instruction and access any memory address.

Privileged Operations: Tasks like managing memory, scheduling processes, and handling interrupts are performed in kernel mode.

Crash Impact: Errors in kernel mode are more critical because they can crash the entire system or lead to security vulnerabilities.

Examples: The OS kernel, device drivers, and other critical system functions operate in kernel mode.

#### Transition Between User Mode and Kernel Mode

When a user application needs to perform an operation that requires higher privileges (like reading a file or accessing hardware), it makes a system call. This causes a mode switch:

a) The CPU switches from user mode to kernel mode.

b) The OS kernel performs the requested operation on behalf of the application.

c) The CPU then switches back to user mode once the task is complete, returning control to the application.

#### Why the Distinction Exists

The distinction between user mode and kernel mode ensures system protection and security by preventing applications from accidentally or maliciously altering critical system components.

#### Process vs Threads

A process is an independent, self-contained program in execution, with its own allocated memory space. Processes run in isolated memory areas, ensuring they do not interfere with each other. While, thread is the smallest unit of execution within a process. Multiple threads can exist within a single process, sharing the same memory space and resources but executing independently.

#### User-Level Threads vs Kernel-Level Threads

User-Level Threads (ULTs): Managed entirely by a user-level thread library within a process, without kernel intervention. The OS kernel is unaware of these threads, treating the entire process as a single-threaded process.

Kernel-Level Threads (KLTs): Managed by the operating system’s kernel. The kernel is fully aware of each thread and can schedule and manage them independently.

#### Scheduling Algorithms

FCFS (First Come First Serve): Non-preemptive, processes served in order of arrival.

SJF (Shortest Job First): Chooses shortest job first, can be preemptive or non-preemptive.

Round Robin: Preemptive, each process gets fixed CPU time (time quantum).

Priority Scheduling: CPU is allocated based on process priority.
