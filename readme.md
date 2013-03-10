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
```

### signals


### events


### reactions
#### using signals
```python
```


#### using events
```python
```


### samples
#### by capturing
```python
```


#### by deltas
```python
```


### lists

### aliases

### custon types

### structures








signals ( "mutable" variables ):
```python
a sig int <- 1

print a
# 1 

a <- 2

print a
# 2 
```

getting a reaction:
```python
a sig int <- 1
b int = a + 1

print a, b
# 1, 2

a <- 2

print a, b
# 2, 3
```

getting no reaction:
```python
a sig int <- 1
# capture the value of a using a()
b int = a() + 1

print a, b
# 1, 2

a <- 2

print a, b
# 2, 2
```

proper signals:
```python
a sig int = input.mouse.x
b int = a + 1

# move mouse to first pixel column left
print a, b
# 1, 2

# move mouse to second pixel column from left
print a, b
# 2, 3
```

events:
```python
a evt int = input.mouse.button1
b int = a + 1

print a, b
# 0, 1

# click left mouse button
print a, b
# 1, 2
```

## keywords and symbols
### keywords
<table>
  <thead>
    <tr> <th>keyword</th> <th>usage</th> </tr>
  </thead>
  <tbody>
    <tr> <td>evt</td>  <td>define an event</td> </tr>
    <tr> <td>def</td>  <td>define a function</td> </tr>
    <tr> <td>as</td>  <td>denotes function with unnamed arguments</td> </tr>
    <tr> <td>sig</td>  <td>define a signal</td> </tr>
  </tbody>
</table>



### symbols
#### keyword aliases
<table>
    <thead>
        <tr> <th>symbols</th> <th>keyword</th> </tr>
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
