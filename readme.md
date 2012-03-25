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
inference:
    every man is mortal
    socrates is man
    ceilingCat is mortal

isMortal(library, x) ->
    library['x is mortal']

isMan(library, x) ->
    library['x is man']

print isMortal(inference, socrates) // true
print isMan(inference, socrates)    // true

print isMortal(inference, ceilingCat) // true
print isMan(inference, ceilingCat)    // false
```

###Syntactic Sugar
Using keywords:

```js
inference as
    david is man
    every man is mortal

    john is parent of david
    jake is parent of john

    X is grandparent of Y implies
        X is parent of A and A is parent of Y

print inference['jake is grandparent of david'] // true
```

Using symbols:

```js
inference:
    man(david)
    mortal(X) =>
        man(X)

    parent(john, david)
    parent(jake, john)

    grandparent(X, Y) =>
        parent(X, P) && parent(P, Y)

print inference['grandparent(jake, david)'] // true
```

###Reactivity
```js
a -> 5
b -> a + 1

a -> 6
print a // 6
print b // 6

x -> 5
y <- x + 1

x -> 6

print x // 6
print y // 7
```

##Propositionals
###Overview
<table>
    <thead>
        <tr> <th>Keywords</th> <th>Symbols</th> </tr>
    </thead>
    <tbody>
        <tr> <td>implies</td>  <td>=></td>      </tr>
        <tr> <td>or</td>       <td>||</td>      </tr>
        <tr> <td>xor</td>      <td>|||</td>     </tr>
        <tr> <td>not</td>      <td>!</td>       </tr>
        <tr> <td>and</td>      <td>&&</td>      </tr>
        <tr> <td>eqv</td>      <td>===</td>     </tr>
    </tbody>
</table>

##Predicates
###Overview
<table>
    <thead>
        <tr> <th>Keywords</th>     <th>Symbols</th> </tr>
    </thead>
    <tbody>
        <tr> <td>leastone</td>  <td>E</td>      </tr>
        <tr> <td>every</td>     <td>A</td>     </tr>
    </tbody>
</table>

##Conditionals
###Overview
<table>
    <thead>
        <tr> <th>Keywords</th> <th>Symbols</th> </tr>
    </thead>
    <tbody>
        <tr> <td>eq</td>    <td>==</td>      </tr>
        <tr> <td>eqv</td>   <td>===</td>     </tr>
        <tr> <td>lt</td>    <td>&lt;</td>    </tr>
        <tr> <td>gt</td>    <td>&gt;</td>    </tr>
        <tr> <td>le</td>    <td>&lt;=</td>   </tr>
        <tr> <td>ge</td>    <td>&gt;=</td>   </tr>
    </tbody>
</table>

##Assignment
###Overview
<table>
    <thead>
        <tr> <th>Keywords</th>    <th>Symbols</th> </tr>
    </thead>
    <tbody>
        <tr> <td>as</td>       <td>:</td>       </tr>
        <tr> <td>is</td>       <td>=</td>       </tr>
        <tr> <td>mimics</td>   <td>-&gt;</td>   </tr>
        <tr> <td>observes</td> <td>&lt;-</td>   </tr>
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
