# GreedyLoadBalancing

- Input: number of jobs n, array T where T[i] is the processing time of job i, number of machines m
- Output: assignment of jobs to machines such that the makespan (maximum load of any machine) is minimized
- Pseudocode:
```
GreedyLoadBalancing(T, n, m)
Initialize an array Load[1..m] = {0, 0, ..., 0}
Initialize assignment array Assign[1..n]
for i = 1 to n do
  Let j = index of machine with minimum Load[j]
  Assign[i] = j
  Load[j] = Load[j] + T[i]
return Assign
```
- Time complexity: O(n log m) (using a priority queue to find the least loaded machine)
