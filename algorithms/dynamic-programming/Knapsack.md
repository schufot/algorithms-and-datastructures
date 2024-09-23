# Knapsack

- Input:
  - n; number of objects
  - g[1..n]: field of object sizes
  - w[1..n]: field of object values
  - G:knapsack size
- Output: Items to include in the collection so that the total weight is less than or equal to G and the total value is as large as possible
- Pseudocode:
  ```
  Knapsack(n,g,w,G)
  Opt = new array [1,..,n][0,..,G]
  for j = 0 to G do \* recursion termination
    if j<g[1] then Opt[1,j] = 0
    else Opt[1,j] = w[1]
  for i = 2 to n do
    for j = 0 to G do
      if g[i] ≤j then Opt[i,j] = max{Opt[i-1,j], w[i] + Opt[i-1,j-g[i]]}
    else Opt[i,j] = Opt[i-1,j]
  return Opt[n,G
	```
  - After calculating the table Opt of Knapsack, KnapsackSolution is called with Opt, g, w, i=n and j=G
  ```
  KnapsackSolution(Opt,g,w,i,j)
  if i=0 return ∅
  else if g[i]>j then return RucksackLösung(Opt,g,w,i-1,j)
  else if Opt[i,j]=w[i] + Opt[i-1,j-g[i]] then
    return {i}  RucksackSolution(Opt,g,w,i-1,j-g[i])
    else return RucksackSolution(Opt,g,w,i-1,j)
  ```
- Time complexity: O(nG)
- Recursion:
  - Opt(1,j)= w[1] for j≥g[1]
  - Opt(1,j)= 0 for j<g[1]
  - Opt(i,j) = max{Opt(i-1,j), w[i] + Opt(i-1,j-g[i])} if i>1 and g[i]≤j
  - Opt(i,j) = Opt(i-1,j) if i>1 and g[i]>j
