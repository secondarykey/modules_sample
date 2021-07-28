# modules_sample
Go Modulesのサンプル用に作成するリポジトリ（しばらくしたら削除予定）

# V2以降のinstallについて

Go1.17 からコマンドのインストールに対してgo installで行えるようになりますが、
cmd/gm/にコマンドのインストール用のmainを作成した場合のベストプラクティスが存在しないため、
このリポジトリで処理を行ってみる


# やっていくこと

- cmd/gm を作成
- installが可能な状態にする
- v3 を作成
- v2,v3でコマンドを作成できるようにする

*V1.17rc1を利用すること*

# いままでやったこと

- 初期の挙動(ローカル)

$ go install github.com/secondarykey/modules_sample/cmd/greet

ローカルで実行するとgo.modを読んでくれて実行し、GOBINにgreetが作成されます。

- リモートで実行

- v2にする

- @latestにする

- v2ディレクトリを作成
