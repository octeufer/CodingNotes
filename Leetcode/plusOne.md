# Plus One

Given a **non-empty** array of digits representing a non-negative integer, increment one to the integer.

### Example:
```
**Input:** [1,2,3]
**Output:** [1,2,4]
```

### Solution:
Consider the situation when $digits[i] = 9$

### Code:
```
def plusOne(self, digits: List[int]) -> List[int]:
        N = len(digits)
        for i in range(N-1, -1, -1):
            if digits[i] == 9:
                digits[i] = 0
            else:
                digits[i] = digits[i] + 1
                return digits
        if digits[0] == 0:
            digits.insert(0, 1)
        return digits
``` 