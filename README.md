# Official Website of TEDxTsukuba

## Introduction
TEDxTsukubaのウェブサイトは

- 学生団体はメンバーの入れ替わりが激しい．
  - 3~4年で引き継ぐ必要がある．
- Web技術の進化のペースは速い．
  - その上，初心者の参入ハードルは，世間で言われているほど低くはない(と思う)
- 開発経験の豊富なメンバーが入ってくるとは限らない．
  - わざわざリクルートして部署を設けるほど大きな学生団体ではない．
- TEDxUTsukubaのサイトと異なり，頻繁な更新は必要ない

といった点を考慮して，長期にわたり安定して利用できることを優先し，いわゆるモダンなフレームワークなどを極力使わず，HTMLとCSSがある程度理解できれば誰でもメンテナンスできるようにしています．

## Prerequisites

- HTMLとCSSの書き方がわかり，エディタとウェブブラウザを使って作業ができる．
- JavaScriptの基礎がわかる．変数, オペレータ(演算記号), 関数, 配列, オブジェクト, JSONなど. 
- GitHubのアカウントを持っており，clone, commit, pushなどのコマンドの使い方がわかる．

ことを前提とします．

ここまでの学習には下記の動画などを活用してみてください．
- [CS50 Week8 - Harvard](https://cs50.jp/x/2021/week8/)
- [Git Basics - GitHub](https://youtube.com/playlist?list=PLg7s6cbtAD165JTRsXh8ofwRw0PqUnkVH)




## Setup
### node.js
node.js (v15.x)を使います．各自の環境にインストールしておいてください．バージョンが異なると，エラーになることがあります．

### browsersync
[browsersync](https://browsersync.io/#install) を使うと，ブラウザを再読み込みすることなく，エディタの変更が直ちにブラウザに反映されるようになります．便利なのでインストールして利用しましょう．


### Alpine.js
Alpine.jsは，JavaScriptの変数をHTMLのコード内で利用することができます．何が嬉しいかというと，データとUIを分離できるのです．下記の例を見てください．

```html
<template x-for="(item, index) in items">
  <p x-text="item.title"></p>
  <a x-bind:href="item.video">Video</a>
</template>
```

```javascript
items: [
  {
    title: "Intro to Alpine.js in Just 7 Minutes",
    video: "https://www.youtube.com/watch?v=M3fY0E60cM0"
  },
  {
    title: "Everything you need to know about the Netlify platform",
    video: "https://www.youtube.com/watch?v=XG8nJDWu3a0"
  }
]
```
ブラウザで描画されたページのソースコードは下記のようになります．
```html
<p>Intro to Alpine.js in Just 7 Minutes</p>
<a href="https://www.youtube.com/watch?v=M3fY0E60cM0">Video</a>

<p>Everything you need to know about the Netlify platform</p>
<a href="https://www.youtube.com/watch?v=XG8nJDWu3a0">Video</a>
```


JavaScriptの中に[オブジェクト](https://developer.mozilla.org/ja/docs/Web/JavaScript/Reference/Global_Objects/Object)として記述したデータを，HTMLで `x-for` という Alpine.js 独自の属性を使ってループさせることで，繰り返し描画しています．これはVueやReactの特徴でもありますが，ビルドを必要とせず，HTMLファイル1つだけで手軽に実現できるのがAlpine.jsの強みです．

公式のドキュメントを要約したようなドキュメントがあったので，詳細はこちらを参照してください．
https://daily.dev/blog/alpine-js-the-ultimate-guide

### About Bulma
CSSフレームワークです．CSSを手書きすることなく利用できます．

___

**Disclaimer**

> In the spirit of ideas worth spreading, TEDx is a program of local, self-organized events that bring people together to share a TED-like experience. At a TEDx event, TED Talks video and live speakers combine to spark deep discussion and connection. These local, self-organized events are branded TEDx, where x = independently organized TED event. The TED Conference provides general guidance for the TEDx program, but individual TEDx events are self-organized. (Subject to certain rules and regulations.) 

Copyright &copy; 2021 TEDxTsukuba All Rights Reserved. 