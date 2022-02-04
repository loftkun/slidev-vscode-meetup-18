---
theme: seriph
title: Markdownでスライドや書籍も書いちゃおう！
download: false
lineNumbers: true
background: https://source.unsplash.com/collection/94734566/1920x1080
class: text-center
---

# Markdownでスライドや書籍も<br>書いちゃおう！

<br>

2022/02/04 VS Code Meetup #18 - ドキュメント、ブログ、書籍執筆編

@loftkun ( 甲斐 新悟 )

<!--
準備

- タイマーをリセット
- 左手は矢印キー
-->

---

<h2>$ whoami</h2>
<br>
<div class="grid grid-cols-[25%,75%] gap-4"><div>
<img src="/loftkun.jpg"/>
</div><div>

```markdown
# loftkun

- IT Specialist at IBM ( ex Yahoo! )
  - Linux OS ( RHEL, etc ), OSS ( OpenShift, etc )
- Python lecturer at Kyushu University Lab ( in 2021 )
- Staff of VS Code Conference Japan 2021

- 🎹 Piano ( YouTuber )
- ☗ 観る将＆指す将
- 🍶 ウィスキー
- 🚲 有酸素運動
```

</div></div>

<div class="grid grid-cols-[25%,25%,50%] gap-4"><div>

<img src="/whisky.jpg" />

</div><div>

<center>
<img src="/recognized-speaker.png" class="w-55"/>
</center>

</div><div>

