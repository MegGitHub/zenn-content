---
title: "AtCoder Beginner Contest 151 解説【Python】"
emoji: "🐎"
type: "tech" # tech: 技術記事 / idea: アイデア
topics: [atcoder]
published: true
---
どうもこんにちは、Megです。

今回はAtCoder ABC151 の解説を**Python**で行っていきます。

# A - Next Alphabet
問題はこちら。
https://atcoder.jp/contests/abc151/tasks/abc151_a

コードは以下です！自分の提出は[こちら](https://atcoder.jp/contests/abc151/submissions/26683371)。

```python:A.py
import string

alpha_list = list(string.ascii_lowercase)

C = input()

print(alpha_list[alpha_list.index(C) + 1])
```


## コード解説
入力されたアルファベットの次のアルファベットを出力するという問題です。
アルファベット全てが記載されているリストを`string.ascii_lowercase`で作成します。
入力を受けとった`C`を用いて、リストで隣の文字のインデックスを参照し出力します。


## 参考にしたサイト

https://tech-shelf.hatenablog.com/entry/programming/alphabet_list

https://note.nkmk.me/python-list-index/


# B問題以降
誠意記事作成中です。

