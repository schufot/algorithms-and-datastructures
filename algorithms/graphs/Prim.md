# Prim

- Input: (negative) weighted graph in adjacency list representation, start node s, SSSP with dynamic programming
- Output: shortest distance to every other node from s
- Pseudocode:
```
Prim(G, r)
Q = V
For each vertex u∈Q do key[u] = ∞
key[r] = 0, parent[r] = NIL
while Q ≠∅ do
  u = Extract-Min(Q)
  For each v∈Adj[u] do
    If v∈Q and w(u,v)<key[v] then
      key[v] = w(u,v), parent[v]=u
```
