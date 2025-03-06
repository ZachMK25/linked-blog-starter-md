![[Drawing 2025-03-05 19.38.48.excalidraw]]

Scheduler prioritizes threads within the current process over switching to a new process
- saves time bc don't need to flush cache when switching context to the other thread

CPU Affinity (Multicore processing specific)
- can pin a process to a specific core to help reduce the amount of context switching that occurs and tries to allow the process to run more often

User Threads vs Kernel Threads
- Kernel Threads are more costly since they run in kernel space and kernel has less memory than the userspace
- User Threads do not need to go to kernel on a context switch --> less costly
- Kernel Threads get administered by kernel --> more closely tied to hardware scheduling
	- can leverage multicore
- 