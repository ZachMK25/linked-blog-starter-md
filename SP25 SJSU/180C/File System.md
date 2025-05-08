
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