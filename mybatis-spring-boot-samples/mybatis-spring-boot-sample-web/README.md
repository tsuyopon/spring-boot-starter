
# どうやってSQLは実行されているのか?
pom.xmlではH2 Databaseが組み込まれています。

この時、application.propertiesには以下の設定が組み込まれていないのでembeddedが指定されることになります。
```
# ALWAYS ： アプリ起動時に毎回実行
# EMBEDDED ： 埋込DB(H2 Database)の時のみ実行 (default)
# NEVER ： 実行しない
spring.datasource.initialization-mode=embedded
```

このとき、クラスパスが通っているディレクトリ src/main/resources/直下に
以下のファイル名を配置すると自動的に読み込む仕組みになっているようだ。
```
schema-(platform).sql
schema.sql
data-(platform).sql
data.sql
```

# How to Access


http://localhost:8080/cities/CA

```
{"id":1,"name":"San Francisco","state":"CA","country":"US"}
```