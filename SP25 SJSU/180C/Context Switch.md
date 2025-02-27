1. Save registers of current process
2. flush memory context
3. set state = ready or waiting for io
4. place current process into ready queue
5. dequeue (ready queue)
6. fill register from pcb
7. set state to running