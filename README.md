# PHPの開発環境を立ち上げるだけのdocker-composeリポジトリ

.env.sampleをコピーして.envを設置する

以下はそれぞれに合わせて設定する
```yaml
#ローカルIPをどれかユニークなものを指定する（他の開発環境と被らないように設定する）
WEB_IP=127.0.0.1

#開発サイトのホスト名を指定する（自身の開発ホストを決めて設定する）
HTTP_CONF_SERVER_NAME=hoge

#開発サイトのドキュメントルートを指定する（フレームワークの都合などに合わせて変更する）
HTTP_CONF_DOCUMENTROOT=/var/www/html/project_root/public

```

ssl関係のファイルを作成するコマンドを実行する
```bash
bash docker_config/web/create_ssl_files.sh
```

docker-composeの実行は以下のbashで行う
```bash
bash docker_compose_up.sh
```

設定したホスト名でアクセスする
```bash
https://hoge/
```
ブラウザの警告を消すには、ssl.crtをブラウザにインポートする

