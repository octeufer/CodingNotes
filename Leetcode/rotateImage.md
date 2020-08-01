# Rotate Image

Given an $n \times n$ $2D$ matrix representing an image.
Rotate the image by 90 degrees (clockwise).

Only **in-place** rotate.

### Example 1:
```
Given **input matrix** = 
[
    [1,2,3],
    [4,5,6],
    [7,8,9]
],

rotate the input matrix **in-place** such that it becomes:
[
    [7,4,1],
    [8,5,2],
    [9,6,3]
]
```

### Solution:
Doing mirror swap two times. First swap vertically, than swap diagonally:
```
First mirror swap vertically:
[
    [3,2,1],
    [6,5,4],
    [9,8,7]
],
then mirror swap diagonally:
[
    [7,4,1],
    [8,5,2],
    [9,6,3]
]
```

### Code:
```
def rotate(self, matrix: List[List[int]]) -> None:
        """
        Do not return anything, modify matrix in-place instead.
        """
        n = len(matrix)
        
        for i in range(n):
            for j in range(n//2):
                temp = matrix[i][j]
                matrix[i][j] = matrix[i][n-j-1]
                matrix[i][n-j-1] = temp
        
        for i in range(n-1):
            for j in range(0,n-i-1):
                temp = matrix[i][j]
                matrix[i][j] = matrix[n-j-1][n-i-1]
                matrix[n-j-1][n-i-1] = temp
```


