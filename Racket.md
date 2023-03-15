## Introduction
Racket is a programming language that is very akin of Lisp. It is a functional programming language that uses lists (usually refered to as s-expressions to represent code. The syntax is very flexible, which allows for a wide range of programming styles. For example, Racket allows you to define your own syntax using macros.

## Supported paradigms
Whilst mainly functional Racket is a multi-paradigm programming language, supporting functional, imperative, and object-oriented programming styles. Supporting first-class functions, higher-order functions, closures, and lazy evaluation. Racket is dynamically typed, which allows for more flexibility and rapid development.

Functional Example:
```rkt
(define (map-square lst)
  (map (lambda (x) (* x x)) lst))

(map-square '(1 2 3 4 5)) ; Returns (1 4 9 16 25)
```

Object Oriented Example: 
```rkt
(define person%
  (class object%
    (init name age)
    (define/public (get-name)
      name)
    (define/public (get-age)
      age)))

(define john (new person% 'John 30))

(send john get-name) ; Returns 'John
(send john get-age) ; Returns 30
```

Macro example:
```rkt
(define-syntax double
  (syntax-rules ()
    ((_ x) (* 2 x))))

(double 5) ; Returns 10
```

## Data Structures and Uses
Racket comes with a rich set of built-in data structures, including lists, vectors, hash tables, and sets. In addition, Racket has a large library of modules that provide additional data structures and functionality. The Racket standard library includes modules for working with files, network programming, regular expressions, and more. The most basic structure in Racket is the list
```rkt
#lang racket
; Creating a list:
(define lst '(1 2 3 4))

; Accessing the elements of a list:
(first lst) ; Returns 1
(second lst) ; Returns 2
(rest lst) ; Returns '(2 3 4)

; Adding an element to the front of a list:
(cons 0 lst) ; Returns '(0 1 2 3 4)

; Adding an element to the end of a list:
(append lst '(5)) ; Returns '(1 2 3 4 5)

; Mapping a function over a list:
(map add1 lst) ; Returns '(2 3 4 5)
```
But the language offers a few more depending on need 
![image](https://user-images.githubusercontent.com/55760411/225259740-f7e2a6fe-0256-401f-b5c6-2b82a3a01871.png)

Much like other languages Racket has primitives which are very common. Boolean, Number, String, Char and Symbol.
Symbols as defined by the Racket Docs has this to say. "A symbol is an atomic value that prints like an identifier preceded with '. An expression that starts with ' and continues with an identifier produces a symbol value." For the most part Symbols act like immutable Strings which is not much different to the usual. But they're different.

## Syntax
To define *anything* in racket you generally start with the following:
```rkt
#lang racket
(define pair (cons 1 2))
```
Following the pattern of (define [name] [value]) where name can be anything that isn't already defined in the language chosen and imports.
Whilst [value] can be just about anything legal in Racket. Value, Function, Object. You can syntactically make it work? There's a decent chance you can do it.
Racket is naturally recursive as it's building blocks stemming from Lisp allow for elegant deconstruction of problems, but does support iterative looping if need be.
Interestingly the language allows non letter characters in [name]s an example being the String to Number conversion.
```rkt
(string->number "123") ; Returns 123
```
Common signaling in racket denote transformative functions and procedures with an arrow from type a->b as a simple way to explain functionality. Similarly question marks are used to signal a boolean test. Such as number? which returns true if the input is a number.

## Under the hood
Racket has the ability to be interpreted or compiled. The interpreter is called "DrRacket" and provides a REPL (Read-Eval-Print Loop) for interactively testing and debugging code. Racket can also be compiled to native code using the "raco" command-line tool. Racket manages memory using garbage collection, which allows devs to focus on the logic over other things.

Alternatively Racket can interface with C code using the "ffi" module, which allows for calling C functions and accessing C data structures.
These options allow Racket developers to either work on a responsive stand alone application or compile down for export if need be. Furthermore by having access to C-Libraries the language has the elegance of recursive functional programming whilst retaining the ability to call highly efficient code that the language may be suited less for.

## Comments
All in all, Racket is an interesting language that I enjoy reading about but dislike writing. As a fan of Object Oriented Imperative programming, having to sit down and arduously disassemble tasks into their parts usually recursively easily makes my head spin. The language also prefers immutability by default which I dislike for my own ease of use. Whilst a great tool for things like writing compilers and such I would rather still use something like Rust as it offers similar perks whilst being better in many other ways.
