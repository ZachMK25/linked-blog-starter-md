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