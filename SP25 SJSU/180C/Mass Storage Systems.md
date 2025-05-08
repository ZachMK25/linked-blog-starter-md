
#### HDD - **Magnetic Disk**
- **Transfer Rate** (MB/s)
- Positioning Time (random access time): seek desired sector under the disk head (rotational latency)
- **Head Crash** results from the disk head making contact with the disk surface
- Size has changed over the years
	- BIG, then 3.5, 2.5, etc.

#### Drive attached to computer via **I/O Bus**
- busses vary
	- EIDE, ATA, SATA, USB, Fibre Channel, SCSI, SAS, Firewire, NVMe
	- Host controller in computer uses bus to talk to **disk controller** built into drive or storage array

#### Sectors
- include error checking for the sector
- think "bad sectors"
- still recoverable when an error occurs
- if the whole track had EC, then if a part of the track broke, then the whole track would be unsalvageable

### HDD Performance
- transfer rate
- Trade-off: increased RPM (improved access time) --> more wear on spindle, etc
- (See slides for formula)

### SSD
- More expensive per byte than HDD
- Endurance concerns

### Magnetic Tape

## Disk Structure
- disk drives are addressed as large 1D arrays of **logical blocks**, where the logical block is the smallest unit of transfer
	- low-level formatting created **logical blocks** of physical media
- _Lowest level that OS can see disk as is a **block device**_


### Disk Attachment
- l 

### Storage Area Network (SAN)
- Attaching a storage array to a network
- multiple devices linked together by a fiber channel switch
- optimized for large packet sizes compared to LAN/WAN (MTU=1500 for most LAN/WAN)
- different from NAS (single device)
- increasing speed of LAN/WAN --> SANs became unnecessary for most usecases

### Network Attached Storage (NAS)
- different protocols
- NFS, CIFS/SMB, iSCSI

### Disk Scheduling
- given a string of input sectors
- algs?
	- FIFO/FCFS
		- slowwww
		- can end up jumping all around the disk
		- ex: start at 50 --> 200 --> 51
	- Shortest Seek-Time First (SSTF)
		- can starve a particular request if it keeps getting pushed back
	- Scan
		- The disk arm starts at one end of the disk, and moves toward the other end, servicing requests until it gets to the other end of the disk, where the head movement is reversed and servicing continues.
		- think about an elevator
			- takes direction into consideration
			- starting at floor 10 going down, wont go to 11 to pick somebody up bc that's going in the wrong direction
- ### EXAM PROBLEM
	- give # of tracks traveled with each algo
	- very similar to process scheduling


Disk Management
- **Low-level formatting**, or **physical formatting** - dividing a disk into sectors that the disk controller can read and write
- error correction code = **ECC**
- **Partition**
- **Logical formatting** or "making a file system"


**Bootstrap loader** program stored in boot blocks of boot  
partition

Page size usually a multiple of block size
- ex Page = 4KB, block = 512 B

### RAID
- attempting to solve latency and resiliency of single drives
- Parity
- degraded state occurs when errors appear on a drive
	- varying severity depending on RAID level (0 = get fucked)


### Snapshots
- view of a file system before a set of changes take place
- good for large original size, but minor changes/deltas
- *relative* to original state
	- lighter weight than a full backup
- downside?
	- need to rebuild the data if trying to recreate the data
		- must apply all snapshots sequentially to the original to get to the current state
	- can be mitigated by periodically creating a backup of original + all snapshots
		- but then lose history of changes

### Remote Backups
- Asynchronous
	- not all at once due to bandwidth limitations
	- "eventual consistency" - Amazon
- 

