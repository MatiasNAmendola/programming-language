#[programming language][1] ![build status][2]
*a proposal for a new programming language.*

## usage
basic variables:
```python
def a int = 1
def b bool = true
def c string = "hello world"

print a, b, c
# 1, true, "hello world"
```

implicit variables:
```python
a = 1.0
b = true
c = "hello world"

print type(a), type(b), type(c)
# float, bool, string
```

mutable variables:
```python
mut a int = 1

print a
# 1 

a = 2

print a
# 2 
```

getting a reaction:
```python
mut a int = 1
def b int = a + 1

print a, b
# 1, 2

a = 2

print a, b
# 2, 3
```

getting no reaction:
```python
mut a int = 1
# capture the value of a using a()
def b int = a() + 1

print a, b
# 1, 2

a = 2

print a, b
# 2, 2
```

basic functions:
```python
def add(x, y int) int =
  return x + y

print add(2, 2)
# 4

def add_five = add(5)

print add_five 3
# 8

```

## keywords and symbols
### propositionals
<table>
    <thead>
        <tr> <th>keywords</th> <th>symbols</th>    </tr>
    </thead>
    <tbody>
        <tr> <td>implies</td>  <td>=></td>         </tr>
        <tr> <td>or</td>       <td>||</td>         </tr>
        <tr> <td>xor</td>      <td>|||</td>        </tr>
        <tr> <td>not</td>      <td>!</td>          </tr>
        <tr> <td>and</td>      <td>&amp;&amp;</td> </tr>
        <tr> <td>eqv</td>      <td>===</td>        </tr>
    </tbody>
</table>

### predicates
<table>
    <thead>
        <tr> <th>keywords</th>  <th>symbols</th>     </tr>
    </thead>
    <tbody>
        <tr> <td>is</td>        <td>f(x)</td>        </tr>
        <tr> <td>leastone</td>  <td>E.predicate</td> </tr>
        <tr> <td>every</td>     <td>A.predicate</td> </tr>
    </tbody>
</table>

### conditionals
<table>
    <thead>
        <tr> <th>keywords</th> <th>symbols</th> </tr>
    </thead>
    <tbody>
        <tr> <td>eqv</td>      <td>==</td>      </tr>
        <tr> <td>eq</td>       <td>===</td>     </tr>
        <tr> <td>lt</td>       <td>&lt;</td>    </tr>
        <tr> <td>gt</td>       <td>&gt;</td>    </tr>
        <tr> <td>le</td>       <td>&lt;=</td>   </tr>
        <tr> <td>ge</td>       <td>&gt;=</td>   </tr>
    </tbody>
</table>

### assignment
<table>
    <thead>
        <tr> <th>keywords</th> <th>symbols</th> </tr>
    </thead>
    <tbody>
        <tr> <td>as</td>       <td>:</td>       </tr>
        <tr> <td>captures</td> <td>-&gt;</td>   </tr>
        <tr> <td>observes</td> <td>&lt;-</td>   </tr>
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
