
Managed by process through a library

Invisible to OS bc no TCB bc managed by process

Process has own thread scheduler

### Advantages:
- Can create many more threads than kernel threads because of increased User Space memory vs Kernel memory
	- ex: 3GB vs 1GB in maxed out 32-bit system

![[user-thread.excalidraw]]

### Downside:
- Single User-space thread makes a blocking call?
	- EVERY USER THREAD has to wait
	- Solution?
		- ASYNC SYSTEM CALLS
		- process can still block
- Cannot take advantage of multiprocessing
