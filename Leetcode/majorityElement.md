# Majority Element

Given an array of size $n$, find the majority element. The majority element is the element that appears more than $[n/2]$ times.

### Example:
```
**Input:** [3,2,3]
**Output:** 3
```

### Solution:
using a *hashmap* to store the elements and count, when the count number is larger than $n/2$, return the number as majority element.