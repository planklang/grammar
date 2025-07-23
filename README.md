# PlankLang grammar

Plank (or PlankLang) is a new programming language describing plots.
It aims to be simple, straightforward, readable, intuitive and modular.

## Example

This is a simple Plank script.

```plank
axis x [0 10] "Label X"
axis y [-5 100] "Label Y"

plot "x -> x^2"
| color 0 0 0 1 # RGBA <- comment
| width 1

plot "exp(x)" # if the argument "x ->" is omitted, it is implicitly deduced
| color 0 0 0 1
| width 1
```

Firstly, it defines how the grid works.

`axis x [0 10] "Label X"` describes how the X axis works.
`[0 10]` is the range of the axis and `"Label X"` is its label.

`axis y [-5 100] "Label Y"` describes how the Y axis works.
`[-5 100]` is the range of the axis and `"Label Y"` is its label.

Then, it defines what populates the plot.

`plot "x -> x^2"` is the mathematical function $x\mapsto x^2$.
This will populate the plot.
`| color 0 0 0 1` sets the color of the graph (RGBA).
`| width 1` sets the width of the line.

`plot "exp(x)"` is the mathematical function $x\mapsto\exp(x)$.
This will also populate the plot.
`| color 0 0 0 1` sets the color of the graph (RGBA).
`| width 1` sets the width of the line.

Finally, the plot is rendered.

You can also write this script in one line:
`axis x [0, 10] "Label X";; axis y [-5, 100] "Label Y";; plot "x -> x^2" | color 0 0 0 1 | width 1;; plot "exp(x)" | color 0 0 0 1 | width 1`. 
Plank uses `;;` to separate two instructions.

## Specification

We are currently working on this.

The EBNF file describing the grammar is available [here](https://github.com/planklang/grammar/blob/main/grammar.ebnf).

## Learn

We are currently working on this.

### Goal

A Plank script describes only one plot.
It defines how visually it must look like.

### Types

Numbers and strings (delimited by `"`, by `'` or by \`) are supported.

PlankLang uses a special type called *identifier* that is a string without quotes and without spaces.

A tuple is a finished group of numbers, strings, identifiers, tuples or lists.
It is between an opening square brackets and a closing parenthesis (`(` and `)`).
These are optional if the tuple is not in a tuple.
Each item is separated by a space.

A list is a group of numbers, strings, identifiers, tuples or lists.
It is between an opening square brackets and a closing square brackets (`[` and `]`).
Each item is separated by a space.
Every item must have the same type.

An atom is the supertype including number, string, identifier, tuple and list.

### Statement

Each description is a statement in PlankLang.
A statement must start with a keyword.
The current list of keywords and their usage will be described in the specification.

A keyword must start a new line or be added after the statemenent delimiter (`;;`).
It can take an argument.
An argument is a tuple.

In this example
```
axis x "Label"
```
`axis` is the keyword, `x` is an identifier and `"Label"` is a string. 
The implicit tuple `(x "Label")` is the argument of `axis`.
You can also write
```
axis (x "Label")
```

### Modifiers

A modifier modifies how a keyword works.
It is always in a statement.
Each keyword has its own modifiers.
The current list of keywords with their modifiers and their usage will be described in the specification.

A modifier is always placed after a pipe (`|`).
It can take an argument.
An argument is a tuple.

A modifier always overrides previous properties.

In this example
```
axis x "Label"
| label "Label 2"
```
`|` is the pipe indicating that the next word is a modifier, `label`  is the modifier and `"Label 2"` is a string.
The implicit tuple `("Label 2")` is the argument of `label`.
You can also write
```
axis x "Label"
| label ("Label 2")
```
This modifier modifies the label of the keyword.
Thus, the label of this axis will be `"Label 2"` and not `"Label"`, because a modifier always overrides previous properties.

### One line

Every Plank script can be written in one line.

Rules to turn a script into a one line:
1. separate each statement with the statement delimiter `;;`
2. replace every line break by a space

For example,
```
axis x "Label"

plot "x^2"
| color 0 0 0 1
```
could be
```
axis x "Label";; plot "x^2" | color 0 0 0 1
```

## License

This repository is licensed under CC-BY-SA 4.0.

Original idea by William "Anhgelus Morhtuuzh" Hergès with the help from Léo "Léo-21" Kosman and other contributors.

