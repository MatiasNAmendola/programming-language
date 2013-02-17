#[programming language][1] ![build status][2]
*a proposal for a new functional, reactive, and logical programming language.*

## usage

### logic
```js
inference:
    every man is mortal
    socrates is man

print inference['socrates is mortal'] // true
```

### functions
```js
mult(x, y) ->
    x * y

print mult(5, 4) // 20
```

### synergy
```js
library:
    every man is mortal
    socrates is man
    kitteh is mortal

is_mortal(x) ->
    library[x + 'is mortal']

is_man(x) ->
    library[x + 'is man']

print is_mortal(socrates) // true
print is_man(socrates)    // true

print is_mortal(kitteh) // true
print is_man(kitteh)    // false
```

### syntactic sugar
using keywords:

```js
parents as
    david, john, jake is man
    jane is woman
    spark is dog

    every man is mortal, human
    every woman is mortal, human
    every dog is mortal

    parent(jake, john)
    parent(john, david)

    grandparent(X, Y) implies
        parent(X, A) and parent(A, Y)



print parents['grandparent(jake, david)'] // true
print parents['X is human']               // ['david', 'jane']
print parents['X is mortal']              // ['david', 'jane', 'spark']
print parents['leastone dog(X) is human(X)'] // true
```

using symbols:

```js
parents:
    man(david)
    man(john)
    man(jake)
    woman(jane)
    dog(spark)

    mortal(X) => man(X) || woman(X) || dog(X)
    human(X) => man(X) || woman(X)

    parent(john, david)
    parent(jake, john)

    grandparent(X, Y) =>
        parent(X, P) && parent(P, Y)

print parents['grandparent(jake, david)'] // true
print parents['human(X)']                 // ['david', 'jane']
print parents['mortal(X)']                // ['david', 'jane', 'spark']
print parents['!(E.dog(X) === human(X))'] // true
```

### reactivity

static variable assignment:

```js
a -> 5
b -> a + 1
a -> 6

print a // 6
print b // 6
```

reactive variable assignment:

```js
a -> 5
b &lt;- x + 1
a -> 6

print a // 6
print b // 7
```

### reactive vs. static
```js
library:
    david, john, dave is man
    jane is woman

    parent(john, david)
    parent(dave, john)
    parent(jane, john)

    grandparent(X, Y) implies
        parent(X, P) and parent(P, Y)

get_static_grandparents() ->
    // **query** returns a list of the unifications of each variable.
    library.query 'grandparent(X, Y)', (x, y) -> x

get_reactive_grandparents() &lt;-
    library.query 'grandparent(X, Y)', (x, y) -> x

static_grandparents   -> get_reactive_grandparents()
reactive_grandparents &lt;- get_reactive_grandparents()

print get_static_grandparents() // ['dave', 'jane']
print get_reactive_grandparents() // ['dave', 'jane']
print static_grandparents         // ['dave', 'jane']
print reactive_grandparents       // ['dave', 'jane']

// Removes any contradictions, i.e., `parent(jane, john)`.
lib.merge('jane is not parent of john')

print get_static_grandparents() // ['dave', 'jane']
print get_reactive_grandparents() // ['dave']
print static_grandparents         // ['dave', 'jane']
print reactive_grandparents       // ['dave']

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
        <tr> <td>eq</td>       <td>==</td>      </tr>
        <tr> <td>eqv</td>      <td>===</td>     </tr>
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
