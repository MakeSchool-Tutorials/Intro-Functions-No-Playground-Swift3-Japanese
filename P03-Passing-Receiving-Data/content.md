---
title: "もっと賢い関数"
slug: passing-receiving-data
---

## 関数のパラメタ

ところで関数を呼び出すコードの最後にカッコが付いているのを不思議に思いませんでしたか？変数と見た目を変えるためではありませんよ。関数にデータを入れることもあるからです。

ここまでは、ハードコードで`moveFifty()` と `rotateNinety()`を入力してきました。これでも問題ありませんが、 `move(steps: 75)`と入力する方が楽ではないですか？下のスペースで試してみましょう。

> [challenge]
>
- `25`単位分動かせますか？`250`単位分はどうでしょう？マイナス値は？
- 特定の角度を回転させる方法が分かりますか？半時計回りではなく、時計回りで回転させられますか？
- これらを組み合わせて、三角形(3辺)を描けますか？五角形(5辺)はどうでしょう？六角形(6辺)は？

## 復習

 `move(steps: 50)` と `rotate(degrees: 90)`の両方を呼び出すと、`moveFifty()`と`rotateNinety()`と同じ結果が得られます。カッコに整数を入力して、任意の距離を動かせることができます。カッコに入力した整数のことを関数パラメタと言います。 `steps` と `degrees`はどちらも関数パラメタの名前です。

# drawTriangle, drawPentagon, drawHexagon

## 疑似コード

多角形のお絵かきスキルをパワーアップさせましょう。紙とペンを出してください。Swiftのコードを書く前に紙にプロセスを書き出します。

> [action]
> 紙とペンを使って多角形を描いてみましょう。`move`関数や`rotate`関数をどのように使えばうまく描けるでしょうか？
>
> 四角を描いたのと同じように、今度は三角(3辺)、五角形(5辺)、六角形(6辺)を描きましょう。
>
> ## やってみよう!
>
> ステップをひとつずつ書き出し、それを声に出して読み返しながら模擬コードを手書きで「実行」してみましょう。うまくできましたか？
>
> ## ヒント
>
> 図形に長らく触れていない方のために補足です。回転角度は多角形の「外角」と言います。外角は辺と辺を伸ばした時に交差する角度と等しいものです。

>
> Y多角形の外角はexteriorAngle = 360 / numberOfSidesという式で計算できます。 `360 / 4 = 90`は確かに四角の外角ですね。この式を他の多角形にも当てはめて、正しいことを確認しましょう。

## 実装

**ちゃんと手で描きましたか？もし飛ばしたなら「模擬コード」に戻ってやってみましょう。近道しないこと！**

> [challenge]
> それぞれの多角形の疑似コードができたところで、これらをSwiftコードに書き換える作業にうつります。 `drawTriangle`, `drawPentagon`,`drawHexagon` の3つの関数を定義して、それぞれ試してみましょう！

# 関数にデータを入れ込む

## 関数を定義する

これまでは、パラメタのある関数、ない関数を呼び出し、パラメタのない関数は定義の書き方も覚えました。

**パラメタのない関数を呼び出す:**

```
functionName()
```

**パラメタを1つもつ関数を呼び出す:**

```
functionName(parameterName: parameterValue)
```

**パラメタのない関数を定義する:**

```
func functionName() {
   // "function body"
   // function's code goes here
}
```

`func`のキーワードではじめ、関数の名前、カッコ、と入力し、関数のなかのコードは中カッコで挟みます。

## 関数の定義にパラメタを組み込む

**1つのパラメタをもつ関数の一般的な形：**

```
func functionName(parameterOneName: parameterOneType) {
   // "function body"
   // function's code goes here
   // value passed in becomes a constant with the name parameterOneName
}
```

これを先程書いた関数の定義と比べてみると、カッコの中にパラメタの名前とタイプが入力されているのが分かります。最初は同じキーワード`func`で書き出し、関数の名前、カッコ、中カッコと続きます。中カッコの中身はインデントすることを忘れずに！(Xcodeが自動的にインデントしない場合は、キーを押すだけ簡単にできます)

