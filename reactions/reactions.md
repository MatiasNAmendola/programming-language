# reactions
## using signals
```python
a sig Int <- signal.sensor.temperature
b Int = a + 1

# it's 25 degrees celsius
print_on a == 25, a, b
# 25, 26

# temperature rises to 26 degrees
print_on a == 26, a, b
# 26, 27
```

