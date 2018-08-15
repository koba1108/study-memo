# study-memo

docker についてお勉強しているよ

## ざっくり
基本 `docker *****` でなんでもできる。

## よく使いそうやつ

1. nginx立ち上げ
```
docker run -d -p 80:80 --name webserver nginx
```

2. コンテナ確認
```
docker container ls -a
```

3. コンテナ停止
```
docker container stop webserver
```

4. コンテナ削除
```
docker container rm webserver
```
※ コンテナを停止してからじゃないと消せない `-f` つけるといけそう

## docker-compose ほにゃらら

1. yamlに `build:` があれば、そのイメージをまとめてビルド
```
docker-compose build
```
2. yaml に `image:` があれば、そのイメージをまとめてプル
```
docker-compose pull
```
3. docker-compose build, docker-compose pullをした後にdocker run
```
docker-compose up -d
```
4. 個別のサービスを指定することもできる。
```
docker-compose up -d redmine
```
※ 依存関係がある場合は関係するコンテナすべてが起動する

5. 関係するコンテナすべての出力を表示
```
docker-compose logs
```
6 関係するコンテナをまとめて終了
```
docker-compose stop
```
7. 関係するコンテナをまとめて削除
```
docker-compose rm
```
