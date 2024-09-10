# BinarySearch

- Input: Field A with length r (sorted in ascending order), p=1, x: number searched for
- Output: Index of x
- Pseudocode:
  ```
	BinarySearch(A, x, p, r)
	​if p=r then return p
  else
    q=⌊(p+r)/2⌋
    if x≤A[q] then return BinarySearch(A, x, p, q)
    else return BinarySearch(A, x, q+1, r)
	```
- Time complexity: O(logn)
- Proof of time complexity: BinarySearch(A, x, p, r) has a runtime of O(logn), where n=r-p+1 is the size of the area to be searched
  - We assume that n is a power of two
  - The recursion equation for the runtime of BinarySearch is: T(n)≤T(n/2) + c and T(1) =c
  - We show that T(n) ≤ 2c log n for n≥2
  - Induction start (n=2): The running time of BinarySearch for n=2 is T(n) = T(2) ≤ T(1) + c = c + c = 2c = 2c log 2
  - Induction assumption: For any power of two m with 2 ≤ m < n, it applies that T(m) ≤ 2c log m
  - Induction conclusion:
	  - Due to the induction assumption, the following applies: T(n) ≤ T(n/2) + c ≤ 2c log(n/2) +c = 2c (log n -1)+c ≤ 2c log n
	  - According to the induction principle, T(n) ≤ 2c log n = O(log n) therefore follows
 - Proof of correctness: BinarySearch(A, x, p, r) finds the index of a number x in a sorted field A[p..r], provided that x is present in A[p..r].
    - We show the correctness by induction over n=r-p+1. We assume that x is in A[p..r], since there is nothing else to show.
    - Induction start: For n=1, i.e. p=r, the algorithm returns p. This is the correct (because it is the only) index.
    - Induction assumption: For all r,p with m=r-p+1 and 1≤m≤n, BinarySearch(A,x,p,r) finds the index of a number x in a sorted field A[p..r], provided x is present in the field.
    - Induction conclusion: We consider the call of BinarySearch for any p, r with n+1 = r-p+1>1.
      - Since n+1>1, p<r follows and the algorithm executes the else case. There, q is set to ⌋(p+r)/2⌊.
      - q≥p and q<r apply. If x≤A[q], BinarySearch is called recursively for A[p..q].
      - Since A[p..r] is sorted, x is in A[p..q].
      - It follows from the induction assumption that the index of x is found.
      - If x>A[q], BinarySearch is called recursively for A[q+1..r].
      - Since A[p..r] is sorted, x is in A[q+1..r].
      - It follows from the induction assumption that the index of x is found.
      - Thus, x is found in all cases and the theorem follows.
