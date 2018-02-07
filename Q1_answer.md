# 問題1解説

まずはさとしマートで商品を買った後の所持金額を考えていきましょう。残りの所持金額でひろしストアで商品をいくつ買えるか考えていけばOKです。

例を使って説明すると、たかし君の所持金額は5000円でスタートです。
商品Pは3000円なので、残りの所持金額は2000円です。
商品Qは700円なので、商品は2つ買えます。
残った600円がたかし君のお小遣にになります。

これをまとめると以下のようになります。

```
1. 所持金額Aから商品Pの値段を引く（残りの所持金額を仮にBとする）
1. Bから商品Qの値段を引く（残りの所持金額を仮にCとする）
1. 2を、C < Qになるまで繰り返す
```