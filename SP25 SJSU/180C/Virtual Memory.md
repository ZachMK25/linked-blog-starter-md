
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

