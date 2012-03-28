#logiko -> reactive sub-language
*A reactive sub-language of the logiko programming language.*

```js
// Assignment:
number    = 40
condition = true
reactive  => number + 2

// Functions:
mult = (x, y) -> x * y

// Conditions:
number   = -44 if condition
reaction = (reactive is -42)

// Reaction:
print 'Going nuclear' if reactive is observer
print 'Indeed we are' if reactive observes number

// Arrays:
nums = [ 1, 2, 3 ]

// Objects:
nums2 = { one: 1, two: 2, three: 3 }
nums3 =
    one:   1
    two:   2
    three: 3

```
