# MongoDBのインストールとクイックスタート

## UbuntuへMongoDBをインストールする

[MongoDB公式ドキュメント](http://docs.mongodb.org/manual/tutorial/install-mongodb-on-ubuntu/)

### 公開鍵をapt-getに登録

````
sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv 7F0CEB10
````

### mongodb.listを作成する

```
echo 'deb http://downloads-distro.mongodb.org/repo/ubuntu-upstart dist 10gen' | sudo tee /etc/apt/sources.list.d/mongodb.list
```

### apt-getのリポジトリ情報をアップデート

```
sudo apt-get update
```

### MongoDBのインストール
安定版をインストールする場合は
```
sudo apt-get install mongodb-org
```

## MongoDBの起動

### MongoDBのデーモンを動かす

```
sudo /etc/init.d/mongod start
```

### MongoDBが動作しているかを確認する
mongodbのログを読むことで確認できる

```
tail -f /var/log/mongod.log
```

### MongoDBのデーモンを停止する

```
sudo /etc/init.d/mongod stop
```

### MongoDBを再起動する

```
sudo /etc/init.d/mongod restart
```

[具体的な使い方を解説している公式ページ](http://docs.mongodb.org/manual/tutorial/getting-started/)
