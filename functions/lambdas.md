# lambdas
```python
def apply(function, argument) = function argument

# apply is just a surrogate function which does nothing but pass an argument
# into a function

def square(x Int) Int = apply {a -> a * a} x

# the previous definition of square can be simplified this way:
#
#     apply {a -> a * a} x
#     {a -> a * a} x
#     x * x
#
# where the lambda expression is the function and x is the argument

print square(7)
# 49
```
