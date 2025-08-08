# SubsetSum

- Explanation:
  - Should calculate the maximum partial sum in A[l..r].
  - This is either in A[l..m] or in A[m+..r], or it intersects the middle.
  - The function Left(A, l, m) should find the largest partial sum in A[l..m] that ends at m, and Right(A, m+1, r) should find the largest partial sum in A[m+1..r] that begins at m+1. The sum is the largest partial sum that intersects the middle.
- Input: Field A with length r, l=1, r: length of field A
- Output: Largest partial sum
- Pseudocode:
  ```
  Left(A, l, m)
  W=0
  max=A[m]
  for i=m downto l do
  W=W+A[i]
  if W> max then max =W
  return max
  ```
- Time complexity: O(nlogn)
