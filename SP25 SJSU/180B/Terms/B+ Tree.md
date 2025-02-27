intuition: think binary search but dividing by n each level of search instead of 2

Each leaf node has at least ⎡(d/2)⎤ values

All leaf nodes are at the same level.


in practice:
fill factor ~67%
average fanout = 133
typical capacities
- 133^4 = 312,900,700
- 133^3 = 2,352,637

![[Screenshot 2025-02-27 at 9.48.53 AM.png]]