# LongestCommonSubsequenceLength

- Input:
  - Sequence X=(x1,...,xm)
  - Sequence Y=(y1,...,yn)
- Output: Length of longest common subsequence of X and Y
- Pseudocode:
  ```
  LongestCommonSubsequenceLength(X, Y, m, n)
  L = new array [0..m][0..n]
  for i = 0 to m do L[i][0] = 0
  for j = 0 to n do L[0][ j] = 0
  for i = 1 to m do
    for j = 1 to n do
      if X[i]= Y[j] then L[i][ j] = L[i-1][ j-1] +1
      else
        if L[i-1][ j]  L[i][ j-1] then L[i][ j] = L[i-1][ j]
        else L[i][ j] = L[i][ j-1]
  return L[m][n]
  ```
- Time complexity: O(nm)
- Recursion:
  - L(i,j) = 0, if i=0 or j=0
  - L(i,j) = L(i-1,j-1) + 1, if i,j>0 and xm=yn
  - L(i,j) = max{L(i-1,j), L(i,j-1)}, if i,j > 0 and xm!=yn
