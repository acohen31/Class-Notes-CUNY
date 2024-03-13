# The Thread Concept
- A thread is an instance of executing a portion of a program within a process without a separate PCB
 ![[Pasted image 20240312175443.png]]
![[chrome_iTi6qnAba2.gif]]
![[Pasted image 20240312175631.png]]
![[chrome_PzXBOOXN1I.gif]]
![[chrome_1GZtqqlEIl.gif]]
# Thread Control Block (TCB)

- B/c each thread within process is an independent execution, the runtime info held in PCB and execution stack must be replicated for each thread
- TCB holds a separate copy of the dynamically changing info needed for thread to execute
![[Pasted image 20240312180059.png]]
![[chrome_bT5Y3hbJvj.gif]]
![[chrome_3137odb8Uq.gif]]
![[uWfeK2J.gif]]
# User-level vs Kernel-level Threads
- Threads can be implemented by user application with thread library
	- Library maintains TCBs within the process
	- OS kernel not aware of the threads and treats process as single-threaded
- Alternative is to implement threads within the OS kernel
	- Kernel calls are used to manage the threads 
![[chrome_NC39GFqhMr.gif]]
1. When the process starts running, the saved CPU_state is copied into the CPU.
2. The CPU continues executing the code using the current program counter (pc) and stack pointer (sp). The PCB gets out of date as the process executes.
3. Using a thread library, the application can create multiple threads, each using a different pc and different sp. All threads share the code and global data.
4. The thread library switches between the threads by saving and copying the CPU_states between the TCBs and the CPU.
5. With user-level threads, all thread management occurs within the user process. The kernel is not aware of the multiple threads.
6. With kernel-level threads, the thread management is handled by the kernel using internal thread functions. The application uses kernel calls to request any action.
# Combining user-level and kernel-level threads
- Advantages of ULT over KLT
	- ULT do not require kernel cooperation so they are faster to manage
	- Applications using ULTs are portable between OSs
- Disadvantages of ULT
	- Not visible to kernel
		- When a ULT blocks the entire process blocks
	- Cannot use multiple CPUs b/c kernel sees the process as a single thread execution
![[chrome_s77yckzIVH.gif]]
1. The kernel maintains a small number of KLTs. The kernel also schedules the KLTs on the available CPUs.
2. Each process can create any number of ULTs using a thread library.
3. The programmer decides which ULTs or groups of ULTs are mapped on separate KLTs.
4. When u1 blocks, k1 blocks as well. But as long as at least one of u2, u3, or u4 is running, the process continues running in k2.
5. When u1 runs again and one of u2, u3, or u4 continues running then the process may continue in parallel on both CPUs.
 