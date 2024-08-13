# InsertionSort

- Input: Field A with n numbers
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
- Time complexity: (3n²+7n-8)/2 ∈ O(n²)
- Proof of loop invariant:
  - Summarize the body of the for loop: Insert A[i] into the sorted subarray A[1..i-1]
	- for loop fulfills the following invariant: Subarray A[1..i-1] is sorted in ascending order
	- Induction start (i=2): Subarray A[1..i-1]=A[1..1] contains only one number and is therefore sorted
	- Induction assumption: Invariant applies to i≤n
	- Induction conclusion: According to the induction assumption, the subarray A[1..i-1] is sorted
	- Line 2 of the algorithm inserts A[i] at the correct position in the sorted subarray. This means that A[1..i] is sorted after insertion and the invariant applies to i+1
- Proof of correctness:
    - for loop ends when i has the value n+1
	  - According to the proof of the loop invariant, the loop invariant applies that A[1..i-1]=A[1..n] is sorted in ascending order
	  - Therefore, at the end of the algorithm, the field is sorted in ascending order
