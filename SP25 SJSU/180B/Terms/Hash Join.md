Goal: For each relation, partition relation into **buckets** such that hB(t.A) = hB(t’.A) they are in the same bucket
- h = hash function
- B = bucket
- t = table
- A = attribute

## Phase 1: Partitioning

- apply the hash function on all keys for this page
- repeat until the buffer bucket pages are full. then flush to disk
	- NOTE: collisions can occur
		- in this case, this can be resolved by another pass/phase of hashing to separate the different keys
- unevenness in the size of buckets = **skew**
	- usually not a big problem

## Phase 2: Partition Join
- Join pairs of buckets from R and S that have the same hash value to complete the join

Given enough buffer pages:
• Hash Partition requires reading + writing each page of R,S  
• → 2(P(R)+P(S)) IOs  
• Partition Join (with BNLJ) requires reading each page of R,S  
• → P(R) + P(S) IOs