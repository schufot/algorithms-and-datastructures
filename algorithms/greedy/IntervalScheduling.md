# IntervalScheduling

- Input: Number of intervals n, fields A and E, so that A[i] denotes the start time of the i-th interval and E[i] its end time; intervals sorted in ascending order by end time
- Ouput: Set S of intervals so that |S| is maximized under the condition that the intervals do not overlap
- Pseudocode:
  ```
  IntervalScheduling(A, E, n)
  S={1}
  j=1
  for i=2 to n do
    if A[i]  E[j] then
      S=S{i}
      j=i
  return S
  ```
- Time complexity: O(n)
