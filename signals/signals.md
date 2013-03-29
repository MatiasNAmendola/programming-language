# signals
## basic
```python
x sig(Int) = sig.mouse.x
y sig(Int) = sig.mouse.y

# setup signal handler
print_when (x is 1) and (y is 1),
           "your mouse touched the top left corner of the screen!"

# move mouse to top left corner of the screen
# "your mouse touched the top left corner of the screen!"
```
