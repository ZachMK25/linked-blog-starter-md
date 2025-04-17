
Consult slides for basics, but I'm trying to just understand the content and write any notes that help with that

Memory kinda like a cache
- pages get evicted to disk when they are deemed not needed (by whatever algo)


![[Screenshot 2025-04-16 at 6.55.13 PM.png]]
Frames don't need to be allocated for the blue bit
**SPARSE**

Load lower pages first since those have the code to get started

Need to start a lot of processes at once?
- One page/process, let processes demand more
	- can even start a process with **0 pages**, called **pure demand paging**
		- let program page fault its way to getting the pages it needs

Don't want to deal with switching pages later and can tolerate a bit of a slower start?
- More pages/process

## Page Fault
- Is the invalid bit set because the page isn't loaded into memory, or because the page *does not exist*?
- OS has a way of determining if the page is on disk
- OS puts process to sleep and in IO queue while it fetches the page, then puts in ready queue once the frame is allocated


### EXPECTED ACCESS TIME PROBLEM

When forking, mark memory as Read-Only
- when written to, the memory needs to be allocated a new frame that is writable such that the frame is writable now


## When there is no free frame?
- Linux: Auto-memory killer
	- kills processes taking up a lot of memory
	- think of when a computer freezes, essentially an auto-version of process manager / activity monitor / top to reclaim as much memory as possible


# Page replacement

### bits on a page
- valid
- dirty
- accessed
	- when a process reads or writes to a page --> 1
	- after a while, set back to 0
	- done in hardware (MMU) as software would be really inefficient

![[Drawing 2025-04-16 19.35.40.excalidraw]]

Optimal to access 0 first, since a) we don't need write to disk and b) **locality of reference** dictates that it is unlikely to be used next since it hasn't been accessed in a while

best order:
	1. 0
	2. 1
	3. 2
	4. 3
## Page Replacement Algo
- walkthrough in slides

## Memory Allocation

Num. Page faults determines the "hungriness" of the process for frames
- more page faults --> allocate more frames to process
- vv

## Thrashing
- Steals frames from process A to process B, but A no longer as its working set --> cycle of shuffling frames
- Happens when sum of all **working sets** is larger than physical memory
	- very high page fault rate
	- 
- NOT the same as swap usage space
- 