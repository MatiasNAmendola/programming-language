#logiko -> logical sub-language
*A logical sub-language of the logiko programming language.*

```js
// Propositions:
      not     true // false
false or      true // true
false xor     true // false
false and     true // false
false implies true // true
false eqv     true // false

// Sugary Predicates:
socrates is man
every man is mortal

socrates is mortal? // true

// Predicates:
man(socrates)
A.M(man(M) eqv mortal(M))

mortal(socrates)? // true

// Predicates (Contd.):
woman(jane)
man(john)
man(david)
man(alex)

parent(david, john)
parent(alex, david)
parent(jane, david)

grandparent(X, Y) eqv
    Parent(X, P) and parent(P, Y)
```
