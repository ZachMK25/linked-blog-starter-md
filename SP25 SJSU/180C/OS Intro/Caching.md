
improve read times by temporarily storing data in a faster medium than where the data is stored

- write back
	- write to LT storage only when about to be evicted from cache (cache is full)
- write through
	- write to LT storage whenever doing a write task