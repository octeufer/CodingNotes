# Longest Substring Without Repeating Characters

Given a string, find the length of the longest substring without repeating characters.

## Example:
```
**Input:** "abcabcbb"
**Output:** 3
```

## Solution:
Maintaining variable for longest length, and substring to check the length.

## Code:
```
 def lengthOfLongestSubstring(self, s: str) -> int:
        maxsub = 0
        N = len(s)
        liststr = list(s)
        temp = []
        for i in range(N):
            temp.append(liststr[i])
            for j in range(i+1, N):
                if liststr[j] not in temp:
                    temp.append(liststr[j])
                else:
                    n = len(temp)
                    if n > maxsub:
                        maxsub = n
                    temp = []
                    break
            n = len(temp)
            if n > maxsub:
                maxsub = n
            temp = []
        return maxsub
```