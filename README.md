# GainenThesis

main.tex
- メインファイル。新しい章を追加するときは¥input{section/<新しい章>}の記述を記入する。

config/setting.tex
- 設定ファイル。新しい章を追加したときには¥graphicpath{}を記入例に倣って追記する。そうすれば、各章のtexファイルで画像を読み込むときは¥includegraphics{画像名}だけでコンパイルできる。

section/
- 各セクションに該当するdirectoryを置く。
