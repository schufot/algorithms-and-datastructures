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
- Proof of time complexity: MergeSort(A, 1, n) has a runtime of O(nlogn)
	- Let n be a power of two
	- We have already shown that for a sufficiently large constant c>1, the runtime of MergeSort can be estimated by the recursion: T(n)≤2 T(n/2) + cn and T(1)=1
	- We show by induction: T(n)≤2cn log n for n≥2
	- Induction start(n=2): The running time of the algorithm for n=2 is T(n) = T(2)≤2 T(1) + 2c = 2 + 2c ≤ 4c = 2cn
	- Induction assumption: For 2≤m<n, m power of two, T(m) ≤ 2c m log m
	- Induction inclsuion:
		- Let n>2 be a power of two
		- According to the induction assumption, T(n) = 2 T(n/2) + cn ≤ 2 (2c n/2 log(n/2)) + cn = 2cn (log n -1) + cn ≤ 2c n log n
	- According to the induction principle, T(n) ≤ 2cnlog n = O(n log n)
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
