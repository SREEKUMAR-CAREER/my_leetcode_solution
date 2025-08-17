# Remove Element from List (LeetCode Problem)
 link: https://leetcode.com/problems/remove-element/solutions/7092813/0-ms-beats-10000-simple-brute-force-appr-knas/

## Problem Statement
Given an integer array `nums` and an integer `val`, remove all occurrences of `val` in `nums` in-place.  
The relative order of the elements may be changed.  

Return the number of elements in `nums` which are not equal to `val`.  

---

## Example
**Input:**
```
nums = [3,2,2,3], val = 3
```
**Output:**
```
2
nums = [2,2]
```

---

## Approach
- Use a `while` loop to repeatedly check if `val` is present in `nums`.  
- If found, remove it using `nums.remove(val)`.  
- Continue until all occurrences of `val` are gone.  
- Finally, return the length of the modified list.  

---

## Code Implementation (Python)

```
class Solution(object):
    def removeElement(self, nums, val):
        # Day 2: Removing element from list 
        while val in nums:
            nums.remove(val)
        return len(nums)
```
---
## Complexity Analysis

Time Complexity: O(n²) in the worst case

Each remove() call takes O(n), and in the worst case, it may be called n times.

Space Complexity: O(1)

The operation is done in-place without extra space.

## Note
This is a simple brute-force approach.

More optimal two-pointer solutions exist with O(n) time complexity.
