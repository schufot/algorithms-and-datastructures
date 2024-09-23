# Kruskal

- Input: graph G
- Output: tree
- Pseudocode:
```
Kruskal(G)
A = ∅
sort edges after weight
for each (u,v) element of E sorted by ascending weight do
  if u and v are not in the same correlation component in Graph H=(V,A) then
  A = AU{(u,v)}
return A
```
