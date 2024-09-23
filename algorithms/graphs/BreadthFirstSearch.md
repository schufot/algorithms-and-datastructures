# BreadthFirstSearch

- Input: unweighted graph in adjacency list representation, start node s
- Output: shortest distance to every other node from s
- Pseudocode:
```
BreadthFirstSearch(G,s)
  „initialize BFS“
  while Q!=∅ do
    u = head[Q]
    for each v element of Adj[u] do
      if color[v] = white then
        color[v] = grey
        d[v] = d[u]+1; p[v] = u
        enqueue(Q,v)
    dequeue(Q)
    color[u] = black
```