[<img src="/ex280.png" class="w-95"/>](https://rhtapps.redhat.com/certifications/badge/verify/BBDH42VN3CSJRXWN6CFVNWD4NIAEQU3CUPSQX2KSDXT6RW46LQ3USGMBTDNSOFVX22WYNJ63KCC3BBTAOIVCQWO7U3Z7NRP66BA673I=)

</div></div>

<!--
loftkunと申します
お仕事は Linux OSや各種OSSの検証やトラブルシューティングをしています
また、副業で大学研究室向けにPythonの講義をしています
今回の発表はこのPython講義のために、Markdownを使って効率よくスライドなどの資料を作成している経験を元にノウハウをお話したいと思っています。

また、昨年VSCodeConferenceJapan2021のスタッフをさせていただいたりしております。

趣味はXXXXXXX 有酸素運動の方をしております。
-->

---

<h2>ご参考</h2>

今回の発表に関連するアウトプットとして、以下の登壇やQiita記事があります。<br>
VSCodeでMarkdownを効率よく書く方法や、Markdownでスライドや電子書籍を書く手順をご紹介しています。

<div class="grid grid-cols-[50%,50%] gap-4"><div>

[VS Code Conference Japan 2021](https://vscode.connpass.com/event/221961/) での発表

<iframe class="w-100 h-57" src="https://www.youtube.com/embed/J2li3qYgu9U?start=3229" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

</div><div>

[Qiita | Visual Studio Code Advent Calendar 2021](https://qiita.com/loftkun/items/414ed6c7789b49ed0c5e)

[<img src="/qiita.jpg"/>](https://qiita.com/loftkun/items/414ed6c7789b49ed0c5e)
こちらの記事はQiitaトレンド1位になりました！

</div></div>
今日は、実際にMarkdownでスライドや電子書籍を書く様子をサンプルとデモを交えてご紹介したいと思います！

<!--
YouTubeの再生開始と止める
-->

---

## Agenda

<br>

### 1. Markdownでスライドを書こう

- Slidevのご紹介 ( この発表スライドもMarkdownで書いてSlidevでスライドとして表示しています )

- サンプルMarkdownを使ったデモ

### 2. Markdownで電子書籍( epub, mobi )を書こう

- Pandocのご紹介

- サンプルMarkdownを使ったデモ

<!--
Slidevのツールバーが見えておりまして

- ダークモード
- 一覧表示
- カメラ映像表示 顔出し
- 録画機能、事前収録もできます
-->

---
layout: cover
background: https://source.unsplash.com/collection/94734566/1920x1080
---

## 1. Markdownでスライドを書こう

デモも交えてお送りします

---

### 1.1. Markdownでスライドを書くには

<br>

- スライドの文章をMarkdownで書き、ツールでMarkdownをスライドとして表示させます
  - スライドとしてのデザインや機能はツールに依存します
  - Markdwon側でも多少のレイアウトの指定は可能です

<br>

- 発表の内容(文章)を書くことに専念し、短時間でまとまった量のアウトプットを出したい場合におすすめです
  - 私の場合、本業の合間に副業のPythonの講義資料を作るための目的に合っていました

<br>

- 様々なツールがありますが、今回は、Slidevを紹介したいと思います！
  - [reveal.js](https://revealjs.com/)
  - [Marp](https://marp.app/)
  - [Slidev](https://sli.dev/)

---

### 1.2. Slidevとは

Markdownでスライドを記述できるエンジニア向けプレゼンテーションツールです

<div class="grid grid-cols-[65%,35%] gap-4"><div>

<img src="/slidev/01.png" class="h-100">

</div><div>

<Tweet id="1423923567465439237"/>

</div></div>

---

### 1.3. Slidevの導入

<div class="grid grid-cols-[50%,50%] gap-4"><div>

```log
$ npm init slidev@latest

  ●■▲
  Slidev Creator  v0.27.15

✔ Project name: … demo
✔ Package name: … demo
  Scaffolding project in demo ...
  Done.

✔ Install and start it now? … yes
✔ Choose the agent › npm

  ●■▲
  Slidev  v0.27.15

  theme   @slidev/theme-seriph
  entry   /home/loft/slidev-demo/slides.md

  slide show      > http://localhost:3030/
  presenter mode  > http://localhost:3030/presenter
  remote control  > pass --remote to enable

  shortcuts       > restart | open | edit
```

</div><div>

- これだけでOK ( 要 `Node.js >=14.0` ) 
- ブラウザで閲覧できます( `localhost:3030` )
- あとは slides.md を執筆していくだけ！
- プレビューにも動的に反映されます

![](/slidev/01.png)

</div></div>

<!--
スライドの中身の文章を書くことに専念すれば良いです
-->

---

### 1.4. サンプルMarkdownとLive Demo

|                 |                                                                                |                               |
| :-------------: | :----------------------------------------------------------------------------- | :---------------------------- |
|    Markdown     | [github.com/loftkun/slidev-example](https://github.com/loftkun/slidev-example) | slides.md をご参照ください    |
| Live Demo (SPA) | [loftkun-slidev-example.netlify](https://loftkun-slidev-example.netlify.app)   | Netlify にデプロイしたSPAです |

<div class="grid grid-cols-[55%,35%] gap-15"><div>

![](/slidev/02.png)

</div><div>

<Tweet id="1423923567465439237"/>

</div></div>

<!--
Markdownでよく使うと思われる記法のサンプルをこちらのリポジトリに用意しております。

ライブデモも用意しておりますので、Markdownの記述内容とSlidevでの見栄えを見比べていただくこともできます。

こちらを後ほどデモしたいと思います。
-->

---

### 1.5. おすすめポイント1: レイアウトが柔軟

Gridレイアウトによりコンテンツを柔軟に配置できます

<br>
<center>ここは横幅いっぱい使えるよ</center>
<br>
<br>
<br>

<div class="grid grid-cols-[33%,33%,33%] gap-4"><div>

<center>左グリッド</center>
<br>
<br>

</div><div>

<center>中央グリッド</center>

</div><div>

<center>右グリッド</center>

</div></div>

<br>
<center>ここは横幅いっぱい使えるよ</center>
<br>

```html
ここは横幅いっぱい使えるよ
<div class="grid grid-cols-[33%,33%,33%] gap-4"><div>
左グリッド
</div><div>
中央グリッド
</div><div>
右グリッド
</div></div>
ここは横幅いっぱい使えるよ
```

<!--
私がSlidevを採用しているのは、このGridレイアウトが用意されていること大きな理由となっております。
-->

---

### 1.6. おすすめポイント2: コードブロックのシンタックスハイライトと行番号表示ができる

ソースコードやコマンドの実行結果などのコードブロックを綺麗に表示できます

Pythonソースコードの表示例 : 

<div class="grid grid-cols-[50%,50%] gap-4"><div>
before

```python {4-}
import os
test_path = os.path.join("data", "data-01.txt")

f = open(test_path, "a", encoding="utf-8")
f.write("this is new append line\n")
f.close()
```

</div><div>
after

```python {4-}
import os
test_path = os.path.join("data", "data-01.txt")

with open(test_path, "a", encoding="utf-8") as f:
    f.write("this is new append line\n")
```

</div></div>

特徴

- 行番号の表示ができるため、行番号での意思疎通できて便利です
- 着目して欲しい行を強調できます ( 上記の例では 4行目以降 )
- 画像ではなくテキストなので、文字列のコピーや検索も可能です
- 上記のように、Gridレイアウトを使うことで左右で比較、のような表現も可能です

<!--
おすすめポイント2としましては、ソースコードコードのシンタックスハイライトと行番号表示がされることですね。

こちらはPythonのコードで、前のページでご紹介した Gridレイアウトを利用しまして、左右にソースコードを配置して比較しやすいようにしております。
-->

---

### 1.7. おすすめポイント3: 拡張機能もあります ( [antfu.slidev](https://marketplace.visualstudio.com/items?itemName=antfu.slidev) )

<br>

<div class="grid grid-cols-[60%,40%] gap-4"><div>

![](/slidev/03.gif)

</div><div>

<br>

- プレビュー表示ができる
  - Markdownの編集が即反映されます
- スライドのタイトル一覧表示、ジャンプができる
  - 順序の変更ができます

</div></div>

<!--
作者のAntfuさんが、拡張機能を公開していて、プレビューしながらMarkdownの編集ができます。

ヘッダ一覧が表示されますので、その章にジャンプしたり、章の順序の入れ替えもできたりします

ので便利です。
-->

---

### 1.8 デモ : Markdownでスライドを書こう

<br>

- インストール
- defaultの`slides.md`がスライドとして表示される
- `slides.md` を 書き換える ( サンプルMarkdownを使用 )
- Markdownの記述内容とスライドの表示を確認する

<!--
このように、Slidevはインストールからスライドの表示、VSCodeでMarkdownで編集が素早くできるように作られていますので、ぜひドキュメントとかサンプルのMarkdownの方も見ていただいてスライド作りに使えるツールの候補の1つとしてご活用いただいけると良いかなと思います。Markdownでスライドを書く方法のご紹介は以上となります。
-->

---
layout: cover
background: https://source.unsplash.com/collection/94734566/1920x1080
---

## 2. Markdownで電子書籍( epub, mobi )を書こう

デモも交えてお送りします

---

### 2.1. Markdownで電子書籍( epub, mobi )を書くには

- 書籍の文章をMarkdownで書き、ツールでMarkdownを電子書籍のフォーマットに変換します
  - 画像の挿入や表もMarkdown記法で書くことができます

- 私はPandocというツールを使用しています
  - 様々なドキュメントのフォーマット変換ができるコンバーターです

- PandocでMarkdownから変換できるフォーマットの例 :
  - html
  - pdf
  - pptx
  - epub
  - などなど、様々なフォーマットに対応しています
    - 詳細は [pandoc.org](https://pandoc.org/) をご参照ください

---

### 2.2. サンプル

<style>
.language-bash span.line { /* bashのコード */
  margin-left: -40px; /* 左に40px移動して行番号を隠す(邪道) */
}
</style>

|                                                                                      |                 |                  |
| :----------------------------------------------------------------------------------- | :-------------- | ---------------- |
| [github.com/loftkun/markdown-to-ebook](https://github.com/loftkun/markdown-to-ebook) | book.md         | Markdownファイル |
|                                                                                      | ebook/book.epub | epubファイル     |

Markdownからepubに変換するコマンドの例 : 

```bash
$ pandoc --from markdown --to epub3 book.md --output book.epub --toc --epub-cover-image=img/cover.png
```

|                  |                        |
| ---------------- | ---------------------- |
| from             | 変換元のフォーマット   |
| to               | 変換先のフォーマット   |
| output           | 出力ファイルのパス     |
| toc              | 目次出力を有効化       |
| epub-cover-image | 表紙画像ファイルのパス |

---

### 2.3. Kindleでも読めます

[Kindle Previewer](https://kdp.amazon.co.jp/ja_JP/help/topic/G202131170) を使うとepubをmobi形式に変換でき、Kindleでも閲覧できます

<div class="grid grid-cols-[60%,40%] gap-10"><div>

epubの閲覧、mobi(Kindleで閲覧可能)への変換が可能です

![](/epub/03.gif)

</div><div>

Kindle Paperwhite で表示した例

<img src="/epub/02.jpg" class="h-80">

</div></div>

---

### 2.4. デモ : Markdownで電子書籍を書こう

<br>

- サンプルリポジトリをclone
- Markdownファイル( `book.md` ) の内容確認
- epubに変換、閲覧
- mobiに変換、閲覧


<!--
Kindleの実機の方に送り込みますと表示されますので、VSCodeで効率よくMarkdown記法でコンテンツを書くことに集中できて、コストをかけずに電子書籍が作成できる方法の1つとしてご紹介いたしました。
-->

---

## 3. まとめ

<br>

### 1. Markdownでスライドを書こう

<br>

- Slidevのご紹介
- サンプルMarkdownを使ったデモ

<br>

### 2. Markdownで電子書籍( epub, mobi )を書こう

<br>

- Pandocのご紹介
- サンプルMarkdownを使ったデモ

<br>

VSCodeのMarkdownの編集支援機能も活用しつつ、SlidevやPandocなどのツールを組み合わせることで、Markdownの活用範囲が広がります<br>

今回の発表が、VSCodeでMarkdown記法で様々な文書を書く際のご参考となりましたら幸いです。

---
layout: cover
background: https://source.unsplash.com/collection/94734566/1920x1080
---

<h1>ご視聴ありがとうございました！</h1>
