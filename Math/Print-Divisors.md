# [Print Divisors]()

Print all the divisors of a given number `n`  

eg:  
`input: n = 36`  
`output: 1 2 3 4 6 9 12 18 36`

## Approach 1 - check square-root(n) numbers

- optimal approach

- if `n = 36` , check numbers from `1 to 6`, ie `square-root(n)`
  ```
  36 / 1 = 36
  36 / 2 = 18
  36 / 3 = 12
  36 / 4 = 9
  36 / 6 = 6
  ```
- we can see that dividing the first 6 of divisors (half of divisors) with `n` gives the rest 6 divisors (other half of divisors)

- so if `n % number = 0` => its a divisor

- also, dividing `n // divisors` with the divisors `1, 2, 3, 4, 6` will give divisors `36, 18, 12, 9, 6`

- if statement to remove duplicates
- use list to print sorted output

```python
import math

n = int(input('enter n: '))
divisors = []

for i in range(1, int(math.sqrt(n)) + 1):
  if n%i==0:
    divisors.append(i)
    if n//i != i:
      divisors.append(n//i)
    
print(*sorted(divisors))
```
*note: import math module to use sqrt() function, else use n**0.5*