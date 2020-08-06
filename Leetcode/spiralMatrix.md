# Spiral Matrix

Given a matrix of $m \times n$ elements, return all elements of the matrix in spiral order.

### Example:
```
**Input:**
[
    [1,2,3],
    [4,5,6],
    [7,8,9]
]
**Output:** [1,2,3,6,9,8,7,4,5]
```

### Solution:

Create two array indicating potential directions in spiral sequence. 
Traverse the matrix following the spiral sequence.

### Code:
```
def spiralOrder(self, matrix: List[List[int]]) -> List[int]:
        if not matrix: return []
        M = len(matrix)
        N = len(matrix[0])
        dm = [0,1,0,-1]
        dn = [1,0,-1,0]
        mark = [[False]*N for _ in matrix]
        output = []
        m = 0 
        n = 0
        di = 0
        
        for _ in range(M*N):
            output.append(matrix[m][n])
            mark[m][n] = True
            curm = m + dm[di]
            curn = n + dn[di]
            if 0 <= curm < M and 0 <= curn < N and not mark[curm][curn]:
                m = curm
                n = curn
            else:
                di = (di+1)%4
                m = m + dm[di]
                n = n + dn[di]
            
        return output
```