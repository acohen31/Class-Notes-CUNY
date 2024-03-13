# Basic states and transitions
- New process starts in READY state
- ![[Pasted image 20240312155119.png]]
- OS selects it for execution and moves to RUNNING
- ![[Pasted image 20240312155205.png]]
- OS **INTERUPTS PROCESS** the state goes back to READY
- ![[Pasted image 20240312155345.png]]
- Process requests **UNAVAILABLE RESOURCE** eg. open file or input data the process changes from RUNNING to BLOCKED
- ![[Pasted image 20240312155458.png]]
- Other process releases resource or generates the data needed by blocked process, OS moves blocked process BLOCKED to READY
# Advanced Process states and transitions
## New States
- Newly created process placed into **NEW** state before it can compete for CPU
- **TERMINATED** state when execution can no longer continue but before PCB is deleted
- **SUSPENDED** state to stop a process even though CPU and resources are available
## New Transitions
- RUNNING or READY or BLOCKED to SUSPENDED
	- If process goes from BLOCKED to SUSPENDED, it returns to BLOCKED
	- If process goes from RUNNING/READY to SUSPENDED, it returns to READY
- RUNNING to TERMINATED when
	- Work finished
	- fatal error