1. d?
2. b
3. idk
4. d?
	1. they definitely share text and heap, but would they also share stack?
5. idk but we didnt cover scheduling so dont worry
6. fork()
7. n/a synchronization
8. a
9. a
10. c?
11. b?
12. a
13. n/a synchronization
14. n/a synchronization
15. a
16. the PCB is the handle that the kernel uses to keep track of a process as it is put through the scheduler. Important information in the PCB includes
	1. PID
	2. Register values
	3. Memory
	4. State
17. Kernel level threads are more expensive due to the limited memory dedicated to the kernel compared to the user space (ex: 3GB vs 1GB in a 32-bit system). The benefits of kernel level threads are that the operating system is aware of them, allowing for more optimal context switching between threads on the same process (no need to flush the cache). User-threads need to be scheduled independent of the operating system by their own process, which creates additional overhead by running a mini-scheduler within a given process.
	1. *explain how related to function calls and system calls*
18. An upcall (AKA A SIGNAL IN LINUX) is when the kernel sends an interrupt to a process in user space that requires it to be handled immediately rather than waiting for when its convenient for the process
19. pthread cals
	1. pthread_join(): synchronize between threads at a given point, blocking
	2. pthread_create(): spawns a new thread similar to fork()
	3. pthread_cancel(): kills a thread
20. *not sure if this is right* A system call is a function called by a process running in user space that requests the kernel to perform some privileged or restricted action. These actions generally have to deal with accessing hardware or the kernel. It is usually implemented via a **trap** so that the kernel gets interrupted and the process can continue where it left off afterwards
21. n/a synchronization
22. 
	1. When a user thread in the process executes a blocking system call, the entire process is blocked. This is because the operating system is not aware of the user threads and only sees the single process that is now being blocked.
	2. A context switch occurs **within the process scheduler**, switching the register values, stack pointer, and program counter from thread 1 to thread 2. Notably, a memory flush does not occur because the context switch happens within the same process. The values are stored in the respective TCBs that the process manages as part of its mini-scheduler. From the perspective of the kernel/kernel thread, nothing changes
23. ![[Drawing 2025-03-12 13.49.09.excalidraw]]
24. 