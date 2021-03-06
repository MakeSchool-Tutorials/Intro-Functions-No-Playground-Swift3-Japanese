---
title: "カスタマイズされた関数"
slug: custom-functions
---

自分の関数を作ってみましょう。さっき四角を描くコードを書きましたね。これが`drawSquare()`関数として使い回しできれば便利でしょう？

## 関数の定義

関数の呼び出しの方法は既に勉強しましたが、自分の関数はどうやって作るのでしょう？

```
func functionName() {
    // “関数コードの中身”
    // 関数のコードはここに入力
}
```

関数は`func`というキーワードを使って定義します。(変数を`var`で、定数を`let`で定義するのと似ていますね)　関数の名前(この場合は`functionName`)は`func`の後に入力し、カッコを付けます。続いて中カッコ(`{`と`}`)を入力します。キーボードのエンターキーのそばにあります。Shiftキーを押しながら入力します。

関数のコードはすべて中カッコの中におさめましょう。関数を呼び出すと、中カッコの中のコードが実行されます。

## はじめての関数

> [challenge]
> 自分なりの`drawSquare`関数を定義してみましょう。上の関数を参考にしつつ、必ず名前を変えましょう！四角を描くコードを前のページからコピーし、“関数コードの中身”に張り付けると簡単にできます。

<!--  -->

> [action]
> カスタム関数を作ったので、`// drawing code goes below here`と
`// drawing code goes above here`の間のコードはいりませんね。消してみましょう。

## うまく動きましたか？

画面上にイメージ通りに四角が描かれましたか？もし失敗したなら、それはどうしてでしょう？

**関数の定義をしてもコードは実行されない**

コードを実行するには、その関数を呼び出さなくてはなりません。ステップを丁寧にこなしても、画面ビジュアルには何も変化がなかったでしょう。新しい関数を定義しただけで、呼び出していなかったからです。上に戻って新しい行(中カッコを閉じた後)に`drawSquare`関数を呼び出すコードを書いてみましょう。これで画面上に四角が出てくるはずです。


> [action]
> `// drawing code goes below here` と `// drawing code goes above here`の間で、`drawSquare`関数を呼び出しましょう。

## 関数に名前を付ける

関数の名前は、変数の名前と同じルールで付けます。

- アルファベットではじめる
- 英数字と特定の記号が使える
- 空欄は使わない

## インデント

ところで、"関数の中身"のテキストはすべてインデントされていることに気が付きましたか？プログラミングでは、中カッコの中はインデントするのが一般的です。(Xcodeが自動的にインデントしない場合は、tabキーを押すだけで簡単にできます)お手本のインデントを真似してコードを書いてみましょう。より読みやすくするためには大切なことです。

# 「大きな」チャレンジ

## もっと大きな四角を描く

> [challenge]
> 新しいスキルを試してみましょう。前のページでは `drawSquare`関数を定義しましたね。下のスペースで`drawBigSquare`の関数を定義してみましょう。今度は、`drawSquare`関数と比べて辺の長さが2倍の四角を描けるようにしましょう。

<!--  -->

> [info]
> ひとたび `drawBigSquare`関数が定義できたら、呼び出しをして画面上にイメージ通りの四角が描かれるか確認しましょう。
