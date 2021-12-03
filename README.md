# ruby-practice

## 目的
- `プロを目指す人のためのRuby入門（伊藤淳一・技術評論社）`を一通り行うことによるRubyプログラミングに関する知識、技術の習熟

## 使用技術
- Docker(Ruby実行環境作成)
- Ruby 3.0.3

## 開発環境作成時に実行するコマンド
### Dockerによって環境を作るために実行したコマンド

```
$ docker run --name ruby -i -t -v `pwd`:/var/ruby -w /var/ruby ruby /bin/bash
```

- `ruby`イメージを使用
- ホストマシンの現在のディレクトリ(`~/ruby-practice`)をコンテナ内の`/var/ruby`にボリュームマウントすることでデータの永続化

### runコマンドで生成されたコンテナは、作業が一通り終わりコンテナ内から抜けたら削除
```
$ docker rm ruby
```

### 作業を再開するときにはまたdockerで環境を作成する
- コンテナを消しても、ボリュームマウントされているのでデータは永続化されている

```
$ docker run --name ruby -i -t -v `pwd`:/var/ruby -w /var/ruby ruby /bin/bash
```
