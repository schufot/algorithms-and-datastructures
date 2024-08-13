# InsertionSort

- Input: Field with n numbers
- Output: Field sorted in ascending order
- Pseudocode:
  ```
  Insertionsort(A, n)
  for i=2 to n do
    x=A[i]
    j=i-1
    while j>0 and A[j]>x do
      A[j+1]=A[j]
      j=j-1
    A[j+1]=x
  ```
- Time complexity: (3n²+7n-8)/2
