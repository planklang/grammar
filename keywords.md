# Keywords in PlankLang

List of keywords and their usage in PlankLang.

## Axis

`axis` modifies how the targetted axis works.

Syntaxe:
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
