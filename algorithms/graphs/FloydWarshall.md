# Floyd-Warshall

- Input: APSP, no negative cycles
- Output: distance between all nodes
- Pseudocode:
```
Floyd-Warshall(W, n)
Reserve memory for fields D(k)
D(0) = W
for k=1 to n do
  for i=1 to n do
    for j=1 to n do
      𝑑𝑖𝑗(𝑘) = min(𝑑𝑖𝑗(𝑘−1), 𝑑𝑖𝑘(𝑘−1) + 𝑑𝑘𝑗(𝑘−1))
return D(n)
```
- Time complexity: O(|V|³)
