- LLs require costly dynamic memory management
- Links are distributed over the child PCBs such that each points to the **IMMEDIATE YOUNGER SIBLING** and **IMMEDIATE OLDER SIBLING**
- parent and child fields in p's PCB replaced with 4 new fields

| PCB Field       | Explanation                                             |
| --------------- | ------------------------------------------------------- |
| parent          | points to p's parent                                    |
| first_child     | points to p's first child                               |
| younger_sibling | points to sibling of p created immediately following p  |
| older_silbling  | points to the sibling of p created immediately before p |