前に勉強した変数の定義と同じように、パラメタの定義でもデータタイプを指定する必要があり、異なるデータタイプの関数を呼び出すことはできません。パラメタの名前もまた、変数の名前に似ています。分かりやすく、短い名前を心掛けましょう。他のプロクラマーが見ても、何の役割があるのか一目瞭然であるのが理想的です。

## データタイプの復習

データタイプはプログラミングに使われている情報の種類を示します。変数や定数の定義、値の修正、関数にパラメタを入れ込む場合に重要となります。これまで3つのデータタイプを学びましたね。

- `Int`: 整数、割り算で少数が出た場合は小数点以下が必ず切り捨てられる
- `Double`: 少数
- `String`: 英数字やその他記号の文字列、たとえ数字だけの文字列であっても計算式は作れない。Stringはダブルクオーテーションで挟まれている (`"これはstring!"`)

## より多目的なdrawSquare

> [challenge]
> 大きさを規定するパラメタを含む、新しい`drawSquare`関数を作りましょう。これでひとつの関数で色々な大きさの四角形を描くことができます！下のスペースに途中まで書いています。`drawSquare`は`sideLength`という `Int`のデータタイプ(整数)のパラメタです。関数の中身を書き込みましょう。
>
```
func drawSquare(sideLength: Int) {
>
}
```
>
> `sideLength`は関数の中で定数となります。定数や変数は他の関数を呼び出す時にパラメタの役割をします。`drawSquare(sideLength: 150)`という関数を呼び出して新しい手法を試してみましょう。
>
> 定義を書いた後にはdrawSquare関数を呼び出すことを忘れずに！前のページで練習した通り、パラメタを含む形で呼び出す必要があります。

## すべてうまくいきましたか？

> [challenge]
> 大きさを調整できる`drawSquare`のコードがうまく実行できたら、`drawTriangle`, `drawPentagon`, `drawHexagon`も同じように変更してみましょう。

# コードを繰り返す

## "loops" の簡単な紹介

何度かポリゴン関数を書き直しましたが、もしかしたらもっと一般的にポリゴンが描きたくなるかもしれません、紙とペンを使って、今使っているコードをどうしたら減らすことができるか考えてみましょう。

今回は、`move`と`rotate`を１度ずつしか使わず、`drawTriangle`, `drawSquare`, `drawPentagon`, and `drawHexagon`を完成させる方法を考えてみましょう。

次のように書くと...

```
repeat 4 times
    move 10
```

全部で40単位分(一度に10単位ずつ)動くことになります。

> [action]
> これまで通り、紙に書き出した模擬コードを自分で読み返し、コードを「実行」してポリゴンを描いてみましょう。

## いい感じ？

擬似コードをSwiftに変換しましょう。

```
repeat 4 times
    move 10
```

Swiftでは、上の擬似コードは下のように書き換えられます。

```
for _ in 1...4 {
    move(steps: 10)
}
```

for-loop構文は後で詳しく勉強しますが、今はこのように一般化できる、という事だけ知っておきましょう。

```
for _ in 1...numberOfTimes {
    // "for-loop body"
    // code repeated numberOfTimes goes here
}
```

関数の中身のように、for-loopの中身は中カッコで挟まれます。また、関数の中身と同じように、中カッコの中はインデントをします。

## やってみよう！

> [challenge]
> "for-loops"の書き方が分かったところで(何行かのコードの繰り返し)、`drawTriangle`, `drawSquare`, `drawPentagon`,  `drawHexagon`の手法をそれぞれ修正してみましょう。修正後も大きさを調整できる関数であることを確かめましょう！

# 関数にもっとデータを渡す

## もっと多くのパラメタ

さてここまでで、パラメタのない関数か、１つだけパラメタのある関数を見てきましたね。２つのパラメタを持つ関数を定義して見ましょう！どんな書き方か想像できますか？

## ポリゴン関数を一般化する

`numberOfSides: Int`と`sideLength: Int`をパラメタに持つ`drawPolygon`関数を作るには:

