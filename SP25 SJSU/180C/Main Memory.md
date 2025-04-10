Concepts:
- Background
- Swapping
- Contiguous Memory Allocation
- Segmentation
- Paging
- Structure of the Page Table
- Ex: Intel 32- and 64-bit arches
- Ex: ARM

### Background
- program must be brought into memory to run
- main memory and registers are only storage CPU can access directly
- memory unit only sees a stream of addresses + read requests, or address + data and write requests

- Contiguous Mem Alloc
	- Processes needed to be allocated in a single chunk
	- If no chunk of size XB exists (even if the total free space exists), then the process can't run
![[Screenshot 2025-04-09 at 6.47.14 PM.png]]
- Memory Defragmentation
	- moving chunks of memory to create a single, large unused block
	- useful for CMA

- Not able to move a running process
	- soln: compile with -fPIC
	- -fPIE
	- relative addressing instead of absolute

**base pointer** and **limit pointer** define the memory boundaries that a program are allocated

Abstraction from Process
- **logical** address for the process instead of a **physical** address
	- process believes it's running at 0 and CPU adds a translation amount to get its actual location
- can use absolute addressing bc we're using **virtual addresses**

**Address Binding**: 