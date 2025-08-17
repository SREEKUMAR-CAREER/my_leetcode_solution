# Add Binary Strings (LeetCode Problem)
link: https://leetcode.com/problems/add-binary/solutions/7092840/0-ms-beats-10000-add-binary-strings-pyth-ghf0/

## Problem Statement
Given two binary strings `a` and `b`, return their sum as a binary string.

---

## Example
**Input:**
```
a = "11", b = "1"
```
**Output:**
```
"100"
```

---

## Approach
- Convert both binary strings to integers using `int(a, 2)` and `int(b, 2)`.  
- Use **bitwise operations** to simulate binary addition:  
  - `carry = a & b` → identifies common set bits (carry).  
  - `a ^= b` → performs addition without carry.  
  - `b = carry << 1` → shifts the carry to the correct place.  
- Repeat until there is no carry left (`b == 0`).  
- Convert the final integer `a` back into a binary string using `bin(a)[2:]`.  

---

## Code Implementation (Python)

```python
class Solution(object):
    def addBinary(self, a, b):
        # Day 2: Bit manipulation
        a = int(a, 2)  # string to integer in binary format
        b = int(b, 2)  # string to integer in binary format
        while b:
            carry = a & b  # carry
            a ^= b         # add without carry
            b = carry << 1 # shift carry
        return bin(a)[2:]
```
---
## Complexity Analysis

Time Complexity: O(n)

n = number of bits in the longer input.

Space Complexity: O(1)

Only uses constant extra space.

---
## Notes

This approach uses bit manipulation, simulating how addition works at the binary level.

Alternatively, one could use Python’s built-in integer addition after conversion, but this method demonstrates the underlying logic.
