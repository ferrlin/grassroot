**Functional Programming 101**

DAML vs Haskell

    - Haskell is lazy language, while allows you to write things like head[1..], meaning "take the first element of an infinite list."
    - DAML by contrast is strict. Expressions are fully evaluated, which means it is not possible to work with infinite data structures

- DAML has a `with` syntax for records, and dot syntax for record field access, neither of which present in Haskell. But DAML supports Haskell's curly brace record notation.

- DAML has a number of Haskell compiler extensions active by default
- Daml doesn't support all features of Haskell's type system. For example, there are no exitential types or GADTs

- Actions are called Monads in Haskell.

**Functions**

Function Types in DAML - can be spotted by looking for `->` which can be read as "maps to".

**Lambdas**

_Control Flow_
Cover branching and looping, and look at a few common patterns of how to translate procedural code into functional code.

_Branching_

- If..Else
  example: implement the function boolToInt: Bool -> Int, which in typical fashion maps True to 1 and False to 0.

Here is an implementation using `case`:

```
code: Haskell
	boolToInt b = case b of
	  True -> 1
	  False -> 0
```

Better implemention using if..else

```
code: daml
	boolToInt2 b = if b
       then 1
	   else 0
```

!!If..Else statements are equivalent to a `case` statement, but are easier to read.!!

- Control Flow as Expressions
`case` statements and `if..else` really are control flow in the sense that they short circuit: