# GainenThesis

## ローカルで編集する方法
編集の方法。
- TeXShopやらで普通に編集したい部分を普通に編集すればよい
- その後、main.texを開いてコンパイルが通ることを確認する。
  - これだけでは変更がローカルに留まったままなので、リモートリポジトリに変更点を取り入れる必要がある。

使うコマンド。
- git add <変更したファイル1> <変更したファイル2> <・・・>
- git commit -m "何らかのログメッセージを書く"
- git pull
  - もしかしたら同じファイルを他のユーザーが変更しているかもしれない
  - このコマンドでいったん最新のリモートの状態を反映させる。これで第二段階終了。
- git push -u origin develop:develop
  - これでローカルの変更点をリモートへと追加できる。
  - permission denied になったら、以下を試す
    - eval ``ssh-agent``
    - ssh-add ~/.ssh/GitHub_key

## 各ファイルの説明
main.tex
- メインファイル。新しい章を追加するときは¥input{section/<新しい章>}の記述を記入する。

config/setting.tex
- 設定ファイル。新しい章を追加したときには¥graphicpath{}を記入例に倣って追記する。そうすれば、各章のtexファイルで画像を読み込むときは¥includegraphics{画像名}だけでコンパイルできる。

section/
- 各セクションに該当するdirectoryを置く。
