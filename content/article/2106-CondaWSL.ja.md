---
title: "メモ: WSLでcondaをインストール"
date: 2021-06-13T16:30:34+09:00
draft: false
summary: "WSLでcondaをインストールした際の備忘録"
excludeFromIndex: true
categories: ["Tips"]
---

# ことのアラマシ
FDTD法という電磁波シミュレーションしたい  
↓  
高額なソフトが必要  
↓  
MEEPというフリーソフトで可能  
↓  
MEEPはLinux or Mac環境でしか動作しないらしい…  

ということでLinux環境をWindows上に構築する必要が生じました。  
最近は便利なものでWindows Subsystem for Linux（WSL）というMicrosoft謹製ツールが配布されており，**手軽に**Linux環境が構築できるとのこと。  
~~いまにして思えばこれを鵜呑みにしたのが良くなかったような…~~

# 導入手順
導入自体は[MEEPの公式ドキュメント](https://meep.readthedocs.io/en/latest/Installation/)で説明されている。

まずはパッケージ管理ツールminicondaを導入する
```plaintext
wget https://repo.continuum.io/miniconda/Miniconda3-latest-Linux-x86_64.sh -O miniconda.sh
bash miniconda.sh -b -p <desired_prefix>
export PATH=<desired_prefix>/bin:$PATH
```
`conda`で`pymeep`を導入する。
```plaintext
conda create -n mp -c conda-forge pymeep
```

ところが，2手目の
```plaintext
bash miniconda.sh -b -p
```
がうまくいかなかった。  
```plaintext
OSError: [Errno 40] Too many levels of symbolic links:
```
原因がよくわからず2週間を費やした（さすがにこればっかりやってたわけじゃないけど…）。  

# 解決
調べても情報があまり出てこなくて時間を費やした。  
結局のところWSL上でAnacondaを入れようとしたときに発生する不具合のようだった（たぶん）。  
Githubで[タイムリーなissue](https://github.com/conda/conda/issues/10333#issuecomment-836803901)が立っていて，これを参考に解決に至った。

あとはこのissueに追記した通り。  
原因は
- `pkgs/ncurses-6.2-h58526e2_4/share/terminfo/N/ncr260vt300wpp`
- `pkgs/ncurses-6.2-h58526e2_4/share/terminfo/E/Eterm`

で，これらに含まれるリンクが良くないとのこと。  
[issue #10333 (comment)](https://github.com/conda/conda/issues/10333#issuecomment-836803901)では別途ncursesパッケージを[Anacondaのページ](https://anaconda.org/conda-forge/ncurses/files)から拾ってきて上記2ファイルを差し替えれば良いとのことだったが，これでは解消しなかった。  
渡邉の環境ではリンク先である
```plaintext
miniconda3/share/terminfo/N/ncr260vt300wpp
```
をコピーしてきて
```plaintext
pkgs/ncurses-6.2-h58526e2_4/share/terminfo/N/ncr260vt300wpp
```
を置き換えたところminicondaのインストールが成功した  
(`Eterm`のファイルサイズが違うぞって怒られたけど無視)。
