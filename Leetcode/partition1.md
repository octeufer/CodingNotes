# Array Partition I

Given an array of **2n** integers, your task is to group these integers into **n** pairs of integer, say $(a_1, b_1), \cdots, (a_n, b_n)$ which makes sum of $min(a_i, b_i)$ for all $i$ from $1$ to $n$ as large as possible.

### Example 1:

```
**Input:** [1,4,3,2]
**Output:** 4

$min(1,2) + min(3,4)$ = 4
```

### Solution:
We consider this problem as minimize the *sum loss*, which is derived by $min$ operation. Hence, we can sort the integers ascending and partition the integers successively.

### Code:
```
def arrayPairSum(self, nums: List[int]) -> int:
        nums.sort()
        output = 0
        N = len(nums)
        for i in range(0,N,2):
            output+=nums[i]
        return output
```