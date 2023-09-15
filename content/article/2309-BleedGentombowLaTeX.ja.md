---
title: "BeamerPosterで塗り足しを設ける"
date: 2023-09-12T19:00:00+09:00
draft: false
summary: "gentombowのbleed幅分だけbackground canvasを拡張する"
showDate: true
excludeFromIndex: false
categories: ["Tips"]
icon: "fa-lightbulb"
tags: ["LaTeX", "Beamer"]
---
LaTeXでポスターを作成する場合，[BeamerPoster](https://ctan.org/pkg/beamerposter)を使うと便利です。  
`header`にタイトルや発表者名，所属を入れ，`beamer color box`を並べてあげればそれっぽくなりますね。

背景にベタが入る場合，塗り足し（bleed）を設けたいところですが，これをLaTeXで実現するにはバウンディングボックスのその側に描画オブジェクトをはみ出させるというチカラワザになります。

幸いBeamerの場合は，背景の描画を`beamertemplete/background canvas`が担っているので，これを再定義して少し大きめに書き直してやれば宜しい。

<script src="https://gist.github.com/atsuyaw/fd52132439a3b7480875e04dea1f08f9.js"></script>

出力:  
![Output](https://user-images.githubusercontent.com/68371029/266809602-fe1bb1ff-6b94-4988-8c8f-49b0c9680cb4.png)

開発版のgentombowでは`\setgentombowshape{cross}`が実装されているようだ。
