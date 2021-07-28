# modules_sample

Go Modulesのサンプル用に作成するリポジトリ（しばらくしたら削除予定）

# V2以降のinstallについて

Go1.17 からコマンドのインストールに対してgo installで行えるようになりますが、
cmd/gm/にコマンドのインストール用のmainを作成した場合のベストプラクティスが存在しないため、
このリポジトリで処理を行ってみる

このモジュールはテスト用に作成したものでV2をすでに発行しています。

V2にコマンドとしての役割を追加してみます。
その後V3で仕様変更を行って実行してみます。


# やっていくこと

- cmd/greet を作成
- installが可能な状態にする
- v3 を作成
- v2,v3でコマンドを作成できるようにする

*V1.17rc1を利用すること*

# いままでやったこと

- 初期の挙動(ローカル)

$ go install github.com/secondarykey/modules_sample/cmd/greet

ローカルで実行するとgo.modを読んでくれて実行し、GOBINにgreetが作成されます。

- リモートで実行

$ go install github.com/secondarykey/modules_sample/cmd/greet

```
go install: version is required when current directory is not in a module
        Try 'go install github.com/secondarykey/modules_sample/cmd/greet@latest' to install the latest version
```

バージョン指定を行っていない為エラーになる

$ go install github.com/secondarykey/modules_sample/cmd/greet@latest

```
go: downloading github.com/secondarykey/modules_sample v1.12.0
go: downloading github.com/secondarykey/modules_sample v2.0.0+incompatible
go install: github.com/secondarykey/modules_sample/cmd/greet@latest: module github.com/secondarykey/modules_sample@latest found (v2.0.0+incompatible), but does not contain package github.com/secondarykey/modules_sample/cmd/greet
```

エラーになる。V1に存在しない為、当然(エラーでわかる)

$ go install github.com/secondarykey/modules_sample/cmd/greet@master

masterブランチを指定するとOKになる

- V2.1.0を発行

この状態にしてgo.modにv2を指定。
実行側をv2を指定して実行してみます。



- v2にする

- @latestにする

- v2ディレクトリを作成
