### Background
- processes can execute concurrently
	- may be interrupted at any time, partially completing execution
- concurrent access to shared data may result in data inconsistency
- maintaining data consistency requires mechanisms to ensure the orderly execution of cooperation processes

### Race Conditions

## Critical Section Problem
- guard a specific section of code that has shared data/something that would cause a race condition
- **Mutual Exclusion**: if a given process **P**1 is executing its critical section, then no other processes can be executing in their other sections
- **Progress**: If no process is executing in its critical section and there exist some processes that wish to enter their critical section, then the selection of the processes that will enter the critical section next cannot be postponed indefinitely
- **Bounded Waiting**: A bound must exist on the number of times that other processes are allowed to enter their critical sections after a process has made a request to enter its critical section and before that request is granted

### Peterson's Solution
- Good algorithmic description of solving the problem
- Two processes solution, not to a large number of processes
```
do {  
flag[i] = true; 

turn = j;  

while (flag[j] && turn == j);  // waiting loop while j's turn

[critical section]

flag[i] = false;  // indicate that i is done with its turn

[remainder section]

} while (true);
```

