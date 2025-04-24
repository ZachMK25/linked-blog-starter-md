
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
- still recoverable when an error occurrs
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
- 