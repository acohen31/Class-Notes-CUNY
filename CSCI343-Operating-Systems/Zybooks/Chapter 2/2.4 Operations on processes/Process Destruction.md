# Process Destruction Function
- called when completing all work or committing a fatal error
- frees the PCB data struct and removes any references to the PCB from the system
![[Pasted image 20240312171926.png]]
1. call destroy() on all children of p
2. remove p from
	1. RL when p is ready
	2. WL when p is blocked
3. release all memory and other resources
4. close open files 
5. deallocate PCB
6. call scheduler() to select next process to run
	1. **IMPORTANT** called outside of destroy() so that the recursive calls don't also call scheduler()