#[logiko][1] [![Alt Creative Commons License][2]][3] [![Build Status][4]][5]
*A proposal for a new logical, reactive, and functional programming language.*

##Basic Examples

###Logic
```py
inference:
    every man is mortal
    socrates is man

print inference?(socrates is mortal)
// true
```

###Functions
```py
mult(x, y) ->
    x * y

print mult(5, 4)
// 20
```

###Synergy
```py
inference:
    every man is mortal
    socrates is man

    ceilingCat is mortal

isMortal(library, x) ->
    library?(x is mortal)

isMan(library, x) ->
    library?(x is man)

print isMortal(inference, socrates)
// true
print isMan(inference, socrates)
// true

print isMortal(inference, ceilingCat)
// true
print isMan(inference, ceilingCat)
// false
```

##Propositionals
###Overview
- implies: =>
- or     : ||
- xor    : |||
- not    : !
- and    : &&
- eqv    : ===

##Predicates
###Overview
- leastone : E
- every    : A

##Conditionals
###Overview
- eq : ==
- eqv: ===
- lt : <
- gt : >
- le : <=
- ge : >=

##Assignment
###Overview
- as       : :
- is       : =
- mimics   : ->
- observes : <-


##Rules and Functions

##License
<span xmlns:dct="http://purl.org/dc/terms/" property="dct:title">logiko</span> by <a xmlns:cc="http://creativecommons.org/ns#" href="mraxil.us" property="cc:attributionName" rel="cc:attributionURL">Mr Axilus</a> is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-sa/3.0/">Creative Commons Attribution-ShareAlike 3.0 Unported License</a>.

Based on a work at <a xmlns:dct="http://purl.org/dc/terms/" href="logiko.mraxil.us" rel="dct:source">logiko.mraxil.us</a>.

[1]: logiko.mraxil.us "logiko"
[2]: http://i.creativecommons.org/l/by-sa/3.0/80x15.png
[3]: http://creativecommons.org/licenses/by-sa/3.0/
[4]: https://secure.travis-ci.org/mraxilus/logiko.png?branch=master
[5]: http://travis-ci.org/mraxilus/logiko
