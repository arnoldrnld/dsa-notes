# Pattern-1

Print the following pattern for given `n` :-

```
4 4 4 4 4 4 4 
4 3 3 3 3 3 4 
4 3 2 2 2 3 4 
4 3 2 1 2 3 4 
4 3 2 2 2 3 4 
4 3 3 3 3 3 4 
4 4 4 4 4 4 4 
```
Here `n=4`

---

## Approach

- just assume the pattern we need to print is this :-
  ```
  0 0 0 0 0 0 0 
  0 1 1 1 1 1 0 
  0 1 2 2 2 1 0 
  0 1 2 3 2 1 0 
  0 1 2 2 2 1 0 
  0 1 1 1 1 1 0 
  0 0 0 0 0 0 0
  ``` 
  - this pattern can be obtained if each element of the result pattern is subtracted with n, `n - each element`
  - we can understand that the value of each element is the min distance (top, bottom, left , right) to its borders
- now its easy to print the result pattern with simple subtraction

### Code `python`

```python
n = int(input("Enter n: "))
size = 2*n-1
for i in range(size):
    for j in range(size):
        dist = [i,j,size-i-1,size-j-1]
        # top = i
        # left = j
        # right = size-j-1
        # bottom = size-i-1
        print(n - min(dist),end=" ")
    print()
```
---
