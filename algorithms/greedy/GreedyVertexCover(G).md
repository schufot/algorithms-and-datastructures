# GreedyVertexCover(G)

- Input:
- Output:
- Pseudocode:
```
GreedyVertexCover2(G)
C = ∅
E' = E(G)
while E' ≠ ∅ do
  Sei (u, v) beliebige Kante aus E'
  C = C ∪ {u, v}
  Entferne aus E' jede Kante, die an u oder v anliegt
return C
```
