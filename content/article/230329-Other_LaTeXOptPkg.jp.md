---
title: "追加で導入しているLaTeXパッケージ（備忘録）"
date: 2023-03-29T13:00:00+01:00
draft: false
summary: "LaTeXに追加で導入しているパッケージの一覧"
showDate: true
excludeFromIndex: false
categories: ["Other"]
icon: "fa-lightbulb"
tags: ["LaTeX","備忘録"]
---

![TeX Live 2023](https://user-images.githubusercontent.com/68371029/228538440-d1f8006c-92ca-4ec8-a12d-637c08519078.png)

TeX Live 2023がリリースされ，TeX Live Managerが文句を吐くようになったのでアップデートしました。  
毎年のことなので以下メモです
（新規のインストールも同じ手順です）。

1. TeX Liveインストーラーを**管理者権限で起動**し，`Advanced`を選択
1. `Scheme`を`basic scheme (plain and latex)`に変更
1. `Customize`から  
`Lunguages`で`Japanese`を追加  
`Other collections`で`LaTeX recommended packages`を追加

VS Codeで使うのでTeX Worksは入れない

ちなみにTeX Live 2023でこのセッティングだと~1.3 GBです。

![TeX Live Installer](https://user-images.githubusercontent.com/68371029/228535698-b342120a-6a0e-4693-abe2-f5e8dce389b9.png)

![Collections](https://user-images.githubusercontent.com/68371029/228535622-4b0774c4-22e3-454b-93a4-b347cdeb330a.png)

インストール終了後，コマンドプロンプトを管理者権限で起動し，`tlmgr install`で以下のパッケージを入れる。
```log
C:\texlive\2023\texmf-var\web2c\tlmgr.log
[Tue Mar 28 16:25:01 2023] install: adjustbox
[Tue Mar 28 16:25:03 2023] install: collectbox
[Tue Mar 28 16:25:35 2023] install: here
[Tue Mar 28 16:26:38 2023] install: tcolorbox
[Tue Mar 28 16:27:33 2023] install: environ
[Tue Mar 28 16:27:34 2023] install: trimspaces
[Wed Mar 29 13:22:50 2023] install: beamertheme-metropolis
[Wed Mar 29 13:24:34 2023] install: pgfopts
[Wed Mar 29 13:26:11 2023] install: siunitx
[Wed Mar 29 13:28:42 2023] install: helvetic
[Wed Mar 29 13:29:40 2023] install: biblatex
[Wed Mar 29 13:29:41 2023] install: logreq
[Wed Mar 29 13:41:22 2023] install: biber.windows
[Wed Mar 29 13:41:23 2023] install: biber
```
`biber.windows`は`biber`と一緒に勝手に入ります。

`beamerthememetropolis.sty`ですが，`beamertheme-metropolis`と入れてやらないとうまく見つからないので注意。

困ったら`tlmgr info`で名前を探す。
![tlmgr info](https://user-images.githubusercontent.com/68371029/228539814-d62e5293-cd96-41a7-86c0-8fc17d4942eb.png)

<iframe class="hatenablogcard" style="width:100%;height:155px;max-width:680px;" title="TeX Live - TeX Users Group" src="https://hatenablog-parts.com/embed?url=https://www.tug.org/texlive/" width="300" height="150" frameborder="0" scrolling="no"></iframe>