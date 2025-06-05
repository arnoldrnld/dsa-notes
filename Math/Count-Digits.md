# [Count Digits]()

Count the number of digits in given `n`

## Approach 1 - log10 method

- take log10 of a number `n = 1234` => `log10(1234) = 3.0913`
- add 1 `4.0913`
- convert to integer to remove decimal part `4`

*note: log10(n) will cause math error if `n <= 0`*


```python
#python
#need math module
import math 

n = int(input('enter n: '))
print(int(math.log10(n) + 1))
```

## Approach 2 - string method

- convert the integer to string
- print its length

```python
#python
n = int(input('enter n: '))

print(len(str(n)))
```

## Approach 3  - division method

- double divide `n` to remove last digit until `n` become zero
- increment `count` each time

```python
#python
n = int(input('enter n: '))

num = n
count = 0

while num:
  num = num // 10
  count += 1
print(count)
```
