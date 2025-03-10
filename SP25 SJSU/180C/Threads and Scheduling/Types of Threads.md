### ![[Kernel Level Threads]]
### ![[User Level Threads]]

## How to balance benefits of [[User Level Threads]] and [[Kernel Level Threads]]?
- alternate
- Can compute how many kernel threads are needed based on how CPU bound it is
	- 50% CPU Bound --> 4 Threads
	- 25% CPU Bound --> 8 Threads
	- ![[scheduler activation.excalidraw]]
	- Issue?
		- Kernel knows that threads are IO Blocked, but User Process is responsible for creating the thread...
		- Solution?
			- SIGNALS
			- Send signal to the process that indicates that the process should make a new thread
			- SIGKCRT
		- **Scheduler Activations**
			- swap a blocked thread with a thread that can be run within the process via an upcall
			- this new thread has kernel level privileges though, so permissions are a concern
				- thus not used that often
				- Linux uses a lot of traps instead or requires the users themselves to implement the multiplexing

Ways of mapping
- One-to-one
- Many-to-one
- Many-to-many
	- see diagram above: many user threads (4) to many kernel threads (2)

### Memory Layout for Threads

0xFFFF  KERNEL at TOP
- for when the program needs to make system calls

STACK grows down

HEAP grows up

DATA Section

0x0000 TEXT section from 0 and grows up
- size known at COMPILE TIME

![[memory.excalidraw]]


What can be shared between threads?
- Text
	- Code is Read-only
- Data
	- Global variables
- Heap
	- need to be careful with what addresses are returned when threads ask for new variable, but can be done safely

What CANNOT be shared
- STACK
	- Function calls!
	- otherwise we wouldn't be able to keep track of where we are in the program

When the main thread creates a new thread via fork(), the resulting stack is added to the main threads heap
- need to understand how much the main thread needs for its stack before allocating for the child thread's stack
- gets tricky when trying to guess how much memory a thread will use and then can often lead to a collision... so...

#### Place thread's stack in space between main thread's stack and heap
- use `mmap()` 
- make sure to call at different locations

![[memory with threads.excalidraw]]


### POSIX Thread API (all start with pthread)
- fork() or exec() --> **pthread_create()**, 
	- takes a function for the thread to execute and an arg
	- returns a **tid** (thread id)
- kill() --> **pthread_cancel()**
	- careful when cancelling thread that has resources
- wait() --> **pthread_join(&r)**
	- get back exit code
- exit() --> **pthread_exit()**