```
func drawPolygon(numberOfSides: Int, sideLength: Int) {
    // "function body"
}
```

> [info]
> パラメタ同士はカンマで区切ります。このようにカンマで区切っていけば、いくらでもパラメタを追加することができますよ！

## 試してみよう！

> [challenge]
> 上のテンプレートを使って、`drawPolygon`関数を作りましょう。for ループを使うといいでしょう！

## １つ以上のパラメタを持つ関数を呼び出す

この関数を呼び出したい時は、どうしたらいいでしょうか？`drawPolygon(numberOfSides: 3, 100)` でしょうか？いや、これでは動きません！

`drawPolygon(numberOfSides: 3, sideLength: 100)`.が正しい呼び出し方です。

## どういうこと？

`drawPolygon(numberOfSides: 3, sideLength: 100)`は動くのに、`drawPolygon(numberOfSides: 3, 100)` はどうして動かないのでしょう。デフォルトでは、Swiftはそれぞれのパラメタに、パラメタラベルを必要とします。パラメタの名前を明言しなかったら、Swiftはパラメタの名前をラベルとして使いたいのだと推測してしまうのです。つまり、複数のパラメタを持つ関数の一般的フォーマットは下のようになります:

```
functionName(parameterOneName: parameterOneValue, parameterTwoName: parameterTwoValue)
```

> [challenge]
>  `drawPolygon` を呼び出して、動くか確かめて見ましょう！

# データを返す

## 戻り値

最後にもう一つ、関数ができることがあります。データを返すことです！良いコードの条件は読みやすいことで、データを返す関数を使うと、綺麗に整理されたコードになります。

どのように定義をすれば良いか見てみましょう。

> [info]
> 円の一周は360度か、2πラジアンです。半周は180度で、πラジアンです。四分の一の円は、90度でπ/2ラジアンです。
>
> `M_PI` はSwiftが持つ定数で、Double型のπを表します。

```
func radiansToDegrees(radians: Double) -> Double {
  return radians * 180 / M_PI
}

let halfPiRadiansInDegrees = radiansToDegrees(radians: M_PI / 2)
let piRadiansInDegrees = radiansToDegrees(radians: M_PI)
let twoPiRadiansInDegrees = radiansToDegrees(radians: 2 * M_PI)
```

## 返り値を持つ関数を定義する

**返り値を持つ関数の書き方:**

```
func functionName() -> ReturnType {
    // "function body"
    return valueToReturn
}
```

パラメタはいくつでも追加できますが、大事なポイントがあります。

1. `-> ReturnType`: `ReturnType`には返したい値のデータ型を入力します。 (`Int`, `Double`, `String`, など)
2. `return valueToReturn`: `return`は、Swiftにこの行で関数を終了して、`return` の後に書かれている値を返してね、と命令します。`valueToReturn`は`ReturnType`で定義したデータ型と同じでなくてはいけません。

> [info]
> この関数は何があっても`ReturnType`を返さなくてはいけません！

## 角度からラジアンへ

返り値を持つ関数を定義してみましょう！

> [challenge]
> `degreesToRadians`を書いて、テストコードをアンコメントしましょう。 `Double`型の`degrees`をパラメタとして受け取り、`Double`を返します。
>
> **ヒント**
>
> 角度からラジアンへの変換の計算は、上に書いてある関数の計算を逆にして使えますね。`180`で割って、`Double.pi` (π)をかける。
>
>  1/2πはだいたい1.57、π はだいたい3.14, 2πは約6.28です。書いた関数がこの数字と合っているか確かめましょう。

# drawPolygonを書き直す

> [challenge]
>  `calculateRotationForPolygon`関数を下に作ります。`Int`型の`sides`をパラメタとして受け取り、`Double`の値を返します。前に書いた `drawPolygon`関数をコピーしてきて使いましょう。

<!--  -->

> [info]
> `sides(辺の数)`は `Int` から `Double` へ _キャスト(変換)_  する必要があります。Swiftはデータ型にとても厳しいのです！`Double(sides)`と書くことで、_キャスト(変換)_ することができます。
