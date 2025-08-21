# Happy Number Problem 
link: https://leetcode.com/problems/happy-number/solutions/7104961/0-ms-beats-10000-python3-by-sree_leetwor-6azc/

## Problem Statement  
Write an algorithm to determine if a number `n` is a **happy number**.  

A **happy number** is defined by the following process:  
- Starting with any positive integer, replace the number by the sum of the squares of its digits.  
- Repeat the process until the number equals `1` (where it will remain), or it loops endlessly in a cycle that does not include `1`.  
- Those numbers for which this process ends in `1` are happy numbers.  

---

## Example  
**Input:** `n = 19`  
**Output:** `true`  
**Explanation:**  
- 1² + 9² = 82  
- 8² + 2² = 68  
- 6² + 8² = 100  
- 1² + 0² + 0² = 1  

So `19` is a happy number.  

---

## Python Solution  

```python
class Solution:
    def isHappy(self, n: int) -> bool:
        if n == 1 or n == 7:
            return True
        elif n < 10:
            return False
        else:
            sum = 0
            while n > 0:
                temp = n % 10
                sum += temp * temp
                n = n // 10
            return self.isHappy(sum)
```

## Approach

- If the number is 1 or 7, return True (base cases for happy numbers).

- If the number is a single-digit number other than 1 or 7, return False.

- Otherwise, calculate the sum of squares of digits and recursively check.

## Complexity Analysis
- Time Complexity: O(log n) per recursion, since we repeatedly process digits.

- Space Complexity: O(log n) due to recursion depth.
