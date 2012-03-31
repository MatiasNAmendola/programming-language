#logiko -> logical sub-language
*A logical sub-language of the logiko programming language.*

###Propositions
```js
      not     true // false
false or      true // true
false xor     true // false
false and     true // false
false implies true // true
false eqv     true // false
```

###Predicates
```js
socrates is man
every man is mortal

socrates is mortal? // true
```

```js
man(socrates)
A.M(man(M) eqv mortal(M))

mortal(socrates)? // true
```

```js
woman(jane)
man(john)
man(david)
man(alex)

parent(david, john)
parent(alex, david)
parent(jane, david)

grandparent(X, Y) eqv
    parent(X, P) and parent(P, Y)

grandparent(jane, john)? // true
```

###Recursion
```js
woman(jane)
woman(felicia)
man(john)
man(david)
man(alex)

parent(david, john)
parent(alex, david)
parent(jane, david)
parent(felicia, jane)

ancestor(X, Y) eqv
    parent(X,Y) or (parent(X,Z) and ancestor(Z,Y))

ancestor(felicia, john)? // true
```
