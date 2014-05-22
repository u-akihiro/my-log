# RubyからMongoDBを利用する
公式ドライバ編

## 公式ドライバのインストール

一応、アップデートをかけてから
```
gem update --system
gem install mongo
```
これだけ。

## 実際に使ってみる

### requireしてあげる

```
require 'mongo'
```

### MongoDBに接続する

3通りの方法があるらしい
```
mongo_client = MongoClient.new
mongo_client = MongoClient.new 'localhost'
mongo_client = MongoClient.new 'localhost', 27017
```

### データベースを使用する

```
mongo_client = MongoClient.new
db = mongo_client.db 'mydb'
```

[Using a Database](https://github.com/mongodb/mongo-ruby-driver/wiki/Tutorial#using-a-database)

#### 認証
MongoDBにはセキュアモードというものがあるらしい。
セキュアモードに設定されているデータベースにアクセスするには、authenticateメソッドにて
認証をパスする必要がある。

```
mongo_client = MongoClient.new
db = mongo_client.db 'mydb'
db.authenticate user_name, password ←　これ
```

参考にしたページ  
[インストール方法を解説した公式ページ](http://docs.mongodb.org/ecosystem/drivers/ruby/)  
[mongoドライバ for rubyの解説](https://github.com/mongodb/mongo-ruby-driver/wiki/Tutorial)  
[Ruby Documentation](http://api.mongodb.org/ruby/current/index.html)
