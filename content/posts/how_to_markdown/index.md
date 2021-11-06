---
title: "Markdownの書き方"
date: 2021-10-27T18:16:20+09:00
lastmod: 2021-10-31T18:16:20+09:00
author: Pei
description: 基本的なMarkdownの文法とサンプルを見てみる
summary: 基本的なMarkdownの文法と、実際にどのように表示されるのかをまとめた
tocopen: true
tags: ["文法"]
categories: ["Markdown"]
# series: []
cover:
    image: logo.png
draft: false
---

---
## 見出し
見出しは６段階で文字の大きさを設定出来る。１～６個のシャープ#で記述する。  
\#と見出し文字の間に半角スペースを入れるのを忘れずに！
~~~md {}
# H1
## H2
### H3
#### H4
##### H5
###### H6
~~~
# H1
## H2
### H3
#### H4
##### H5
###### H6

---
## 改行と段落
半角スペースを２つ記述することで改行出来る。また、空行を挟むことで段落となる。
~~~md {}
あいうえお(半角スペース×２)  
かきくけこ
（空行）
さしすせそ
~~~
あいうえお  
かきくけこ


さしすせそ

---
## 太字
アスタリスク\*２つで囲むことで、太字に出来る。  
アスタリスク\*はアンダースコア_でも可。
```md {}
文字を **太く** します。
```
文字を **太く** します。

---
## 斜体
アスタリスク\*1つで囲むことで、太字に出来る。  
アスタリスク\*はアンダースコア_でも可。
```md {}
文字を _斜め_ にします。
```
文字を _naname_ にします。

---
## インラインコード
バッククォート\`で囲むことで、インライン表示が出来る。
```md {}
インストールコマンドは `install @@@` です。
```
インストールコマンドは`install @@@`です。

---
## 打ち消し線
チルダ~２つで囲むことで、打ち消し線を表示できる。
```md {}
今日は ~~晴れです。~~ 雨でした。
```
今日は ~~晴れです。~~ 雨でした。

---
## エスケープ
ここまで、\#、\*、\`などのマークダウン記号を用いてきた。  
これらの記号を単純に文字として表示したいときはバックスラッシュ\を記述する。
```md {}
インストールコマンドは \`install @@@` です。
```
インストールコマンドは \`install @@@\` です。

---
## リスト
アスタリスク\*、またはハイフン-でリスト表示が出来る。
```md {}
- お茶
    - 紅茶
        - アールグレイ
        - ダージリン
    - 緑茶
- ジュース
```
- お茶
    - 紅茶
        - アールグレイ
        - ダージリン
    - 緑茶
- ジュース
---
## リンク
\[表示文字](URL)　でリンクを張ることが出来る。
```md {}
トップページは[ここ](https://ktwl215.github.io/)です。
```
トップページは[ここ](https://ktwl215.github.io/)です。

Markdownの中に長いリンクを記述するなんてスタイリッシュじゃない！  
同じリンクの参照を何度も書くのは面倒だ！て場合は、リンク先への参照を定義出来る。
```md {}
[top]: https://ktwl215.github.io/
トップページは[ここ][top]です。[これ][top]もトップページです。
[このリンク][top]ももちろんトップページです。
```
[top]: https://ktwl215.github.io/
トップページは[ここ][top]です。[これ][top]もトップページです。  
[このリンク][top]ももちろんトップページです。

---
## 引用・注釈
\>を記述することで、引用を表現出来る。また、注釈をつけることも出来る。  
\[^1]:で注釈を記述している。注釈内容はどこに記述しても文末に表示される。
```md {}
> PaperMod[^1] is a simple but fast and responsive theme with useful feature-set that enhances UX.
[^1]: PaperModとはHugoのテーマの１つで、このサイトで使用しているものです。
PaperModの[デモサイト](https://adityatelange.github.io/hugo-PaperMod/)
```
> PaperMod[^1]  is a simple but fast and responsive theme with useful feature-set that enhances UX.
[^1]: PaperModとはHugoのテーマの１つで、このサイトで使用しているものです。
PaperModの[<span style="color:skyblue">デモサイト</span>](https://adityatelange.github.io/hugo-PaperMod/)

---
## コード
バッククォート\`３つで囲むことで、コードブロックを挿入できる。  
また、言語名を続けて記述することで、シンタックスハイライトも可能（環境による）。
````md {}
``` py
import cv2 as cv

img = cv.imread("filename.png")
gray = cv.cvtColor(img, cv.COLOR_BGR2GRAY) # RGB2~ ではなくBGR2~ に注意
cv.imwrite("output.png", img)
```
````
``` py {}
import cv2 as cv

img = cv.imread("filename.png")
gray = cv.cvtColor(img, cv.COLOR_BGR2GRAY) # RGB ではなくBGR に注意(OpenCVの仕様)
cv.imwrite("output.png", img)
```

---
## テーブル
バーティカルバー|を用いて記述する。これは見た方が早い。

```md {}
| A | B | C |
|---|---|---|
|111|222|333|
```
| A | B | C |
|---|---|---|
|111|222|333|

---
## 画像
!\[代替テキスト](URL"タイトル")　と記述することで、画像を挿入できる。  
代替テキストとは、画像の説明のことで、HTMLに変換した際にalt部分に格納される。  
代替テキストとタイトルは無くてもHTMLへの変換自体に問題はない。
```md {}
![](画像へのパス"depth map")
```
![](cap.PNG "depth map")
[<span style="color:skyblue">Google AI Blog 「Moving Camera, Moving People: A Deep Learning Approach to
Depth Prediction」</span>](https://ai.googleblog.com/2019/05/moving-camera-moving-people-deep.html )より引用
