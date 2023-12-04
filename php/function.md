# file_put_content
* データをファイルに書き込む

https://www.php.net/manual/ja/function.file-put-contents

#### 記述例：dataディレクトリにnews.txtというファイルを書き込む場合
```
<?php
$success = file_put_contents('data/news.txt', 'ホームページをリニューアルしました');

if($success !== false) {
  echo 'ファイルの書き込みが完了しました';
} else {
  echo 'ファイルの書き込みに失敗しました';
}
?>
```

# file_get_contents;
* 外部の指定したデータを読み込むことができる(読み込んだファイルを変換や加工したいときに使用する) 
### メリット：外部のファイルを読み込むことでプログラムを変更しなくてもそれを変更するだけですむ
#### 記述例：読み込んだファイルに追記をして出力する例
```
<?php
$news = file_get_contents('data/news.txt');
echo $news;

// ファイルの追記
$news = $news . '<br>追記のニュースです';
$success = file_put_contents('data/news.txt', $news);
?>
```

# readfile();
* 外部の指定したデータを読み込み出力することができる。
#### 記述例：読み込んだファイルを出力する例
```
<?php
readfile('data/news.txt');
?>
```

