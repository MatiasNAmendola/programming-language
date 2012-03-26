#[logiko][1] [![Alt Creative Commons License][2]][3] [![Build Status][4]][5]
*A proposal for a new logical, reactive, and functional programming language.*

##Basic Examples

###Logic
```js
inference:
    every man is mortal
    socrates is man

print inference['socrates is mortal'] // true
```

###Functions
```js
mult(x, y) ->
    x * y

print mult(5, 4) // 20
```

###Synergy
```js
library:
    every man is mortal
    socrates is man
    kitteh is mortal

isMortal(x) ->
    library[x + 'is mortal']

isMan(x) ->
    library[x + 'is man']

print isMortal(socrates) // true
print isMan(socrates)    // true

print isMortal(kitteh) // true
print isMan(kitteh)    // false
```

###Syntactic Sugar
Using keywords:

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
print parents['X is human']                   // ['david', 'jane']
print parents['X is mortal']                  // ['david', 'jane', 'spark']
print parents['leastone dog(X) is human(X)']        // true
```

Using symbols:

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

###Reactivity

As one would expect:

```js
a -> 5
b -> a + 1
a -> 6

print a // 6
print b // 6
```

Whoah Nelly!:

```js
a -> 5
b &lt;- x + 1
a -> 6

print a // 6
print b // 7
```

###Reactive vs. Static
```js
library:
    david, john, dave is man
    jane is woman

    parent(john, david)
    parent(dave, john)
    parent(jane, john)

    grandparent(X, Y) implies
        parent(X, P) and parent(P, Y)

getStaticGrandparents() ->
    // **query** returns a list of the unifications of each variable.
    library.query 'grandparent(X, Y)', (x, y) -> x

getReactiveGrandparents() &lt;-
    library.query 'grandparent(X, Y)', (x, y) -> x

staticGrandparents   -> getReactiveGrandparents()
reactiveGrandparents &lt;- getReactiveGrandparents()

print getStaticGrandparents()   // ['dave', 'jane']
print getReactiveGrandparents() // ['dave', 'jane']
print staticGrandparents        // ['dave', 'jane']
print reactiveGrandparents      // ['dave', 'jane']

// Removes any contradictions, i.e., `parent(jane, john)`.
lib.merge('jane is not parent of john')

print getStaticGrandparents()   // ['dave', 'jane']
print getReactiveGrandparents() // ['dave']
print staticGrandparents        // ['dave', 'jane']
print reactiveGrandparents      // ['dave']

```

##Keywords and Symbols
###Propositionals
<table>
    <thead>
        <tr> <th>Keywords</th> <th>Symbols</th>    </tr>
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

###Predicates
<table>
    <thead>
        <tr> <th>Keywords</th>  <th>Symbols</th>     </tr>
    </thead>
    <tbody>
        <tr> <td>is</td>        <td>f(x)</td>        </tr>
        <tr> <td>leastone</td>  <td>E.predicate</td> </tr>
        <tr> <td>every</td>     <td>A.predicate</td> </tr>
    </tbody>
</table>

###Conditionals
<table>
    <thead>
        <tr> <th>Keywords</th> <th>Symbols</th> </tr>
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

###Assignment
<table>
    <thead>
        <tr> <th>Keywords</th>    <th>Symbols</th> </tr>
    </thead>
    <tbody>
        <tr> <td>as</td>          <td>:</td>       </tr>
        <tr> <td>mimics</td>      <td>-&gt;</td>   </tr>
        <tr> <td>observes</td>    <td>&lt;-</td>   </tr>
    </tbody>
</table>

##License
<span xmlns:dct="http://purl.org/dc/terms/" property="dct:title">logiko</span> by <a xmlns:cc="http://creativecommons.org/ns#" href="mraxil.us" property="cc:attributionName" rel="cc:attributionURL">Mr Axilus</a> is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-sa/3.0/">Creative Commons Attribution-ShareAlike 3.0 Unported License</a>.

Based on a work at <a xmlns:dct="http://purl.org/dc/terms/" href="logiko.mraxil.us" rel="dct:source">logiko.mraxil.us</a>.

[1]: logiko.mraxil.us "logiko"
[2]: http://i.creativecommons.org/l/by-sa/3.0/80x15.png
[3]: http://creativecommons.org/licenses/by-sa/3.0/
[4]: https://secure.travis-ci.org/mraxilus/logiko.png?branch=master
[5]: http://travis-ci.org/mraxilus/logiko
