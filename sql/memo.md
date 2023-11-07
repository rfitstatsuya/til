# 用語
* SQL（Structured Query Language）・・データーベースを操作する言語。SequelProや`rails db:create`コマンドは最終的にSQLを使用している仕組みになっている。
* ORM（Object Relational　Mapping）・・RDB（リレーショナルデータベース）のデータを、オブジェクト指向プログラミング言語でオブジェクトとして使用するために変換する技術

# SQL
## 基本
* 小文字でも大文字でも起動するが、SQL文を読みやすくするために大文字で記述する
## SQLの命令
* データを定義するDDL（Data Definition Language）
  
| 命令	  | 機能 |
| ----- | ---------------------- |
|CREATE	|データベースやテーブルの作成 |
|ALTER	|データベースやテーブルの更新 |
|DROP	|データベースやテーブルの削除 |

* データを操作するDML（Data Manipulation Language）

| 命令	| 機能 |
| --- | --------- |
|INSERT	| データの登録 |
|UPDATE	| データの更新 |
|DELETE	| データの削除 |
|SELECT	| データの検索 |

* データを制御するDCL（Data Control Language）

| 命令	| 機能 |
| --- | --- |
| COMMIT |	DBの変更の確定 |
| ROLLBACK |	DBの変更の取り消し |
| GRANT	| ユーザーに操作権限を付与 |
| REVOKE	| ユーザーの操作権限を無効化 |

![image](https://github.com/rfitstatsuya/til/assets/142726441/d5ff7f30-663e-4fa3-a12f-cf9b22ec8493)

## SQLの使用方法
* SELECT文・・データベースからデータを取得する場合に使用する文
```
SELECT <取得したいデータ(カラム名)> FROM <テーブル名>;
```
テーブルに登録されているすべてのカラムのデータを取得したい場合
```
mysql> SELECT * FROM 《テーブル名》
```
*（ワイルドカード）・・「すべてのパターンにマッチするもの」という意味を持ち、文字の代わりとして使うことができる特殊な記号のひとつ。SELECT句においては、アスタリスク*が「すべてのカラム」という意味のワイルドカードとして定義されているため、すべてのデータを取得できる。
*****

* CREATE文・・データベースやテーブルを作成できるSQLの文。指定した名前のデーターベースを作成できる
```
mysql> CREATE DATABASE 《データベース名》;
```
```
mysql> CREATE TABLE　　《テーブル名（カラム名１　カラム名１の型, カラム名2　カラム名2の型）》;
```
* 型の指定
  
|型名 |	保存できる値 |
| -- | ---------- |
| INT |	数字 |
| VARCHAR(M) |	最大M文字の文字列 |
*****

* SHOW文・・データベースやテーブルを一覧表示できるSQLの文。作成したデーターベースを一覧で表示できる
```
mysql> SHOW DATABASES;
```
```
mysql> SHOW TABLES;
```
* テーブルの構造を表示する方法
```
mysql> SHOW columns FROM 《テーブル名》;
```
*****

* DROP文・・データベースやテーブルを削除できるSQLの文。指定した名前のデーターベースを削除できる
```
mysql> DROP DATABASE 《データベース名》;
```
*****

* USE文・・どのデータベースを使用するのかを指定するSQLの文。指定した名前のデーターベースを選択できる
```
mysql> USE 《データベース名》;
```
*****

* ALTER(オルター)文・・データベースやテーブルを編集できるSQLの文。テーブルに対してカラムの追加や削除できる
```
mysql> ALTER TABLE 《テーブル名》 操作;
```
カラムを追加する場合は以下の記述をする
```
mysql> ALTER TABLE テーブル名 ADD カラム名 カラムの型;
```

カラムを変更する場合は以下の記述をする
```
mysql> ALTER TABLE テーブル名 CHANGE 古いカラム名 新しいカラム名 新しいカラムの型;
```

カラムを削除する場合は以下の記述をする
```
mysql> ALTER TABLE テーブル名 DROP カラム名;
```

* INSERT文・・テーブルにデータを登録するためのSQL文。`INTO`という句と組み合わせて`INSERT INTO`として使用する。また、実際に設定する値は、`VALUES`という句の後に入力する。
**すべてのカラムに値を入れる場合**
```
mysql> INSERT INTO 《テーブル名》 VALUES(値1, 値2, 値3);
```
**特定のカラムのみに値を入れる場合**
```
mysql> INSERT INTO テーブル名(カラム名1, カラム名2) VALUES(値1, 値2);
```
*****

* UPDATE文・・データを更新するためのSQLの文。使用する際は、`SET`という句のあとに変更内容、`WHERE`という句のあとに条件を指定する。
```
mysql> UPDATE 《テーブル名》 SET 《変更内容》 WHERE 《条件》;
```
*****

* DELETE文・・データを削除するためのSQLの文。使用する際は、`FROM`句を、条件を指定するために`WHERE`句をあわせて使用する。
```
mysql> DELETE FROM 《テーブル名》 WHERE 《条件》;
```
*****

## SQLの使用
**ターミナル**
```
# MySQLに接続
% mysql -u root
```
