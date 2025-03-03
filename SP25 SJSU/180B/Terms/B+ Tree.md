intuition: think binary search but dividing by n each level of search instead of 2

Each leaf node has at least ⎡(d/2)⎤ values

All leaf nodes are at the same level.

**Internal nodes** are **JUST FOR DISTRIBUTION**, there is no guarantee that an exists with that key in the tree

Leaf nodes are where data is stored

in practice:
fill factor ~67%
average fanout = 133
typical capacities
- 133^4 = 312,900,700
- 133^3 = 2,352,637

![[Screenshot 2025-02-27 at 9.48.53 AM.png]]

Insertions:
- can either increase the height by 1 or get redistributed among neighbors
	- redistribution typically happens at leaf levels
	- for this class we're focusing on splits

Deletions:
- if under 50% occupancy --> violating rule --> borrow from siblings or potentially merge
	- prioritize a redistribution over a merge since its less computationally intensive

Duplicates:
- many data entries may have the same value
	- Solution 1:
		- all entries with a given key value reside on a single page
		- use overflow pages
	- Solution 2:
		- Allow dupe keys
		- modify search
		- use RID to get a unique (composite) key