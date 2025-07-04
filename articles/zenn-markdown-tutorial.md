---
title: "Zennのマークダウン記法を使ってみる"
emoji: "⛳"
type: "tech" # tech: 技術記事 / idea: アイデア
topics: [Zenn]
published: true
published_at: 2025-06-29 09:00
---

# Zenn のマークダウン記法を使ってみる
メモ兼ブログとして[Zenn](https://zenn.dev/)を使ってみようと思い当たり、[GitHub連携](https://zenn.dev/zenn/articles/connect-to-github)、[CLIの設定](https://zenn.dev/zenn/articles/install-zenn-cli)まで終わった後の話。
最初の投稿記事として、マークダウン記法についていろいろ試していこうと思う。

Zenn公式さんがこちらの記事で丁寧に解説してくださっている。
https://zenn.dev/zenn/articles/markdown-guide

# 実際に使ってみる
なにはともあれ、使ってみた方が分かりやすいということで、さっそくお試し。
以降は、個人的に使用頻度が高いだろうと思ったものから順に書いていこうと思う。


## 見出し1,2,3,…6
#の後に記述する。見出しは6まで記述できるみたい。
目次に反映されるのは見出し2まで。
アクセシビリティの観点から、見出し2から始めるのが良いらしい。

```md
# 見出し1
## 見出し 2
### 見出し 3
#### 見出し4
##### 見出し5
###### 見出し6
```

# 見出し1
## 見出し 2
### 見出し 3
#### 見出し4
##### 見出し5
###### 見出し6


## 空行
適宜空行を挿入すると可読性が上がると思う。
```md
テキスト
&nbsp;
テキスト
```

テキスト
&nbsp;
テキスト

## テキストリンク
文の途中のリンクや、引用など、これは多用しそうな気がします。
```md
[ZennのMarkdown記法](https://zenn.dev/zenn/articles/markdown-guide)
```

[ZennのMarkdown記法](https://zenn.dev/zenn/articles/markdown-guide)


## コードブロック
(```)で囲んだ中に記述。
```md
    ```
    console.log("Hello world!")
    ```
```

```
console.log("Hello world!")
```


## コードブロック（シンタックスハイライト：装飾あり）
(```)の後に言語を指定することでコードを装飾できる。
視覚的にわかりやすいので、こちらを使用していきたい。
ちなみに、対応している`言語`や`記述法`は[https://prismjs.com/#supported-languages](https://prismjs.com/#supported-languages)で確認できるみたい。

javascript
```md
    ```js
    console.log("Hello world!")
    ```
```

```js
console.log("Hello world!")
```

htmlだと↓のような感じ。jsの記法はシンタックスハイライトされない。
```md
    ```html
    console.log("Hello world!")
    <p>Hello world!<p>
    ```
```


~~~html
console.log("Hello world!")
<p>Hello world!<p>
~~~

jsxだときちんと反映されます。
```md
    ```jsx
    console.log("Hello world!")
    <p>Hello world!<p>
    ```
```
~~~jsx
console.log("Hello world!")
<p>Hello world!<p>
~~~


## コードブロック（ファイル名を表示する）
上記から更に（:）で繋いでテキストを入力するとコードのファイル名や見出しのようなものを設定できる。

```md
    ```jsx:index.jsx
    console.log("Hello world!")
    <p>Hello world!<p>
    ```
```

~~~jsx:index.jsx
console.log("Hello world!")
<p>Hello world!<p>
~~~


## リンクカード
URLを指定するだけで、その部分がカードとして表示される。
webページや、youtube、GitHub、Twitterなどに対応。
分かりやすいし、記述も簡単。
```md
https://www.youtube.com/
https://github.com/zenn-dev/zenn-docs/blob/main/README.md
https://x.com/zenn_dev/status/1938039355647660489
```

https://www.youtube.com/
https://github.com/zenn-dev/zenn-docs/blob/main/README.md
https://x.com/zenn_dev/status/1938039355647660489



## 文字の装飾
(*)で囲む：イタリック
(**)で囲む：太字
(~~)で囲む：打消し線
(`)で囲む：インライン
特に、インラインは多用しそうなイメージ。
```md
*イタリック*
**太字**
~~打消し線~~
インラインで`強調`する
```

*イタリック*
**太字**
~~打消し線~~
インラインで`強調`する


## 文字の装飾（メッセージ）
視覚的にわかりやすいZenn独自の記法。

(:::)message　メッセージ
(:::)message alert 警告

```md
:::message
メッセージ
:::

:::message alert
警告メッセージ
:::
```

:::message
メッセージ
:::

:::message alert
警告メッセージ
:::

## 画像
画像はURLやパスで指定できる。
../images…のような相対パス指定はダメみたい。
```md
![](/images/dogs.jpg)
```

![](/images/dogs.jpg)

## 画像（横幅指定）
```md
![](/images/dogs.jpg =200x)
```

![](/images/dogs.jpg =200x)

## 画像にリンクを張る
テキストリンクとくっつけたみたいな感じ。
```md
![](/images/dogs.jpg)(https://pixabay.com/ja/)
```

![](/images/dogs.jpg)(https://pixabay.com/ja/)


## トグル
使えそうな場面は多くあると思う。
記述法は、メッセージと似ている。

```md
:::details タイトル
表示したい内容
:::
```

:::details タイトル
表示したい内容
:::


## リスト
-の後にテキストを記述。インデントで管理するみたい。

```md
- Hello!
    - world
```

- Hello!
    * world

### 番号付きリスト
```md
1. First
2. Second
```

1. First
2. Second


## コメント
メモ用に。
HTML形式で記述できる。表示はされない。
```md
<!-- コメント -->
```

<!-- コメント -->


## 区切り線
```md
-----
```

-----


## テーブル
使い方によってはという感じ。
記述が結構手間なので、使用頻度は少ないかなというイメージ。
```md
| Head | Head | Head |
| ---- | ---- | ---- |
| Text | Text | Text |
| Text | Text | Text |
```

| Head | Head | Head |
| ---- | ---- | ---- |
| Text | Text | Text |
| Text | Text | Text |


## 引用
(>)の後に記述する。
```md
>引用1
>引用2
```

>引用1
>引用2


## 脚注
脚注はページの最下部に設定される。

```md
脚注の例[^1]
脚注の例[^2]
[^1]:脚注の例1です。
[^2]:脚注の例2です。
```

脚注の例[^1]
脚注の例[^2]
[^1]:脚注の例1です。
[^2]:脚注の例2です。


## 数式
使う機会はほぼないだろうけど、こんなこともできるということで。
($$)で囲むと数式のブロックを挿入できる。
```md
$$
e^{i\theta} = \cos\theta + i\sin\theta
$$
```

$$
e^{i\theta} = \cos\theta + i\sin\theta
$$

## 最後に
今回はZennを使ってみる一番最初の記事ということで[公式さんが投稿している記事](https://zenn.dev/zenn/articles/markdown-guide)を参考にメモ感覚でマークダウン記法について記述しました。
まだまだ、できることは多そうです。
これから、学習の過程を少しずつ蓄積していきたいと思います。
ここまで読んでくださり、ありがとうございました。













