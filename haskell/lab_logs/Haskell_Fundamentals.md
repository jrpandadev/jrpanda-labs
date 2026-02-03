# 🛰️ Haskell Engineering Lab: Core Fundamentals  
**Status:** Documentation Phase  
**Objective:** Understanding Pure Functional Programming and Type Systems.

---

## 💡 What is Haskell?
Haskell is a **functional** programming language.It is used for describing *functions*.unlike C,Python it is built on mathematical functionss rather than sequences of instructions.It is a *case-sensitive* language.

**Functional Programming** :- A style of programming in which the basic method of computation is applying functions to arguments.

**Functions**
* A **function**
      * Takes one or more arguments
      * Returns a single result 

Haskell is 

* **⚙️Functional** : the basic building blocks of programs are *functions*. Functions can return functions and take functions as arguments. Also, the only looping construct in Haskell is *recursion*.
* **⚙️Pure** : Haskell functions are pure: same inputs always give the same output — every time, no exceptions. They never print, read files, or do anything sneaky. This sounds restricting, but makes reasoning about programs easier, and allows for more optimizations by the compiler.
* **💤Lazy** :  values are only evaluated when they are needed. This makes it possible to work with infinite data structures, and also makes pure programs more efficient.
* **🛡️Strongly typed** - every Haskell value and expression has a type. The compiler checks the types at compile-time and guarantees that no type errors can happen at runtime.The Haskell type system is very powerful and can help you design better programs.
* **Type inferred** - in addition to checking the types, the compiler can deduce the types for most programs. This makes working with a strongly typed language easier. Indeed, most Haskell functions can be written completely without types. However programmers can still give functions and values type annotations to make finding type errors easier. Type annotations also make reading programs easier.
* **🧠Garbage-collected** -Haskell has automatic memory management via garbage collection. This means that the programmer doesn’t need to worry about allocating or freeing memory, the language runtime handles all of it automatically.

---

## 🚀 Uses of Haskell
Here are some examples of software projects that were written in Haskell.

* The Darcs distributed version control system.
* The Sigma spam-prevention tool at Facebook.
* The implementations of the PureScript and Elm programming languages are written in Haskell.
* The Pandoc tool for converting between different document formats – it’s also used to produce this course material.
* The PostgREST server that exposes a HTTP REST API for a PostgreSQL database.
* Functional consulting companies like Galois and Well-Typed have a long history of developing critical systems for clients in Haskell.

---
## 📜 Some History
A brief timeline of Haskell:

 * 1930s: Lambda Calculus
 * 1950s-1970s: Lisp, Pattern Matching, Scheme, ML
 * 1978 John Backus: Can programming be liberated from the von Neumann style?
 * 1987 A decision was made to unify the field of pure functional languages
 * 1990 Haskell 1.0
 * 1991 Haskell 1.1 (let-syntax, sections)
 * 1992 Haskell 1.2, GHC
 * 1996 Haskell 1.3 (Monads, do-syntax, type system improvements)
 * 1999 Haskell 98
 * 2000’s: GHC development, many extensions to the language
 * 2009 The Haskell 2010 standard
 * 2010’s: GHC development, Haskell Platform, Haskell Stack

 ---

## 🧮 Expressions and Types
An expression has a value and a type. We write an expression and its type like this: expression :: type. 

**Syntax of Expressions**
Expressions consist of functions applied to arguments. Functions are applied (i.e. called) by placing the arguments after the name of the function – there is no special syntax for a function call.

**Haskell**     	**Python, Java or C**
* f 1	               f(1)
* f 1 2	               f(1,2)
* g h f 1	           g(h,f,1)
* g h (f 1)	           g(h,f(1))
* g (h f 1)	           g(h(f,1))
* g (h (f 1))	       g(h(f(1)))
* a + b	               a + b
* f a + g b	           f(a) + g(b)
* f (a + g b)	       f(a+g(b))

**Note** :- In Haskell : f g x y same as (((f g) x )y)

**Types**
* Int - (64-bit) integer
       * Bounded Range : minBound(-2^63) & maxBound(2^63-1)
       * Operations : +, -, *, div, mod
* Integer - unbounded integers
            * Operations : +, -, *, div, mod
* Float - floating point ("Real Numbers")
          * Operations : +, -, *, div, mod,sqrt
* Double - floating point ("Real Numbers")
           * Operations : +, -, *, div, mod,sqrt
* Bool - true,false
         * Operations : &&, ||, not
* char - characters: 'a','%' etc.
         * Operations :reverse, ++ 
* String - strings of characters: "abcd",etc. 
           * Operations :reverse, ++

**Syntax of Types**
Function types are written using the -> syntax:

* one argument: argumentType -> returnType
* two arguments: argument1Type -> argument2Type -> returnType
* three arguments: argument1Type -> argument2Type -> argument3Type -> returnType

**Note**
* To find type press either :type or :t in ghci
* ghci>:t 1+1
  1+1 :: Num a -> a (here a : any number type)

---

## The Structure of a Haskell Program
```haskell
module Gold where --A module consists of definitions

-- The golden ratio (comment)
phi :: Double --type
phi = (sqrt 5 + 1) / 2 --definition

polynomial :: Double -> Double --type
polynomial x = x^2 - x - 1 --definition

f x = polynomial (polynomial x) --the definition of a function called f

main = do --later
  print (polynomial phi)
  print (f phi)
  ```

**Output**
0.0
-1.0

**Note**:- the lack of type annotation
* Type f :: double -> double
* Reason : As both inner and outer function operates on double inputs and returns double. So, f maps double to double.

---

