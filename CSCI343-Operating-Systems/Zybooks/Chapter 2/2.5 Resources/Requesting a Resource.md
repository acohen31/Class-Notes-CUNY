- resource r is **ALLOCATED** to a process p if p has **ACCESS TO IT AND IS ABLE TO UTILIZE IT**
- resource r is **FREE** if r can be allocated to requesting process
- Scenarios when p invokes request():
	1. r is free
		1. state of r = **FREE to ALLOCATED** 
		2. pointer to r put in other_resources of p
	2. r is not free
		1. p is **blocked**
		2. p's PCB moved from RL to waiting_list of r
		3. scheduler() is called
# Request Function
![[Pasted image 20240312173015.png]]