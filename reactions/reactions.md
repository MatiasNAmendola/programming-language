# reactivity
## signals
```python
a sig(Int) = signal.sensor.temperature
b Int      = a + 1

# setup signal handlers
print_when (a is 25), a, b
print_when (a is 26), a, b

# temperature changes to 25 degrees celsius
# 25, 26

# temperature rises to 26 degrees
# 26, 27
```

