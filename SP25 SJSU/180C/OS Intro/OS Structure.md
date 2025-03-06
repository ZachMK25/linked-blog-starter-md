
**Multiprogramming (Batch system)** needed for efficiency
- single user cannot keep CPU and IO devices busy at all times
- multiprogramming organizes jobs (code and data) so CPU always has to execute
- a subset of total jobs in system is kept in memory
- one job selected and run via **job scheduling**
- when it has to wait (for IO, for example) OS switches to another job

**Timesharing (multitasking)** is logical extension in which CPU switches jobs so frequently that users can interact with each job while it is running, creating **interactive computing**
- **Response time** should be < 1 sec
- each user has at least one program executing in memory => **process**
- if several jobs are ready to run at the same time => **CPU Scheduling**
- if processes don't fit in memory, **swapping** moves them in and out to run
- **virtual memory** allows execution of processes not completely in memory