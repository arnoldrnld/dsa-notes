# [Reverse Integer](https://leetcode.com/problems/reverse-integer/description/)

*leetcode : https://leetcode.com/problems/reverse-integer/description/*

## Approach 1
- initialize result
- `x % 10` gives last digit of number
- add to result
- `res * 10` move digit place (tens => hundreds =>)
- `x // 10` removes last digit
- iterate until number <= 0

---

### Code 1 `python`

```python
class Solution:
    def reverse(self, x: int) -> int:
        res = 0
        sign = -1 if x < 0 else 1
        x = abs(x)
        while x:
            res = res*10 + x%10
            x = x//10
        
        if res not in range(-2**31,2**31-1):
            return 0
        else:
            return sign * res
```
---

## Approach 2
- convert number to string
- use slicing to reverse `[::-1]`
- convert back to integer

*note* : use absolute value, then add sign

### Code 2 `python`

```python
class Solution:
    def reverse(self, x: int) -> int:
        res = 0
        sign = 1 if x > 0 else -1
        res = int(str(abs(x))[::-1]) * sign

        if res not in range(-2**31,2**31):
            return 0
        else:
            return res
```
