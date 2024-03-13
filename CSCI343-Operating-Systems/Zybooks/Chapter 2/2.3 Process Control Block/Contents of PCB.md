- PCB = instantiation of a process
- On creation OS assigns a process a unique identifier = **p**
- **p** can be:
	- pointer to the PCB
	- index into an array of PCBs

| **PCB Field**          | **Explanation**                                                                                                                                                          |
| ---------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| CPU_state              | when p is stopped, current state of CPU is saved here. when p resumes the state is copied back to the cpu                                                                |
| process_state          | Store's p's current state eg: Running, ready, blocked                                                                                                                    |
| memory                 | describes area of memory assigned to p. Simplest case is a pointer to a contiguous area of main mem. In systems w/ virtual mem it can point to hierarchy or memory pages |
| scheduling_information | Contains info used by the **scheduler** to decide when p runs. Records p's CPU time, real system time, priority, deadlines                                               |
| accounting_information | amount of CPU time or memory used                                                                                                                                        |
| open_files             | tracks files currently open by p                                                                                                                                         |
| other_resources        | keeps track of other resources p has requested and successfully acquired                                                                                                 |
| parent                 | **PARENT PROCESS** created p and identity stored here                                                                                                                    |
| children               | **CHILD PROCESS** c of p is created by p. All c's are recorded here                                                                                                      |
