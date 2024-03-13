- The OS maintains numerous resources that processes can request and release at runtime.
- Hardware resources
	- keyboards, pointing devices, printers,...
- Software resources
	- input/output buffers, locks on database tables, messages, timers,...
# Generic RCB structure of resource r

| RCB Field            | Explanation                                                                                                                                                                                                                                                         |
| -------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| resource_description | contains description of r's properties/capabilities                                                                                                                                                                                                                 |
| state                | current state of r. If r is single-unit resource then it keeps track of whether r is currently **FREE** or **ALLOCATED** to some process. If r has multiple identical units, then state keeps track of how many units are currently free and how many are allocated |
| waiting_list         | When process p requests r but r is unavailable then p's PCB is removed from the RL and added to r's waiting_list. Process is moved back to the RL when r becomes available and is allocated to the process                                                          |
