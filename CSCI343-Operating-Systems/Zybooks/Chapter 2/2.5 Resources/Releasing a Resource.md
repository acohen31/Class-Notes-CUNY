# Release Function
![[Pasted image 20240312173605.png]]
- If r's waiting_list contains no processes then the state of r is changed to free and p continues executing.
- If the waiting list of r is not empty then the process q at the head of the list is allocated r, the state of q is changed to ready, and q is moved from the waiting_list to RL. Since a new process (q) is now on RL, the scheduler must be called to decide which process (p or q) should continue to run.