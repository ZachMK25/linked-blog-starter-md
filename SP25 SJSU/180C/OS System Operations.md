**Dual-mode** operation allows OS to protect itself and other system components
- **User mode** and **Kernel mode**
- **Mode bit** provided by hardware
	- provides ability to distinguish when system is running user code or kernel code
	- some instructions designated as **privileged**, only executable in kernel mode
	- system call changes mode to kernel, return from call resets it to user
- Increasingly CPUs support multi-mode operations
	- i.e. **virtual machine manager (VMM)** mode for guest **VMs**
	