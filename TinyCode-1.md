Tiny Code No.1	小代码 第1期
===================

### Framed, Style an object in Mathematica
```
Table[If[PrimeQ[n], Style[n, Green], n], {n, 100}]
{Panel[1/x + y], Framed[1/x + y]}
```

### ArrayPlot
 ArrayPlot[RandomChoice[{Red, Green, Blue}, {19, 19}], Mesh -> True]
 
 ArrayPlot[{{-1, 0, 1}, {2, 3, -5}, {1, 2, 1}}, 
 ColorRules -> {_?EvenQ -> Red, 1 | -1 -> Blue, 
   x_ /; x < -1 -> Black}]
   
### Chat for GitHub
https://gitter.im/poemus/poemus.github.io

> Written with [StackEdit](https://stackedit.io/).
