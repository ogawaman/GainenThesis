# GainenThesis

## ローカルで編集する方法
一番最初だけダウンロードしてくる必要がある
- git clone git@github.com:ktakeda0204/GainenThesis.git
-- これでローカルにGainenThesisというフォルダができ、編集することができる。
-- git に鍵認証しておく必要がある。https://github.com/settings/keysa
-- それをローカルの ~/.ssh/に置く
-- そして以下を実行する
--- eval `ssh-agent`; ssh-add ~/.ssh/<作った鍵の名前>
-- ダウンロードできなかったら上記を試した後、もう一回 git clone ~ をしてみる

次に編集の方法。
- TeXShopやらで普通に編集したい部分を編集して、main.texを開いてコンパイルが通ることを確認する。
- これだけでは変更がローカルに留まったままなので、リモートリポジトリに変更点を取り入れる必要がある。

使うコマンド。
- git add <変更したファイル1> <変更したファイル2> <・・・>
-- まず変更したファイルをリモートへと追加する前準備。

- git commit
-- こうすることでコミットメッセージ記入画面に切り替わるので、何を変更し追加したかを書く。
-- git add と git commit を終えれば作業の第一段階終了。

- git pull (慣れてきたら git remote updateと git merge --no-ff)
-- もしかしたら同じファイルを他のユーザーが変更しているかもしれない
-- このコマンドでいったん最新のリモートの状態を反映させる。これで第二段階終了。

- git push -u origin master:master
-- これでローカルの変更点をリモートへと追加できる。

## 各ファイルの説明
main.tex
- メインファイル。新しい章を追加するときは¥input{section/<新しい章>}の記述を記入する。

config/setting.tex
- 設定ファイル。新しい章を追加したときには¥graphicpath{}を記入例に倣って追記する。そうすれば、各章のtexファイルで画像を読み込むときは¥includegraphics{画像名}だけでコンパイルできる。

section/
- 各セクションに該当するdirectoryを置く。
