# Dijkstra

- Input: weighted graph in adjacency list representation, start node s
- Output: shortest distance to every other node from s
- Pseudocode:
```
Dijkstra(G, w, s)
initialize SSSP
Q = V[G]
while Q!=∅ do
  u = ExtractMin(Q)
  for each vAdj[u] do
    if d[u] + w(u,v)< d[v] then
      d[v] = d[u] + w(u,v)
      DecreaseKey(v,d[v])
      p[v] = u
  color[u] = schwarz
```
- Time complexity: O((|V|+|E|) log |V|
