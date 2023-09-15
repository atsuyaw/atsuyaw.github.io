---
title: "MS PowerPointで「°C」がうまく入力できない。欧文フォントにならないDegree Sign"
date: 2023-03-20T15:00:00+01:00
draft: false
summary: "「°」を欧文フォントで入力したい"
showDate: true
excludeFromIndex: false
categories: ["Tips"]
icon: "fa-lightbulb"
tags: ["Microsoft Office", "PowerPoint", "Presentation", "Font"]
---

<p>
<img src="//img.shields.io/badge/-MS%20PowerPoint-B7472A?logo=Microsoft%20PowerPoint" alt="MS PowerPoint" align="left"></br>
</p>

Microsoft PowerPointで「°」をそれっぽく入力する方法について。

## そもそも: MS Wordの場合
MS Wordで記号を入力するには，ここで`ど`を変換して`°`とした後，Times New RomanやArialなどの欧文フォントを指定してやればSI単位等と同じ欧文フォントで入力できます。
![MS Wordの場合](https://user-images.githubusercontent.com/68371029/226357385-0d2edee8-aae5-42a7-8de3-12a6cd6a6e58.gif)

## PowerPointの場合
PowerPointでも同じように欧文フォントで記号の入力が可能ですが，Degree Signだけうまくいきません。
角度のときはそこまで気にならないような気がしますが，右揃えや温度°Cなど後ろに文字が続く場合は目立ちます。  
欧文フォントを設定しても実際にはこんな風に和文フォントのまま変わりません。
![PowerPointでDegree Signを入力](https://user-images.githubusercontent.com/68371029/226348473-dcd4d6fe-1340-4979-a6f7-ba95d2e781b9.png)

WordにしてもPowerPointにしても［挿入 / 記号と特殊文字パッド］から入力することができますが，ここで欧文フォントを指定してもPowerPointではうまくいきません。
![記号と特殊記号](https://user-images.githubusercontent.com/68371029/226348477-33d46472-0a3a-4096-b4f9-d571e10c1f9f.png)

## 応急的対処法
メイリオかMeiryo UIを設定してあげるとあまり悪目立ちしない雰囲気になります（若干でかい気がしますが…）。

![Meiryo UIで入力したDegree Sign](https://user-images.githubusercontent.com/68371029/226361238-d1e463b7-d3aa-4abd-a193-54387f1cc7b2.png)

ここでArialを指定してやっても，同様に見かけ上Arialなどになりますが，文字は変化しない。

Wordで入力できるので当然ですが，ArialのDegree Sign自体はあるはずなのに…入力できない。
![ArialのDegree Sign](https://user-images.githubusercontent.com/68371029/226348481-4058733a-29d7-48b0-8bfb-daec414751cb.png)

Wordで入力しておいてからコピーしてもだめ（和文フォントになる）。  
これバグなんですかね。

海外のページだと記号パッドなり文字コードなりで同じように入力しているんですが，日本語環境特有の問題なのか？謎は深まるばかり。

同様にPowerPointでDegree Signを入力できる欧文フォントとしてはMeiryo UI以外にもVerdanaやTahomaがあるようです。
共通点は，Matthew Carter…？

{{< blog-card "https://qualityoflife.link/2161.html" >}}

{{< blog-card "https://en.wikipedia.org/wiki/Matthew_Carter" >}}

それぞれのフォントでやってみるとこんな感じ。
![各フォントのDegree Sign比較](https://user-images.githubusercontent.com/68371029/226365906-91abd0ac-f1f0-44c8-960e-69dc1eaf1364.png)

Verdanaは`I`と`l`の表現等，視認性が良いので一時期多用していたんですが，ちょっとクセがあります。
メイリオ（Meiryo UI）もTahomaも兄弟みたいなもので，やっぱりちょっとクセあります。

いずれにしてもMS Pゴシックのままよりはマシです。  
あと，セリフ体を入れたいときはどうすれば…（Degree Signならサンセリフでもバレない？）

ちょっとギークですが，メイリオはベースラインがずれる問題があるので，個人的にはあまり好みません。。

{{< blog-card "https://zenn.dev/ken7253/articles/mairyo-with-uipart" >}}

でも仕方ないのでとりあえず渡邉はこれで騙し騙し入力しています。  
末端がないDegree Signだからぎりぎり許容できますが…  
Beamerに乗り換えるか？

良い方法があれば誰か教えてください…
