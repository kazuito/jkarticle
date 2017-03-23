# jkreport.sty
じょっこーのための卒論LaTeXスタイルファイル
version 1.0.3

## 概要
じょっこー用卒論表紙をLaTeXスタイルファイルとして実装しました．

Word，LaTeXそれぞれで表紙と本文のPDFを作成して連結させる必要がなくなります．


## インストール
texmf-local/texディレクトリに入れるか，あなたのレポート用.texファイルがあるディレクトリに入れてください．
texmf-localディレクトリについては，TeX Wikiの[この記事](https://texwiki.texjp.org/?TeX%20%E3%81%AE%E3%83%87%E3%82%A3%E3%83%AC%E3%82%AF%E3%83%88%E3%83%AA%E6%A7%8B%E6%88%90)に詳しく記載されています．
texmf-localディレクトリに入れることで，何回もjkarticle.styをコピーする必要はなくなりますが，mktexlsrコマンドを実行しなければLaTeXのコマンドに認識されないことに注意して下さい．

## 使い方
### 読み込ませる
`\documentclass{jsarticle}`などと`\begin{document}`の間(プリアンブル)に`\usepackage{jkarticle}`を挿入して下さい．PDF化することが大半だと思うので，`\usepackage[dvipdfmx]{graphicx}`を挿入しておけばOKです．

以下のようになればOKです．

```
\documentclass{jsarticle}
\usepackage{color,okumacro}
\usepackage[dvipdfmx]{graphicx}
\usepackage{jkarticle}

\begin{document}
〜本文〜
\end{document}
```

注意: `sample.tex`，`template.tex`では`\documentclass[uplatex]{jsarticle}`となっています．これは，upLaTeX をエンジンとして使用するためです．他のエンジン（pLaTeX，XeLaTeX など）を使用する場合は，適宜変更してください．

### 変数を設定する
jkarticle.styでは以下の項目をマクロで変数的に使えるようにしました．

- `\jatitle{タイトル（日本語）}`でタイトル（日本語）を設定します．
- `\entitle{タイトル（英語）}`でタイトル（英語）を設定します．
- `\jaauthor{著者名（日本語）}`で著者名（日本語）を設定します．
- `\enauthor{著者名（英語）}`で著者名（英語）を設定します．
- `\enteredyear{入学年度}`で入学した年度（西暦）を設定します．
- `\articleyear{提出年度}`で卒論を提出した年度（西暦）を設定します．
- `\studentid{学籍番号}`で学籍番号を設定します．
- `\professorname{指導教員名}`で指導教員の名前を設定します．
- `\professorsuffix{指導教員の職階}`で指導教員の職階を設定します．
- `\submittingdate{提出年月日}`で卒論を提出した年月日（和暦）を設定します．
- `\picture{PNG，JPEGなどの画像ファイル}`で著者の顔写真を設定します．

### 表紙を生成する
変数を設定したら，`\maketitle`で表紙ページを生成します．
その後はいつも通りに本文を書いていくだけです．
