# my mastodon tips
公式ドキュメント: https://github.com/tootsuite/documentation   
さくらのmastodonスクリプト詳細: https://secure.sakura.ad.jp/vps/#/startupscripts/9bda5985-394f-4821-b455-c1f189c4f8b6 

## さくらvpsによるmastodonサーバ構築
1. さくらvpsを契約する。(現在はメモリ1GB、ストレージ50GBの契約)

2. 事前作業   
https://secure.sakura.ad.jp/vps/#/startupscripts/9bda5985-394f-4821-b455-c1f189c4f8b6   
↑に従って「ドメイン取得」、「逆引き設定」、「DNS設定」を実施する。

3. 環境構築   
サーバの各種設定→OSインストール→CentOS7を選択→スタートアップスクリプト(Mastodon)を選択→設定内容を確認 で環境構築実施。
20~30分ほどでブラウザからMastodonにアクセスできるようになる。

## Mastodonサーバ管理
1. 管理者アカウント作成   
事前に登録したアカウントに対し下記のコマンドで管理者権限を付与する。
```
su - mastodon
cd /home/mastodon/live/bin/
RAILS_ENV=production bundle exec bin/tootctl accounts modify 対象ユーザー名 --role admin
```
コマンド実行後、再ログインすると設定画面に「管理」項目が追加される。
