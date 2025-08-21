
i-nodes: information nodes; metadata

all blocks start as free

array of bits that represent whether the block is free or not

What we need to implement a FS:
1. free list of data blocks
2. free list of inodes
3. root directory
4. file system type, version
5. file system usage: _df_


MD for file --> inode
MD for F.S. --> **superblock**

`mount -rw /dev/hd1 /`
- then reads superblock to get information about how to interpret FS, etc.

formatting a drive
- determines # of blocks and inodes
- need at least one inode for root dir
- creates segment for blocks and segment for inodes

`touch /output.txt`
- checks permissions if curr users can write to this dir
- fills out inode with filename, type, size (0), time of creation, ownership, permissions, etc.
- write filled-out inode to disk
- create a data block for `/` directory (if not created), and add the file to the directory

`echo "Gomez" > /output.txt`
- check to see if `/output.txt` exists and is writable for the user
- allocate a data block
- add `"Gomez"` into data block
- change size of `/output.txt` inode
- point index to data block

Dangling data block - doesn't have an inode pointing to it
- How to rectify?
	- check which blocks are allocated and check all blocks that inodes point to
	- can rectify if it's just 1 inode with a mismatched size and 1 dangling block
	- `fschk` does this
	- `/lost+found/`!!!
	- can change sequence of data block allocation to lessen the severity of data corruption


Hardlinks vs Softlinks
- hardlinks point to inode
- softlinks point within the fs? (ex: path)
- shared_ptr style for deallocation (only deallocate when ref count = 0)
- hard links cannot cross file systems, local to their own FS's scope
- WHY DO WE USE HARDLINKS? EXAM QUESTION