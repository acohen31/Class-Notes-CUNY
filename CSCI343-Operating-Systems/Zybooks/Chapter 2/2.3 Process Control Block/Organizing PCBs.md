# Organized in 2 ways
## 1. An array of structures
- PCBs are marked as free or allocated
- Doesn't need dynamic mem
- Lots of wasted mem
![[Pasted image 20240312163718.png]]
![[Pasted image 20240312163729.png]]
![[Pasted image 20240312163814.png]]


# 2. An array of pointers to dynamically allocated PCBs
- Little mem wasted
- Can be much larger
- Drawback is overhead of dynamic mem management to alloc new PCB and free mem when process terminates
![[Pasted image 20240312163742.png]]
![[Pasted image 20240312163802.png]]
![[Pasted image 20240312163829.png]]

