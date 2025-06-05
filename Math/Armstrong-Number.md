# [Armstrong Number]()

Check whether a given number `n` is Armstrong  
153 is an Armstrong number

153 => `(1 ** 3) + (5 ** 3) + (3 ** 3)` = 153

## Approach

- extract last digit one by one
- multiply with power 
- add to sum
- remove last digit until 0

```python
#python
n = int(input('enter n: '))

#copy
num = n
sum = 0

while num:
  #last digit
  ldigit = num % 10
  sum += ldigit**3
  num = num // 10

if n == sum:
  print(True)
else:
  print(False)
```
*note: this code is for checking 3 digit armstrong number.*