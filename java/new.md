# 新規アプリ作成
## 作成の流れ
1. プロジェクトファイルの作成（https://start.spring.io/）
2. 作成したファイルを解凍してファイルを移動。
3. intellijで「build.gradle」ファイルをプロジェクトとして開く
4. データーベースを準備する
mysqlを起動する
```
mysql -u root
```
テーブルを作成
```
mysql> create database issue_app;
mysql> exit;
```
5. アプリケーションとデーターベースを接続する
src/main/resources/application.properties
```
spring.sql.init.mode=always
spring.datasource.driverClassName=com.mysql.cj.jdbc.Driver
spring.datasource.url=jdbc:mysql://localhost:3306/issue_app
spring.datasource.username=root
spring.datasource.password=
```
6. schema.sqlの設定
アプリの起動時に、データベースのテーブルが作成される設定を行う。
* ファイルの作成（src/main/resourcesにschema.sqlという名前のファイルを作成する）
```
CREATE TABLE IF NOT EXISTS issues (
    id BIGINT NOT NULL PRIMARY KEY AUTO_INCREMENT,
    title VARCHAR(256) NOT NULL,
    content VARCHAR(256) NOT NULL,
    period VARCHAR(256) NOT NULL,
    importance VARCHAR(256) NOT NULL
);
```
