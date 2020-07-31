# Move Zeroes

Given an array *nums*, write a function to move all $0$s to the end of it while maintaining the relative order of the non-zero elements.

### Example:
```
**Input:** [0,1,0,3,12]
**Output:** [1,3,12,0,0]
```

### Solution 1:

Maintaining two arrays and merge them later:

### Code:
```
N = len(nums)
        nums1 = []
        nums2 = []
        for i in range(N):
            if nums[i] == 0:
                nums2.append(0)
            else:
                nums1.append(nums[i])
        n1 = len(nums1)
        nums[:n1] = nums1
        nums[n1:] = nums2
```

### Solution 2:

Two pointers, one for last non-zero element, and one for traversing the array.
Only C++ implementation.