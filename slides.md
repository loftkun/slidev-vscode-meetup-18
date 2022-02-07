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

---

<h2>はじめに</h2>

このスライドは、2022/02/04開催の [VS Code Meetup #18 - ドキュメント、ブログ、書籍執筆編](https://vscode.connpass.com/event/236710/) にて、私[@loftkun](https://twitter.com/loftkun) のセッション`Markdownでスライドや書籍も書いちゃおう！`で使用したものです

<div class="grid grid-cols-[50%,50%] gap-4"><div>

本資料(SPA版)<br>

<center>

[<img src="/qrcode_loftkun-slidev-vscode-meetup-18.netlify.app.png" class="h-37">](https://loftkun-slidev-vscode-conference-japan-2021.netlify.app/)

https://loftkun-slidev-vscode-conference-japan-2021.netlify.app/

</center>

</div><div>

YouTubeアーカイブ

<center>

<iframe width="280" height="150" src="https://www.youtube.com/embed/e5-1SVKKHv4?start=3060" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

https://www.youtube.com/embed/e5-1SVKKHv4?start=3060

</center>

</div></div>

❗ PDF( Speaker Deck / slideshare )版をご覧の方へ : ぜひ[SPA版](https://loftkun-slidev-vscode-conference-japan-2021.netlify.app/)をご覧ください :

SPA版ではSlidevツールバー(画面下部に表示されます)や、Webアプリとしての機能( YouTube埋め込みやGIFアニメの再生 )を体験いただけます。(PDF版ではアニメーションは静止画像となってしまいます)

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

趣味はXXXXXXXウィスキーを飲んだりしています。
-->

---

<h2>ご参考</h2>

今日の発表に関連するアウトプットとして、以下の登壇やQiita記事があります。<br>
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
今日の発表に関連するアウトプットとしてVSCodeConJP 2021 での登壇やQiitaのVSCodeアドベントカレンダーに投稿した記事があります。

今日は取り上げない内容として、VSCodeでMarkdownを効率よく書くための拡張機能のご紹介をしていますので、ぜひこちらもご参照いただきますと幸いです。

今日はXXXXXXXXX
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
ここは読むだけ！
-->

---
layout: cover
background: https://source.unsplash.com/collection/94734566/1920x1080
---

## 1. Markdownでスライドを書こう

デモも交えてお送りします

<!--
ここまで2分
-->

---

### 1.1. Slidevとは

Markdownでスライドを記述できるエンジニア向けプレゼンテーションツールです

<div class="grid grid-cols-[65%,35%] gap-4"><div>

<img src="/slidev/01.png" class="h-100">

</div><div>

<Tweet id="1423923567465439237"/>

</div></div>

---

### 1.2. Slidevの導入

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
導入は非常にかんたんです。
Node.js 14以上
XXXXXXXXXXXX
スライドの中身の文章を書くことに専念すれば良いです
-->

---

### 1.3. サンプルMarkdownとLive Demo

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
ここはさらっと！
よく使うと思われる記法のサンプルMarkdownをこちらのリポジトリに用意しております。

ライブデモも用意しておりますので、Markdownの記述内容とSlidevでの見栄えを見比べていただくこともできます。

こちらを後ほどデモしたいと思います。
-->

---

### 1.4. おすすめポイント1: レイアウトが柔軟

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
さらっと！
おすすめポイントXXXXX

私がSlidevを採用しているのは、このGridレイアウトが用意されていること大きな理由となっております。
-->

---

### 1.5. おすすめポイント2: コードブロックのシンタックスハイライトと行番号表示ができる

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
ここもさらっと！
おすすめポイント2としましては、ソースコードコードのシンタックスハイライトと行番号表示がされることですね。
-->

---

### 1.6. おすすめポイント3: 拡張機能もあります ( [antfu.slidev](https://marketplace.visualstudio.com/items?itemName=antfu.slidev) )

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
ここもさらっと！
作者のAntfuさんが、拡張機能を公開していて、プレビューしながらMarkdownの編集ができます。

ヘッダ一覧が表示されますので、その章にジャンプしたり、章の順序の入れ替えもできたりします
ので便利です。
-->

---

### 1.7 デモ : Markdownでスライドを書こう

<br>

<div class="grid grid-cols-[50%,50%] gap-4"><div>

- インストール
- defaultの`slides.md`がスライドとして表示される
- `slides.md` を 書き換える ( サンプルMarkdownを使用 )
- Markdownの記述内容とスライドの表示を確認する

</div><div>

<iframe width="420" height="225" src="https://www.youtube.com/embed/e5-1SVKKHv4?start=3485" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

アーカイブ : https://www.youtube.com/embed/e5-1SVKKHv4?start=3485

</div></div>

---
layout: cover
background: https://source.unsplash.com/collection/94734566/1920x1080
---

## 2. Markdownで電子書籍( epub, mobi )を書こう

デモも交えてお送りします

<!--
ここまで12分
-->

---

### 2.1. Pandocについて

- [Pandoc](https://pandoc.org/) は 様々なドキュメントのフォーマット変換ができるコンバーターです
  - `pandoc is your swiss-army knife`

- Markdownから変換できるフォーマット例
  - html
  - pdf
  - pptx
  - epub
  - などなど、様々なフォーマットに対応しています

<!--
Markdownから電子書籍に変換できるツールとしてPandocを紹介します。
-->

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

<!--
ここはさらっと、デモしますでいいと思う
-->

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

<!--
Kindleで読める形式に変換するにはKindle Previeerというツールが使えます。
-->

---

### 2.4. デモ : Markdownで電子書籍を書こう

<br>

<div class="grid grid-cols-[50%,50%] gap-4"><div>

- サンプルリポジトリをclone
- Markdownファイル( `book.md` ) の内容確認
- epubに変換、閲覧
- mobiに変換、閲覧

</div><div>

<iframe width="420" height="225" src="https://www.youtube.com/embed/e5-1SVKKHv4?start=4240" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

アーカイブ : https://www.youtube.com/embed/e5-1SVKKHv4?start=4240

</div></div>

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

VSCodeのMarkdownの編集支援機能も活用しつつ、SlidevやPandocなどのツールを組み合わせることで、Markdownの活用範囲が広がります！<br>

今回の発表が、VSCodeでMarkdown記法で様々な文書を書く際のご参考となりましたら幸いです。

<!--
全体で18:30
-->

---
layout: cover
background: https://source.unsplash.com/collection/94734566/1920x1080
---

<h1>ご視聴ありがとうございました！</h1>
