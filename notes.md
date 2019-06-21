Tiny Code No.1	小代码 第1期
==

#### Framed, Style an object
tags: Mathematica
```
Table[If[PrimeQ[n], Style[n, Green], n], {n, 100}]
{Panel[1/x + y], Framed[1/x + y]}
```

#### ArrayPlot

```
 ArrayPlot[RandomChoice[{Red, Green, Blue}, {19, 19}], Mesh -> True]
 
 ArrayPlot[{{-1, 0, 1}, {2, 3, -5}, {1, 2, 1}}, 
 ColorRules -> {_?EvenQ -> Red, 1 | -1 -> Blue, 
   x_ /; x < -1 -> Black}]
```
   

#### GraphPlot
```
GraphPlot[RandomChoice[{0.01, 0.99} -> {1, 0}, {100, 100}]]

ArrayPlot[Table[Sin[x y], {x, -40, 40}, {y, -40, 40}], 
 ColorFunction -> "BlueGreenYellow"]
```
 


#### make-a-resizable-chess-board
http://mathematica.stackexchange.com/questions/47441/how-to-make-a-resizable-chess-board

#### apk downloader
http://apkleecher.com/download/?dl=com.smule.magicpiano


> Written with [StackEdit](https://stackedit.io/).
