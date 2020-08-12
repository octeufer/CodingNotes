# Search in Rotated Sorted Array

Given an array sorted in ascending order is rotated at some pivot unknown beforehand. Search the position of a target and return its index. If can`t find, return -1.

### Example:
```
**Input:** nums = [4,5,6,7,0,1,2], target = 0.
**Output:** 4
```

### Solution:
Binary search with two pointers. This problem can be considered regarding to two comparisons:
- the comparison between 'mid' element and the target.
- the comparison between target and two pointers.

### Code:
```
def search(self, nums: List[int], target: int) -> int:
        n = len(nums)
        l = 0
        r = n-1
        while l <= r:
            mid = nums[l + (r-l)//2]
            if target == mid:
                return l + (r-l)//2
            elif mid < nums[l]:
                if target > mid and target <= nums[r]:
                    l = l + (r-l)//2 + 1
                else:
                    r = l + (r-l)//2 - 1
            else:
                if target >= nums[l] and target < mid:
                    r = l + (r-l)//2 - 1
                else:
                    l = l + (r-l)//2 + 1
        return -1
```
