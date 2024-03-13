# Process Creation Function
![[Pasted image 20240312171238.png]]
1. New PCB allocated
2. cput_state, memory, scheduling_info, accounting_info are filled w/ init vals from function params
3. (**ASSUMING** simple state transition diagram) process_state set to ready
4. parent of p set point to self which is the calling process and therefore parent of p
5. p inserted into self.children
6. other_resources = NULL  b/c p has no children, open files, other resources
7. p inserted into RL
8. scheduler() called to select the process to run. Depending on the prio of the parent and itself scheduler 
	1. start process p
	2. continue parent of p's process
9. when scheduler() returns the function returns the ID of the new child p to the calling process

