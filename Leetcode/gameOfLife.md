# Game of Life

Given a *board* with $m$ by $n$ cells, each cell has initial state 1(live) or 0(dead). Each cell interacts with its **eight** neighbors using the following four rules:
    - Any live cell with fewer than two live neighbors dies, as if caused by under-population.
    - Any live cell with two or three live neighbors lives on to the next generation.
    - Any live cell with more than three live neighbors dies, as if by over-population.
    - Any dead cell with exactly three live neighbors becomes a live cell, as if by reproduction.
Write a function to compute the next state of the board given its current state, creating by applying rules simultaneously.

### Example:
```
**Input:**
[
    [0,1,0],
    [0,0,1],
    [1,1,1],
    [0,0,0]
]

**Output:**
[
    [0,0,0],
    [1,0,1],
    [0,1,1],
    [0,1,0]
]
```

### Solution:

The basic action for solving this problem is traversing each cell for all its neighbors and applying the 4 rules to decide the next state.

The challenge is that the change of state should be computed simultaneously, which means the update of each cell`s state should not influence the computation of the state of other cells.

One possible solution is to create another board and keep it invariant, so that we can update the state of the original board and compute the state for each cell. This method uses space O(M * N).

Another solution is to create pseudo for state update, such as mark 1->0 as -1 and mark 0->1 as 2. Hence $abs()$ operator will not be influenced when calculating the number of live neighbors.

### Code:
```
def gameOfLife(self, board: List[List[int]]) -> None:
        """
        Do not return anything, modify board in-place instead.
        """
        neighbors = [(1,0), (-1,0), (1,1), (1,-1), (-1,1), (-1,-1), (0,1), (0,-1)]
        
        rows = len(board)
        cols = len(board[0])
        
        for row in range(rows):
            for col in range(cols):
                live_ngbs = 0
                for ngb in neighbors:
                    r = (row + ngb[0])
                    c = (col + ngb[1])
                    if (r < rows and r>=0) and (c<cols and c>=0) and abs(board[r][c])==1:
                        live_ngbs+=1
                
                if board[row][col] == 1 and (live_ngbs<2 or live_ngbs>3):
                    board[row][col] = -1
                
                if board[row][col] == 0 and live_ngbs == 3:
                    board[row][col] = 2
                
        for row in range(rows):
            for col in range(cols):
                if board[row][col] > 0:
                    board[row][col] = 1
                else:
                    board[row][col] = 0
```