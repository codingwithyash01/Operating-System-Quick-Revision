1. System Calls

Interface between OS and user programs.

Types: Process control, File management, Device management, Information maintenance.

2. Fork() System Call

Creates a new child process identical to the parent.

Used for multitasking and process execution.

3. User Mode vs Kernel Mode

User Mode: Executes application code with limited privileges.

Kernel Mode: Executes OS core functions with full access to hardware.

4. Process vs Threads

Process: Independent execution unit with its own memory space.

Thread: Lightweight execution unit that shares memory with its parent process.

5. User-Level Threads vs Kernel-Level Threads

User-Level Threads: Managed without kernel support, fast but less efficient.

Kernel-Level Threads: Managed by OS, more overhead but better utilization.

6. Scheduling Algorithms

FCFS (First Come First Serve): Non-preemptive, processes served in order of arrival.

SJF (Shortest Job First): Chooses shortest job first, can be preemptive or non-preemptive.

Round Robin: Preemptive, each process gets fixed CPU time (time quantum).

Priority Scheduling: CPU is allocated based on process priority.
