# currying
```python
def add(x, y Int) Int = x + y

add_five = add 5

# the previous definition of add five is equivalent to defining this:
#
#     def add_five(y Int) Int = 5 + y
#

print add(2, 2), add_five(3)
# 4, 8
```
