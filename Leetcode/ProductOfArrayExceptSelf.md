# Product of Array Except Self

Given an array *nums* of *n* integers where *n>1*, return an array *output* such that *output[i]* is equal to the product of all the elements of *nums* except *nums[i]*.

### Example:
`**Input:** [1,2,3,4]
**Output:** [24,12,8,6]`

### Solution:
- With division:
```
def productExceptSelf(self, nums: List[int]) -> List[int]:
        pdall = nums[0]
        N = len(nums)
        zeros = []
        for i in range(1,N):
            if nums[i]==0:
                zeros.append(i)
                continue
            pdall*=nums[i]
        if len(zeros)>1:
            return [0 for i in range(N)]
        elif len(zeros)==1:
            output = [0 for i in range(N)]
            output[zeros[0]]=pdall
        else:
            output = []
            for i in range(N):
                output.append(pdall//nums[i])
        return output
```

- Without division:
```
        output = []
        N = len(nums)
        L = [0]*N
        L[0]=1
        for i in range(1, N):
            L[i] = L[i-1] * nums[i-1]
        R = [0]*N
        R[N-1]=1
        for i in range(N-2,-1,-1):
            R[i] = R[i+1] * nums[i+1]
        for i in range(N):
            output.append(L[i] * R[i])
        
        return output
```