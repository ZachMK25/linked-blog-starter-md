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
	- If no **chunk** of size XB exists (even if the total free space exists), then the process can't run
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
- compile with Position Independent Code (PIC)
	- Limited in size (think 3MB Program in 4MB of memory, cannot use any starting address in the "upper" 3MB of mem)
- Use **Virtual Memory**
	- "every prog starts at 0 and you can use absolute addressing"
- Symbol Translation Table
	- think CS 365 Compiler symbol table!
	- binding at loading time

Address binding can happen at:
1. Compile time
2. Load time
3. Execution time

![[Screenshot 2025-04-09 at 7.05.52 PM.png]]


Memory Management Unit (MMU)

Dynamic Linking
- **static linking**: system libraries and program code combined by the loader into the binary program image
- DL postpones linking until execution time
- uses a **stub**, a small piece of code, to locate the appropriate memory address of the library routine
	- stub handles API of the library
- **good for deduplication of instances of a given library**
	- ex: all running processes can call 1 cryptography library instead of each running their own instance of the binary
- aka **shared libraries**
- .so extension

### Schematic View of Swapping
- Older practice
	- dropped in favor of swapping pages instead of whole processes
		- more modular and can be less costly
- Swap out a whole process to disk to free up memory, then allow it to return later
	- can take a really long time based on memory

## Contiguous Allocation
- Main memory must support both OS and user processes
- two **partitions**
	- resident OS, usually held in low memory
	- user processes held in high memory
	- each process contained a single contiguous section of memory

![[Drawing 2025-04-09 18.33.15.excalidraw]]

- conceivably, there is a set of inputs such that requests can be made to make a super high number of segments (ex: a bunch of requests that divide a segment in half)
	- soln: standardized sizes
		- ex: requests can be made for 1KB, 2KB, 64KB, etc.
			- PAGING

## Segmentation
- Program does not need to be all together
	- ex: stack can be separated from code can be separated from heap


**Segment table** - maps 2D physical addresses; each table has
- **base**
- **limit**
- stored on PCB (if using segmentation, but most use paging nowadays)

**Segment-table base register (STBR)** points to the segment table's location in memory

**Segment-table length register (STLR)** indicates number of segments used by a program

![[Screenshot 2025-04-09 at 7.59.38 PM.png]]

- NOT SHOWN: validation bit in segment table to indicate whether the segment is currently in memory
## Paging

- **Physical memory** referred to as a **frame**
- **Logical memory** referred to as a **page**

![[Screenshot 2025-04-09 at 8.04.28 PM.png]]

_tradeoff of page table size and page size_
- Mem Size = Page size \* table size

**Page-table base register** (PTBR) points to the page table  
**Page-table length register** (PTLR) indicates size of the page
Hardware traps generated to prevent accessing pages allocated to other processes

2 Accesses to Memory for each lookup
- one to page table to figure out where to look
- one to actual frame

**Table Lookaside Buffer (TLB)**
- Hardware cache; *Very fast*
- caches that maps page number to frame number
- first lookup takes 2 lookups as usual, but then can access cache after
- TLB Hit = Cache Hit = found page number and can immediately go to 
- As limit of *n* accesses --> infinity, the affect becomes stronger (closer to cache access time)
	- 1 initial cache miss then 99999 cache hits
	- EXAM QUESTION

Valid/Invalid Bit
- OS checks to see if access to a specific page is valid
	- ex: proc doesnt own page: --> page fault and kill proc
	- ex: page invalid (not loaded in phys mem) --> load page and restarts proc

Shared Pages
- multiple procs pointing to same frame

Two-level paging example
- think B+ tree
	- inverse tradeoff though
	- save mem space, cost is increased lookup due to multiple page lookups
		- TLB hits only guarantee the first level, and might miss on the second level --> need to access
		- still cached though
- used to save memory on the size of the page table
- EXAM QUESTION