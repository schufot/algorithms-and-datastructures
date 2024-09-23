# BellmanFord

- Input: (negative) weighted graph in adjacency list representation, start node s, SSSP with dynamic programming
- Output: shortest distance to every other node from s
- Pseudocode:
```
BellmanFord(G, s)
d = new array [1..|V|]
for each v element of V do d[v]=∞
d[s]=0
for i=1 to |V|-1 do
  for each vV do
    for each (u,v)In[v] do
      if d[u]+w(u,v)<d[v] then d[v]=d[u]+w(u,v)
return d
```
- Time complexity: O(|V|²+|V|*|E|)
