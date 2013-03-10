#[programming language][1] ![build status][2]
*a proposal for a new programming language.*

## usage
### variables
#### basics:
```python
a = 1
b = true
c = "hello world"

print a, b, c
# 1, true, "hello world"
```

#### explicit types:
```python
a Float = 1
b Int = 1.5

print a, b
# 1.0, 1
```

### functions
#### basics
```python
# variables have been functions all along
def a() Int = 2

def square(x Int) Int =
  x * x

print square(a), square(4)
# 4, 16
```

#### currying
```python
def add(x, y Int) Int = x + y

def add_five = add 5

print add(2, 2), add_five(3)
# 4, 8
```

#### lamdas
```python
def add(a Int) = ((x Int) = a + x)

def add_five = add 5

print add_five(3)
# 8
```

#### unamed arguments
```python
def contains_zero((Int, Int)) as
  0, 0 = True
  # underscore means ignore argument
  _, 0 = True
  0, _ = True
  _, _ = False

print contains_zero((0, 0)), contains_zero((0, 1)), contains_zero((1, 0)), contains_zero((1, 1))
# True, True, True, False
```


### lists


### signals
#### basic
```python
a sig Int = signal.mouse.x

# move mouse to first pixel column from the left on screen
print a
# 1

# move mouse to second pixel column from the left on screen
print a
# 2
```

#### user defined
```python
a sig Int <- [1, 2, 3]

# a signal holds it's most recent value
print a, a, a, a
# 1, 2, 3, 3

# [1..] means a list containing values from 1 to infinity
b sig Int <- [1..]

print b, b, b #, b, ...
# 1, 2, 3 #, 4, ...
```

### events
#### basic
```python
a evt Int = event.mouse.button1

print_on a
# 0
# click left mouse button once
# 1
```


### reactions
#### using signals
```python
a sig Int <- signal.sensor.temperature
b Int = a + 1

# it's 25 degress celcius
print a, b
# 25, 26

# temperature rises to 26 degress
print a, b
# 26, 27
```


#### using events
```python
```


### sampling
#### by capturing
```python
a sig Int <- sig.sensor.temperature
# just like our reactive example but note the invocation of a
b Int = a() + 1

# it's 25 degress celcius
print a, b
# 25, 26

# temperature rises to 26 degress
print a, b
# 26, 26
# notice how the value of b isn't reactive
```


### aliases


### custon types


### structures


## keywords and symbols
### keywords
<table>
  <thead>
    <tr> <th>keyword</th> <th>usage</th> </tr>
  </thead>
  <tbody>
    <tr> <td>evt a</td> <td>define an event of type a</td>               </tr>
    <tr> <td>def</td>   <td>define a function</td>                       </tr>
    <tr> <td>as</td>    <td>denotes function with unnamed arguments</td> </tr>
    <tr> <td>sig a</td> <td>define a signal of type a</td>               </tr>
  </tbody>
</table>



### symbols
#### keyword aliases
<table>
    <thead>
        <tr> <th>symbol</th> <th>keyword</th> </tr>
    </thead>
    <tbody>
        <tr> <td>==</td>   <td>eqv</td>      </tr>
        <tr> <td>===</td>  <td>eq</td>     </tr>
        <tr> <td>&lt;</td> <td>lt</td>    </tr>
        <tr> <td>&gt;</td> <td>gt</td>    </tr>
        <tr> <td>&&</td>   <td>and</td>   </tr>
        <tr> <td>||</td>   <td>or</td>   </tr>
    </tbody>
</table>


#### unaliased symbols
<table>
    <thead>
        <tr> <th>symbol</th> <th>name</th> <th>usage</th> </tr>
    </thead>
    <tbody>
        <tr> <td>=</td>     <td>equals</td> <td>define a function</td>                  </tr> 
        <tr> <td>&lt;-</td> <td>pipe</td>   <td>simulate input into a signal/event</td> </tr>  
    </tbody>
</table>


#### operaters
<table>
    <thead>
        <tr> <th>symbol</th> <th>name</th> <th>usage</th> </tr>
    </thead>
    <tbody>
        <tr> <td>+</td> <td>addition</td> <td>add two values</td> </tr>   
    </tbody>
</table>

## license
copyright © mr axilus [![flattr this][3]][4]

permission is hereby granted, free of charge, to any person obtaining a copy of
this software and associated documentation files (the "software"), to deal in
the software without restriction, including without limitation the rights to
use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of
the software, and to permit persons to whom the software is furnished to do so,
subject to the following conditions:

the above copyright notice and this permission notice shall be included in all
copies or substantial portions of the software.

the software is provided "as is", without warranty of any kind, express or
implied, including but not limited to the warranties of merchantability, fitness
for a particular purpose and noninfringement. in no event shall the authors or
copyright holders be liable for any claim, damages or other liability, whether
in an action of contract, tort or otherwise, arising from, out of or in
connection with the software or the use or other dealings in the software.

[1]: mraxil.us "programming language"
[2]: https://secure.travis-ci.org/mraxilus/programming-language.png?branch=master
[3]: http://api.flattr.com/button/flattr-badge-large.png
[4]: https://flattr.com/profile/mraxilus
