# unnamed arguments
## basic
```python
def add(Int, Int) Int as
  x, y = x + y

print add(7)
# 14
```


## pattern matching
```python
def is_one_seven(Int, Int) as
  x, 7 = "yes, the second"
  7, y = "yes, the first"
  x, y = "no, just " ++ x ++ " and " ++ y

print is_one_seven(0, 7), is_one_seven(7, 0), is_one_seven(5, 9)
# "yes, the second", "yes, the first", "no, just 5 and 9"
```


## catch all
```python
def is_one_seven(Int, Int) as
  _, 7 = True
  7, _ = True
  _, _ = False

print is_one_seven(0, 7), is_one_seven(7, 0), is_one_seven(5, 9)
# True, True, False
```
