# [解説]練習1 駐車料金

### 考え方
N日目の駐車料金が何円かに注目して答えを求めます。
最初はX円で1日過ぎるとY円増加するので1日目は`X円`、2日目は`X + Y円`、3日目は`X + 2Y円`となります。
このことからN日目は、
<pre>
X + (N-1)Y 円
</pre>
となることがわかるでしょう。  
駐車料金を1日ずつ足していくと、
```
X 円
2X + Y 円
3X + 2Y 円
4X + 3Y 円
…
```
となります。

後は純粋にA日目までの合計を求めればよいので、答えを導くための式は
<pre>
<img src="https://latex.codecogs.com/png.latex?\sum_{a=1}^N(X&space;&plus;&space;(a&space;-&space;1)Y)&space;=&space;NX&space;&plus;&space;\frac{N(N&space;-&space;1)}{2}Y" />
</pre>
となり、これに与えられた値を代入するとA日目までの駐車料金の合計金額を求めることが出来ます。
