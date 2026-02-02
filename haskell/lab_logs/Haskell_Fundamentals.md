# 🛰️ Haskell Engineering Lab: Core Fundamentals  
**Status:** Documentation Phase  
**Objective:** Understanding Pure Functional Programming and Type Systems.

---

## 🧬 What is Haskell?
Haskell is a **functional** programming language.It is used for describing *functions*.unlike C,Python it is built on mathematical functionss rather than sequences of instructions.

Haskell is 
⁃**Functional** : the basic building blocks of programs are *functions*. Functions can return functions and take functions as arguments. Also, the only looping construct in Haskell is *recursion*.
⁃**Pure** : Haskell functions are pure: same inputs always give the same output — every time, no exceptions. They never print, read files, or do anything sneaky. This sounds restricting, but makes reasoning about programs easier, and allows for more optimizations by the compiler.
⁃**Lazy** :  values are only evaluated when they are needed. This makes it possible to work with infinite data structures, and also makes pure programs more efficient.
⁃**Strongly typed** - every Haskell value and expression has a type. The compiler checks the types at compile-time and guarantees that no type errors can happen at runtime.The Haskell type system is very powerful and can help you design better programs.
⁃**Type inferred** - in addition to checking the types, the compiler can deduce the types for most programs. This makes working with a strongly typed language easier. Indeed, most Haskell functions can be written completely without types. However programmers can still give functions and values type annotations to make finding type errors easier. Type annotations also make reading programs easier.
⁃**Garbage-collected** -Haskell has automatic memory management via garbage collection. This means that the programmer doesn’t need to worry about allocating or freeing memory, the language runtime handles all of it automatically.

---

## Uses of Haskell
Here are some examples of software projects that were written in Haskell.

⁃The Darcs distributed version control system.
⁃The Sigma spam-prevention tool at Facebook.
⁃The implementations of the PureScript and Elm programming languages are written in Haskell.
⁃The Pandoc tool for converting between different document formats – it’s also used to produce this course material.
⁃The PostgREST server that exposes a HTTP REST API for a PostgreSQL database.
⁃Functional consulting companies like Galois and Well-Typed have a long history of developing critical systems for clients in Haskell.

---

**Expressions and Types**
An expression has a value and a type. We write an expression and its type like this: expression :: type. 

---

⁃
⁃
⁃
⁃
