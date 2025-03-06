### Kernel threads
- OS is aware of them
### User-level threads
- Live within the process
- OS doesn't know they exist

Optimal way of combining the benefits of the two?
- scheduler activations

Ways of mapping
- One-to-one
- Many-to-one
- Many-to-many

Thread Programming API
- fork() or exec() --> make a thread
- exit() to exit a process --> 
- wait() --> 
- kill() --> 

### Memory Layout for Threads

0xFFFF  KERNEL at TOP
- for when the program needs to make system calls

STACK grows down

HEAP grows up

DATA Section

0x0000 TEXT section from 0 and grows up
- size known at COMPILE TIME

![[Drawing 2025-03-05 18.23.22.excalidraw]]


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

![[Drawing 2025-03-05 18.23.24.excalidraw]]


### POSIX Thread API (all start with pthread)
- fork() or exec() --> **pthread_create()**, 
	- takes a function for the thread to execute and an arg
	- returns a **tid** (thread id)
- kill() --> **pthread_cancel()**
	- careful when cancelling thread that has resources
- wait() --> **pthread_join(&r)**
	- get back exit code
- exit() --> **pthread_exit()**
