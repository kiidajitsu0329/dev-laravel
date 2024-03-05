# laravel開発開始用
laravelをdockerで開発する際に使用

## 環境
- nginx
- Laravel(PHP)
- MySQL
- phpMyAdmin

# 環境構築流れ
- ## プル
  - ローカル環境にこのディレクトリをプルする
- ## dockerでlaravel環境の構築(「」内はコマンドラインに打ち込むコマンド)
  - ターミナルを開いてcd でディレクトリに移動
  - 「docker-compose up -d」でdocker環境を構築する
  - 「docker exec -it test_php bash」でコンテナに入る
  - 「composer create-project --prefer-dist "laravel/laravel=9.*" .」でlaravelプロジェクトを立ち上げる
- ## プレビュー
  - http://localhost
  - http://localhost:8888
