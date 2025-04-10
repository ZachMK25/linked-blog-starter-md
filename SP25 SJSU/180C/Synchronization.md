### Background
- processes can execute concurrently
	- may be interrupted at any time, partially completing execution
- concurrent access to shared data may result in data inconsistency
- maintaining data consistency requires mechanisms to ensure the orderly execution of cooperation processes

### Race Conditions

## Critical Section Problem
- guard a specific section of code that has shared data/something that would cause a race condition
- #### Every solution to this must have
	- **Mutual Exclusion**: if a given process **P**1 is executing its critical section, then no other processes can be executing in their other sections
	- **Progress**: If no process is executing in its critical section and there exist some processes that wish to enter their critical section, then the selection of the processes that will enter the critical section next cannot be postponed indefinitely
		- ex: not stopping someone from dating your ex
	- **Bounded Waiting**: A bound must exist on the number of times that other processes are allowed to enter their critical sections after a process has made a request to enter its critical section and before that request is granted
		- can't tell a process to wait forever

### Peterson's Solution
- Good algorithmic description of solving the problem
- Two processes solution _only_, not to a large number of processes
```
do {  
flag[i] = true; 

turn = j;  

while (flag[j] && turn == j){};  // waiting loop while j's turn
// NOTE THE WHILE LOOP IS A PAUSE, NOT RUNNING ANYTHING INSIDE

[critical section]

flag[i] = false;  // indicate that i is done with its turn, allows j to go

[remainder section]

} while (true);
```

#### Confirming it works: Proof by Contradiction

ASSUME NO MUTUAL EXCLUSION
conditions for pn not running: assume some set of conditions of the following
```
P0:
flag[0] = true AND flag[1] = false
OR
turn = 0
OR
turn = 0 AND flag[1] = false


P1:
flag[1] = true AND flag[0] = false
OR
turn = 1
OR
turn = 1 AND flag[0] = false
```

can these exist at the same time?

cancel out terms --> reduces to **turn = 0 for 0 to run, or turn = 1 for 1 to run**
- MUTUAL EXLCUSION!
#### Test_and_set, Atomic booleans
```
boolean test_and_set(boolean * l)
- (hardware instruction executed by CPU atomically)
- can be interrupted by Context Switch, but CPU will just restart atomic instruction from the beginning to ensure atomicity
```

```
bool l = false;

while (test_and_set(&l)){};

Crit_Section()

l = false;
```


### Mutex Locks
```Lock l;

l.lock();
Crit_Section();
l.unlock();

internals of lock behave something like test_and_set example above
```

Processes just kinda waste time checking the lock over and over...
- Solution? **Semaphores**

### Semaphores
unlike locks, they have multiple states
maintain a *count*; initialized with a *value*
`Sem s=n`

#### Spinning semaphore example

```
wait(s){

while (s==0){
l.unlock();
	yield(); //i dont have anything to do rn, can you (scheduler) run something else from the ready queue, (in hopes that signal is called to get me unstuck)

l.lock();
};

s--;
l.unlock();

}
```


- every time you wait, decrement the counter
- only stop on wait when it becomes 0

```
signal(s) {

l.lock();
s++;
l.unlock();

}
```
- increments the count to allow another process in

**binary semaphores** can only have a max count of 1
**counting semaphores** can have count > 1

### Blocking Semaphore
```
struct Sem {
	int count;
	Lock lock;
	Queue q;
}

wait (Struct Sem * s){
	s -> lock.lock();
	if (s-> count <= 0){
		// Queue this process
		s->q.push(current);
	}

}

signal (Struct Sem * s){
	s -> lock.lock();
	if (!s->q.empty()){
		PCB p = q.pop();
		ReadyQ.push(p);
	}
	s->count++;
	s->lock.unlock();
}
```

![[Buffer with Semaphore.excalidraw]]


### Deadlock
- Proc A holds Sem1, Proc B holds Sem2
	- if need Sem1 and Sem2 to run, it can't bc each proc is holding the one the other needs
	- soln: acquire semaphores in the same order for each proc

- Natively handled by Java's `synchronized` keyword