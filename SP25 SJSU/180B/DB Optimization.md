ACID:
- Atomicity
- Consistency
	- data is reflected across all instances
- Isolation
	- 
- Durability
	- changes are persistent
		- ie: once a transaction is committed, those changes are reflected in the data


#### Building blocks of Transactions
- break in to Reads and Writes
	- use for Scheduling transactions in an efficient manner
		- can reorder to make it "feel" like it was executed serially, but actually happens in parallel (writes *cannot* be parallelized, but reads can)

![[Screenshot 2025-04-24 at 9.47.24 AM.png]]

![[Screenshot 2025-04-24 at 9.49.44 AM.png]]

![[Screenshot 2025-04-24 at 9.49.09 AM.png]]

The read value for T2 changes (read A=9 in the first, then A=10 in the second), but because the end state does not change, it's fine


The third schedule is bad bc it ends with a different state than 1 or 2


**Conflicting actions (or conflicts)** are pairs of actions from different concurrent transactions where:
- Both actions involve the same data item.
- At least one of the actions is a write operation.
- Not all of them end up in a wrong state though (see the second schedule)

