# TwoSum, ThreeSum and KSum

## TwoSum

- HashSet
Construct a hashset to store the difference between current value and the target.

## TwoSum Sorted

To solve this problem, we need to make use of the sorted information.

- TwoPointer
Using two pointer to scan the sorted array, skip the duplicate values.

## ThreeSum

Modifying and combining twosum and twosum sorted.
Using one loop to scan the value and recalculate the target.
Reuse twosum pointer to find twosum solution.

## KSum

Recursively applying ThreeSum to TwoSum.