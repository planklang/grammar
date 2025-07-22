# PlankLang grammar

Plank (or PlankLang) is a new programming language describing plots.
It aims to be simple, straightforward, readable, intuitive and modular.

## Example

This is a simple Plank script.

```plank
axis x [0, 10] "Label X"
axis y [-5, 100] "Label Y"

plot x -> x^2
| color (0, 0, 0, 1) # RGBA <- comment
| width 1

plot x -> exp(x)
| color (0, 0, 0, 1)
| width 1
```

Firstly, it defines how the grid works.

`axis x [0, 10] "Label X"` describes how the X axis works.
`[0, 10]` is the range of the axis and `"Label X"` is its label.

`axis y [-5, 100] "Label Y"` describes how the Y axis works.
`[-5, 100]` is the range of the axis and `"Label Y"` is its label.

Then, it defines what populates the plot.

`plot x -> x^2` is the mathematical function $x\mapsto x^2$.
This will populate the plot.
`| color (0, 0, 0, 1)` sets the color of the graph (RGBA).
`| width 1` sets the width of the line.

`plot x -> exp(x)` is the mathematical function $x\mapsto\exp(x)$.
This will also populate the plot.
`| color (0, 0, 0, 1)` sets the color of the graph (RGBA).
`| width 1` sets the width of the line.

Finally, the plot is rendered.

You can also write this script in one line:
`x [0, 10] "Label X";; y [-5, 100] "Label Y";; plot x -> x^2 | color (0, 0, 0, 1) | width 1;; plot x -> exp(x) | color (0, 0, 0, 1) | width 1`. 
Plank uses `;;` to separate two instructions.

## Specification

We are currently working on this.

## Learn

We are currently working on this.

## License

This repository is licensed under CC-BY-SA 4.0.

Original idea by William "Anhgelus Morhtuuzh" Hergès with the help from Léo "Léo-21" Kosman and other contributors.

