# Keywords in PlankLang

List of keywords and their usage in PlankLang.

## Axis

`axis` modifies how the targetted axis works.

Syntax:
```
axis <identifier: target> [string: label] [number array: range]
```
- `target` is the identifier of the axis.
- `label` is the label of the axis.
- `range` is the range of the axis. It must be a number array of length 2. The first item is the minimum and the second is the maximum.

Example:
```
axis x # target the axis x

axis x "X axis" # target the axis x and set its label to "X Axis"

axis y [0 10] # target the axis y and set its minimum to 0 and its maximum to 10

axis y "Y Axis" [0 10] # target the axis y and set its minimum to 0, its maximum to 10 and its label to "Y Axis"
```

## Plot

`plot` populates the plot.

Syntax:
```
plot <string: function>
```
- `function` is the mathematical function to use. It must follow this syntax: `arg1 -> expression` where expression is a mathematical expression using `arg1` as a variable. If `arg1 ->` is omitted, `x` is implicitly deduced to be the variable.

Example:
```
plot "x -> x^2" # populate the plot with the quadratic function

plot "1/x"

plot "3x!^exp(x)/2" # LaTeX equivalent: $\frac{3x!^{\exp(x)}}{2}$
```

## Default

`default` modifies the default values of modifiers.

Syntax:
```
default <identifier: target> <tuple: value>
```
- `target` is the modifier to edit
- `value` is the value to use

Example:
```
default color (0 0 0 1)

default color (255 0 0 1)

default color (0 0 0 .5)
```