## Defining Functions
**Function Definition** 
 * A equation with a function name, argumented names, and a body.
 * Ex: double x = x + x
 * Ex: sqr :: Int -> Int
       sqr x = x * x
 * Ex: isordered :: Int -> Int -> Int -> Int -> Bool
       isordered x y z = (x <= y) && (y <= z)

**Local Definitions**
Haskell has two different ways for creating local definitions: let...in and where.

* where adds local definitions to a definition:

* Ex: circleArea :: Double -> Double
      circleArea r = pi * rsquare
          where pi = 3.1415926
                rsquare = r * r

* let...in is an expression:

* Ex: circleArea r = let pi = 3.1415926
                         rsquare = r * r
                     in pi * rsquare

* Local definitions can also be functions:

* circleArea r = pi * square r
    where pi = 3.1415926
          square x = x * x

* circleArea r = let pi = 3.1415926
                   square x = x * x
               in pi * square r

* Ex: increment x = let x = x+1
                    in x
* This is just an infinite loop, because it tries to define a new variable x with the property x = x+1. Thus when evaluating x, Haskell just keeps computing 1+1+1+1+... indefinitely.

* Ex: compute x = let a = x+1
                      a = a*2
                  in a
* error:
    Conflicting definitions for ‘a’
 
* **Remark** : local definitions can shadow the names of variables defined elsewhere. Shadowing is not a side-effect. Instead, shadowing creates a new variable within a more restricted scope that uses the same name as some variable in the outer scope.  

**XOR (Exclusive Or)**
* check that exactly one of them is true
```haskell
xor1 :: Bool -> Bool -> Bool
xor1 b1 b2 = ( b1 && ( not b2 )) || (( not b1 ) && b2 )
```
* **Conditionals** :
* if-else

```haskell
xor2 :: Bool -> Bool -> Bool
xor2 b1 b2 = if b1 == b2 then False else True
--alternative
xor3 :: Bool -> Bool -> Bool
xor3 b1 b2 = if b1 /= b2 then True else False
--simplified
xor4 :: Bool -> Bool -> Bool
xor4 b1 b2 = b1 /= b2
--alternative
xor5 :: Bool -> Bool -> Bool
xor5 b1 b2 = (/=) b1 b2
--simplified
xor6 :: Bool -> Bool -> Bool
xor6 b1 b2 = (/=)
```
* **Pattern Matching** :
A definition (of a function) can consist of multiple equations. The equations are matched in order against the arguments until a suitable one is found. This is called pattern matching.

```haskell
xor7 :: Bool -> Bool -> Bool
xor7 False False = False
xor7 False True = True
xor7 True False = True
xor7 True True = False
--simplified
xor8 :: Bool -> Bool -> Bool
xor8 False True = True
xor8 True False = True
xor8 b1 b2 = False
--alternative
xor9 :: Bool -> Bool -> Bool
xor9 False b = b
xor9 b False = b
xor9 b1 b2 = False
--alternative
xor10 :: Bool -> Bool -> Bool
xor10 False True = True
xor10 True False = True
xor10 _ _ = False --underscore'_'matches anything.
--simplified
xor11 :: Bool -> Bool -> Bool
xor11 False b = b
xor11 True b = not b
```
**Note** :- Underscore "-" 
            * don't case - argument not used in the body.
            * It scans from top to bottom, then replaces the first definition whose input pattern matches the argument.  

**Examples of Pattern matching**
* Ex. greet :: String -> String -> String
      greet "Finland" name = "Hei, " ++ name
      greet "Italy"   name = "Ciao, " ++ name
      greet "England" name = "How do you do, " ++ name
      greet _         name = "Hello, " ++ name

Ex. brokenGreet _         name = "Hello, " ++ name
    brokenGreet "Finland" name = "Hei, " ++ name

* Here the first case gets selected for all inputs.
* GHC even gives you a warning about this code:

<interactive>:1:1: warning: [-Woverlapping-patterns]
    Pattern match is redundant

* First let’s introduce the standard library function *show* that can turn (almost!) anything into a string:

* ghci> show True
  "True"
* ghci> show 3
  "3"
* Ex: describe :: Integer -> String
      describe 0 = "zero"
      describe 1 = "one"
      describe 2 = "an even prime"
      describe n = "the number " ++ show n

* **Guards** :
* The if then else is often a bit cumbersome, especially when you have multiple cases. An easier alternative is Haskell’s conditional definition or guarded definition.

* Syntax:
  f x y z
    | condition1 = something
    | condition2 = other
    | otherwise  = somethingother

```haskell
xor12 :: Bool -> Bool -> Bool
xor12 False b = b
xor12 True b
   |b == False = True
   |b == True = False
--Alternative
xor13 :: Bool -> Bool -> Bool
xor13 False b = b
xor13 True b
   |b == False = True
   |b == True = False

xor14 :: Bool -> Bool -> Bool
xor14 b1 b2
   |b1 == False = not b2
   |b == False = b1
--error : Excption:Non exhaustive pattern in function xor
xor15 :: Bool -> Bool -> Bool
xor15 b1 b2
   |b1 == True = not b2
   |otherwise = b2

--Nested: like switch in c 
xor16 :: Bool -> Bool -> Bool
xor16 b1 b2 + case b1 of
   False -> b2
   True -> not b2

xor117 :: Bool -> Bool -> Bool
xor17 b1 b2 + case b1 of
   False -> case b2 of
      False -> False
      True ->  True
   True -> not b2
--Alternative
xor17 :: Bool -> Bool -> Bool
xor17 b1 b2 + case b1 of
   | b1 == b2 = False
   | b1 /= b2 = True
```

⁃
⁃
⁃
