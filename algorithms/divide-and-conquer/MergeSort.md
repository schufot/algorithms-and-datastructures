# MergeSort

- Input: Field A with r numbers
- Output: Field sorted in ascending order
- Pseudocode:
  ```
	MergeSort(A, p, r)
	​if p<r then // Recursion abort if p=r
		q=⌊(p+r)/2⌋ // Calculate center
		MergeSort(A, p, q) // Sort left half
		MergeSort(A, q+1, r) // Sort right hald
		Merge(A, p, q, r) // Put the parts together
	```
  ```
	Merge(A, p, q, r)
	B=new array[1..(r-p+1)]
	i=p //current position of array 1
	j=q+1 //current position of array 2
	for k=i to r-p+1 do
		if i≤q and (j>r or A[i]≤A[j]) then
			B[k]=A[i]
			i=i+1
		else
			B[k]=A[j]
			j=j+1
	A[p..r]=B[1..(r-p+1)]
	```
- Time complexity:
	- T(n) ≤ 1, if n=1
	- T(n) ≤ 2T(n/2) + cn, if n>1 (c is a sufficiently large constant)
- Proof of correctness: Algorithm MergeSort(A, p, r) sorts the field A[p..r] correctly
	- Induction via the size n of the area to be sorted (i.e. n=r-p+1)
	- Induction start (n=1):
		- The area to be sorted A[p..r] contains one element p=r
		- Range is already sorted and the algorithm does not enter the then case and ends without changing the field
	- Induction assumption: MergeSort sorts areas of size m with 1≤m<n correctly
	- Induction conclusion:
		- We consider MergeSort(A, p, r) with n=r-p+1
		- Since n>1, p<r follows and the algorithm executes the then case
		- Here q is set to ⌊(p+r)/2⌋
		- The following applies: q≥p and q<r
		- MergeSort is then called recursively in the limits p, q or q+1, r
		- According to the induction assumption, MergeSort sorts correctly in this case
		- Now the correctness follows from the fact that Merge correctly merges the two areas into a sorted field
