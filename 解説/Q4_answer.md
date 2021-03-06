# [解説] 問題4 ユニバス株式会社

### 単純に求める方法
まず、単純に乗っている区間を一人ずつシミュレートする方法を考えてみます。  
問題文で停留所がM個あると書かれているので、長さがMの配列Sを用意します。  
町民iの乗り降りする情報は<code>(A<sub>i</sub>, B<sub>i</sub>)</code>で与えられるので、
配列Sの  
<pre>
A<sub>i</sub>番目から
B<sub>i</sub> - 1番目(B<sub>i</sub>で下車するためB<sub>i</sub>番目の停留所の乗車人数には含まない)
</pre>
までのすべての要素に1を加算します。  
全町民の情報を配列に反映し終えた後に配列Sの要素を調べれば、乗車人数が最大となる停留所と人数を求めることが出来ます。

### 最大の計算回数
ここですべての町民が最初から最後までの停留所を利用する場合を考えてみます。
ある町民の最長の停留所の利用区間は問題文の制約から、
<code>停留所1から停留所10<sup>5</sup></code> 
であることがわかります。  
町民の最大の人数は10<sup>5</sup>人なので、
純粋に一人ずつシミュレートした場合数列Sに対する加算処理は
<pre>
10<sup>5</sup>(回)×10<sup>5</sup>(人) = 10<sup>10</sup>(回)
</pre>
であることがわかります。これは非常に数が大きく処理に時間がかかってしまいます。

### 計算回数の減らし方
ここで、町民の停留所の乗る場所と降りる場所だけに注目してみます。
配列Sへの反映を行う際に、　　
- 乗る停留所のA<sub>i</sub>番目の要素に1を加算(乗ったことを表す)
- 降りる停留所のB<sub>i</sub>番目の要素に-1を加算(降りたを表す)  

という処理だけ行います。
すべての町民についての乗り降りの情報を配列Sに反映し終えるとこの時の配列の要素は各停留所での乗り降りの変化量を表しています。  
これを利用して乗車人数をシミュレートすれば先頭から順番に配列の要素をすべて見るだけで乗車人数が最大となる停留所のその時の人数を求めることが出来ます。
また、この方法を用いたときの上記と同様の条件の場合の計算回数は、
<pre>
2(乗る＋降りる) × 10<sup>5</sup>(人) + 10<sup>5</sup>(配列のすべての要素を見る) = 3 × 10<sup>5</sup>(回)
</pre>
となり、計算する回数が非常に少ないことがわかります。
