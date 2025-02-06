After IO starts, control returns to user program only upon IO completion
- wait instruction idles the CPU until the next interrupt
- wait loop
- at most one I/O request is outstanding at a time, no simultaneous I/O processing


After I/O starts, control returns to user program without waiting for I/O completion

- **System Call**
	- request to the OS to allow user to wait for I/O completion

- **Device-status table**
	- contains entry for each I/O device indicating its type, address and state
	
- OS indexes into I/O device table to determine device status and to modify table entry to include interrupt