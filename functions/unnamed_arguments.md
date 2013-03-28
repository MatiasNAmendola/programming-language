# unnamed arguments
## basic


## more unnamed arguments
```python
def add(Int, Int) as
  0, 0 = 0
  x, 0 = x
  0, y = y
  x, y = add x + 1, y - 1

print add(0, 0), add(0, 1), add(1, 0), add(1, 1)
# 0, 1, 1, 2
```

## catch all
```python
def contains_zero(Int, Int) as
  0, 0 = True
  # underscore means ignore argument
  _, 0 = True
  0, _ = True
  _, _ = False

print contains_zero(0, 0), contains_zero(0, 1), contains_zero(1, 0), contains_zero(1, 1)
# True, True, True, False
```
