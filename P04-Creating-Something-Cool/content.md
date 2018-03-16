---
title: "かっこいい絵を描いてみよう"
slug: create-something-cool
---

> [challenge]
> これまでに習ったことを使って、何かかっこいい絵を描いてみましょう！他にも使えるツールを紹介します:

>
> `runDrawing()`や、新しく作る関数の中で使いましょう

# ペンを置いたり離したりする

## ペンを置く
```
penDown()
```

## ペンを離す
```
penUp()
```

> [info]
> 初めはペンを置いた状態からスタートしています。

# ペンを動かす

## stepだけペンを動かす
```
move(steps: Int)
```

## x, yへペンを動かす
```
moveTo(x: Int, y: Int)
```

## 回転させる
```
rotate(degrees: Int)
```

# ペンを変える

## ペンの色を変える
```
setColor(red: Double, green: Double, blue: Double)
```

> [info]
> それぞれの値は0から1の間で設定します。
>
```
setColor(red: 0.0, green: 0.0, blue: 0.0)
```
>
これはペンを黒にセットします。
>
```
setColor(red: 1.0, green: 0.0, blue: 0.0)
```
>
これはペンを赤にセットします。

## ペンの太さを変える
```
set(thickness: Double)
```

## ペンの動きを変える
```
set(delay: Double)
```
