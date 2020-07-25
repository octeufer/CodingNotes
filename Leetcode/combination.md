# Combination

Given two integers n and k, return all possible combinations of k numbers out of 1 ... n.

### Example:
```
**Input:** n=4, k=2
**Output:**
[
    [2,4],
    [3,4],
    [2,3],
    [1,2],
    [1,3],
    [1,4],
]
```


### Solution

- Backtracking
```
 def combine(self, n: int, k: int) -> List[List[int]]:
        def comb(first=1, curr=[]):
            if len(curr) == k:
                output.append(curr[:])
            for i in range(first, n+1):
                curr.append(i)
                comb(i+1, curr)
                curr.pop()
        
        output = []
        comb()
        return output
```
- Lexicographic combinations