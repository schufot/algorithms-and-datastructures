# DepthFirstSearch

- Input: graph G, APSP
- Output:
- Pseudocode:
```
DepthFirstSearch(G)
for each vertex u element of V do color[u] = white ; p[u] = nil; time = 0
for each vertex u element of V do
  if color[u]=white then DepthFirstSearchVisit(u)
```

```
DepthFirstSearchVisit(u)
color[u] = grey
time = time +1; d[u] = time
for each v element of Adj[u] do
  if color[v] = white then p[v] = u ; DepthFirstSearchVisitt(v)
color[u] = black
time = time+1; f[u] = time
```
- Time complexity: O(|V|+|E|)
