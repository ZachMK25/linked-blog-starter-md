
### **Short-term scheduler**

CPU Scheduling decisions may take place when a process
1. switches from running to waiting state
2. switches from running to ready state
3. switches from waiting to ready
4. terminates
1 and 4 are **nonpreemptive**
all other scheduling is **preemptive**


Dispatcher Latency:

## Scheduling Criteria
- CPU Utilization - keep the CPU busy as possible
- Throughput - # of processes that complete their execution per time unit
- Turnaround time - amount of time to execute a particular process
- Waiting time - amount of time a process has been waiting in the ready queue
- Response time - amount of time it takes from when a request was submitted until the first response is produced, not output (for time-sharing environment)

#### FIFO/First-Come-First-Serve Scheduling

| **Process** | **Burst Time** | **Waiting time** | **Avg Waiting Time** |
| ----------- | -------------- | ---------------- | -------------------- |
| P1          | 24             | 0                | 17                   |
| P2          | 3              | 24               |                      |
| P3          | 3              | 24+3=27          |                      |
#### SJF (Shortest Job First) Scheduling
- can lead to a starvation for long jobs, as they always get "cut in line" by the shorter jobs

#### Shortest Remaining-Time First
- variant of SJF but allows for newly-added jobs to be processed optimally
- Uses remaining burst-time as metric
- can think of it as checking after every step of time t --> t+1

### Round Robin
Each process gets a small unit of CPU time (**time quantum q**),  
usually 10-100 milliseconds. After this time has elapsed, the  
process is preempted and added to the end of the ready queue.

### Priority Scheduling
- priority num associated with each process
- CPU is allocated to the process with the highest priority (smallest integer)
	- non-preemptive
	- preemptive
- SFJ is priority scheduling where priority is the inverse of predicted next CPU burst time
- Problem = **Starvation** - low priority process may never execute
- Solution = **Aging** - as time progresses, increase the priority of the process

#### Time-Quantum
- Setting a window for how long each process runs uninterrupted before reevaluating scheduling based on criteria
- Lower quantum = More context switching, but also more accurate placement of timing

### Multilevel Queue
- partitioned ready queue into two parts
	- **foreground** (interactive) - RR
	- **background** (batch) - FCFS
- 
### Multilevel Feedback Queue
- 3 Queues
	- Q0 - RR with q=8
	- Q1 - RR with q=16
	- Q2 - FCFS
		((SEE SLIDES))

#### Pthread Scheduling
- in the set of attributes passed to thread, can influence way in which they are scheduled

### Multiple Processor Scheduling
- CPU Scheduling more complex when multiple CPUs are available
- **Homogenous processors** within a multiprocessor
- **Asymmetric Multiprocessing** - only one processor accesses the system data structures, alleviating the need for data sharing
- **Symmetric Multiprocessing** - each processor is self-scheduling, all processes in common ready queue, or each has its own private queue of ready processes
	- currently, most common
- CPU Affinity
	- soft affinity
	- hard affinity
- NUMA and CPU Scheduling
	- slower access to memory that is across NUMA nodes due to physical distance (Think Thread Ripper chiplets)

#### Hardware Multithreading
- Hiding memory latency by running two threads concurrently, which keeps the CPU busy more often
	- i.e., when one HW thread needs to go to I/O, can still run CPU tasks on other threads

### Real-Time CPU Scheduling
- **Soft real-time systems** - no guarantee as to when critical real-time process will be scheduled
- **Hard real-time systems** - task must be serviced by its deadline