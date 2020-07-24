# Next Permutation

We need to find the next lexicographic permutation of the given list of numbers than the number of formed by the given array.

### Solution

- Brute Force
    $O(N!)$

- Single pass search
    there are three situations:
    + ascending sorted. In this case, just swap the rightest two successive elements.
    + descending sorted. In this case, no larger permutation exists, just sort by ascending.
    + descending at some places. In this case, assume that $nums[i]>nums[i-1$, then swap $nums[i-1]$ with the smallest one larger than $nums[i]$ in the right places. Then sort the right ones ascending.
    + why? because on larger permutation than descending, so ascending can return to the start, so the smallest one larger than $nums[i]$ is the next permutation.