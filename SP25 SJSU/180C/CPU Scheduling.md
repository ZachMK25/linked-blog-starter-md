
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

#### Example: FIFO Scheduling

| **Process** | **Burst Time** | **Waiting time** | **Avg Waiting Time** |
| ----------- | -------------- | ---------------- | -------------------- |
| P1          | 24             | 0                | 17                   |
| P2          | 3              | 24               |                      |
| P3          | 3              | 24+3=27          |                      |
