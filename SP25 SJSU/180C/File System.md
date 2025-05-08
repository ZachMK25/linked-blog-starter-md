
Fixed file sizes:
- not easy to extend file sizes
	- can't do it non-contiguously
- ex: movies, songs, anything WORM

Proposed Solution: use lists to link blocks of a file together
- B1 --> B2 --> ... Bn --> null
- allows it to be non-contiguous blocks
- hurts arbitrary access time
- good for stuff like logs

