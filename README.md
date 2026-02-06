# PlankLang grammar

Plank (or PlankLang) is a new programming language to perform easily math expressions.
It aims to be simple, straightforward, readable, intuitive and modular.

## Example

This is a simple Plank script.
```plank
# define a variable
let x = 2

# function with two args
let f: x, y -> x^y

# recursive fibonacci
let fib: x
| when x = 0 -> 0
| when x = 1 -> 1
| when x > 1 -> fib(x-1) + fib(x-2)

# display the results
1+x # prints 3
f(x,x) # prints 4
fib(3) # prints 2
```

You can oneline easily this script.
Plank uses `;;` to separe two instructions.
```plank
let x = 2;; 1+2
```
is equivalent to
```plank
let x = 2
1+2
```
You can also oneline functions!
```plank
let fib: x | when x = 0 -> 0 | when x = 1 -> 1 | when x > 0 -> fib(x-1) + fib(x-2)
```

## Specification

We are currently working on this.

The EBNF file describing the grammar is available [here](https://github.com/planklang/grammar/blob/main/grammar.ebnf).

## Learn

We are currently working on this.
