# nestjs-trello-api

バックエンドの学習目的でnestjsを用いたAPIを実装



# 環境構築

パッケージ管理は`npm`、Node.jsはv18系を利用してください

```
- npm install
  - パッケージのインストール
- cp .env.sample .env
  - 環境変数のコピー
- docker-compose up -d
  - docker環境を立ち上げてMySQLコンテナの起動
- npm start
  - nestjs-apiの起動ができることを確認
```

# アーキテクチャ

ドメイン駆動設計 & オニオンアーキテクチャを採用しています。  
`ドメイン`ごとにオニオンアーキテクチャのレイヤーを表すディレクトリを定義しています。

```
- src/{ドメイン}
  - domain
  - usecase
    - オニオンアーキテクチャ上ではアプリケーションと呼ばれていますが、アプリケーションだと不明瞭となるのでユースケースと命名を置き換えています
  - presentation
    - controllerなどの入出力を担当  
  - infrastructure
    - RDBやS3などの具体的な技術実装
```


# コミットメッセージ規約

コミットメッセージの形式統一を目的として[Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/)を採用しています。
コミットする際は`git cz`コマンドを叩くと対話形式で`Conventional Commits`の規約通りにコミットを進めることができるので、こちらのコマンドで進めるようにしてください。

※ 仕組みとしてはpackage.jsonの依存関係に含まれている`git-cz`を利用しています。

