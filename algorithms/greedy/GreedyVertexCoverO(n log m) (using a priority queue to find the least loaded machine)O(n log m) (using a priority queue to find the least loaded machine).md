# GreedyVertexCover

- Input: graph G
- Output: Vertex cover set C such that every edge in E is incident to at least one vertex in C
- Pseudocode:
```
GreedyVertexCover(G)
C = {}
while E is not empty do
  Pick any edge (u, v) ∈ E
  C = C ∪ {u, v}
  Remove all edges incident to u or v from E
return C
```
- Time complexity: O(|E|)
