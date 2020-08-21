# Diameter of Binary Tree

Given a binary tree, compute the longest path between any two nodes.

### Example:
Given a binary tree:
```
            1
           / \
          2   3
         / \
        4   5
```
The longest path is [4,2,1,3] or [5,2,1,3], return diameter 3.

### Solution:
Traversing each node in the tree with depth first search. Time complexity O(N).

### Code:
```
def diameterOfBinaryTree(self, root: TreeNode) -> int:
        self.max = 1
        def traverse(root):
            if root == None:
                return 0
            L = traverse(root.left)
            R = traverse(root.right)
            self.max = max(self.max, L + R + 1)
            return max(L, R) + 1
        
        traverse(root)
        return self.max - 1
```