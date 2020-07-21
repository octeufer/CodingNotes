# Merge Interval

Given a collection of intervals, merge all overlapping intervals.

### Example 1
`**Input:** [[1,3],[2,6],[8,10],[15,18]]
**Output:** [[1,6],[8,10],[15,18]]`

### Solution

- Connected Graph
    Traversing all the intervals and build a connected graph, merge the connected components respectively. 
- Sorted
    Sorting the intervals according to their first values. Then merge with the decision of overlapping.