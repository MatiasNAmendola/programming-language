#[logiko][1] ![Alt Creative Commons License][2] ![Alt Build status.][3]
*A proposal for a new logical, reactive, and functional programming language.*

##Basic Examples

###Logic
    inference:
        every man is mortal
        socrates is man

    print inference?(socrates is mortal)
    // true

###Functions
    mult(x, y) ->
        x * y

    print mult(5, 4)
    // 20


###Synergy
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

[1]: logiko.mraxil.us "logiko"
[2]: http://i.creativecommons.org/l/by-sa/3.0/80x15.png
