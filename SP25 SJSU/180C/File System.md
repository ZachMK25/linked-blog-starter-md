
Fixed file sizes:
- not easy to extend file sizes
	- can't do it non-contiguously
- ex: movies, songs, anything WORM

Proposed Solution: use lists to link blocks of a file together
- B1 --> B2 --> ... Bn --> null
- allows it to be non-contiguous blocks
- hurts arbitrary access time
- good for stuff like logs

1024 byte block --> 1020 byte block for file + 4 byte pointer to use for FS
- need to read full block to get pointer

Next Step: Move pointers from inside data structure to somewhere else
- array of pointers
- for B1, B2, B3:

| index   | 0   | 1   | 2   | 3     | 4   | 5   |
| ------- | --- | --- | --- | ----- | --- | --- |
| pointer |     | 2   | 3   | * EOF |     |     |

- FILE ALLOCATION TABLE
- very easy to traverse array to find the last block
- FAT32!!!!
- Issue:
	- block goes bad --> you're screwed
	- can make a copy of the FAT
		- synchronization issues if crashes in middle of updating tables
	- INSTEAD DISTRIBUTE THE PIECES
		- that way only a few files are lost instead of everything


Use fixed number of Direct Pointer
- points directly to block

If you need more than `n` pointers, use an indirect pointer that points to a metadata block

![[Drawing 2025-05-07 18.51.59.excalidraw]]

