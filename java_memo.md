# Java基本的な知識

## Javaのルール
* 語尾に「;」をつける

## 変数の定義の仕方
```java
型名　変数名;
```
変数の型を宣言→変数を使用できるようになる

## 型推論
```java
var 変数名 = 値
```
値の種類によってデータ型が推論され、推論されたデータ型で宣言が行われる

```java
System.out.println(((Object)変数名).getClass().getSimpleName());
```
上記の記述で型推論で選択された型を確認することができる


## 出力の方法

```java
 System.out.println();
```

##　演算子
Rubyで学習した演算子と同じである
### 代数演算子の種類

| 演算子 | 使い方 | 意味 |
| :---: | :---: | :---: |
| + | a + b | 加算 |
| - | a - b | 減算 |
| *	| a * b | 乗算 |
| / | a / b | 除算 |
| % | a % b | 剰余 |

### 比較演算子の種類

| 演算子 | 使い方 | 意味 |
| :---: | :---: | :---: |
| == | a == b | aとbが等しい場合true |
| < | a < b | aがbより小さい場合true |
| > | a > b | aがbより大きい場合true |
| <= | a <= b | aがb以下の場合true |
| >= | a >= b | aがb以上の場合true |
| != | a!= b | aとbが等しくない場合true |

## Javaの配列
Rubyの配列との違い
* 格納する要素の数を最初に決める必要がある
* 後で要素数を変更することができない
要素を増やす場合
* サイズの大きな配列を新たに作成して元データをコピーする
* ArrayListというリストの一種を使用する

### 配列の使い方
1. 配列の宣言を行う
2. 配列の要素を作成し、配列に代入する
3. 配列の要素に値を代入する
```
class Main {
  public static void main(String[] args) {
    int[] scores;　　　　　　　　　　　　　　　　　　　　　　　　　　　←１
    scores = new int[3];　　　　　　　　　　　　　←２

    scores[0] = 1;　　　　　　　　　　　　　　　　　　　　　　　　　←３
    scores[1] = 5;　　　　　　　　　　　　　　　　　　　　　　　　　←３
    scores[2] = 10;　　　　　　　　　　　　　　　　　　　　　　　←３

    System.out.println(scores[0]);
    System.out.println(scores[1]);
    System.out.println(scores[2]);
  }
}
```
### 配列の宣言方法
三種類あります。
```
int[] scores;
scores = new int[3];
```

1.配列の宣言と同時に、要素の作成も行う方法
```
int[] scores = new int[3];
```
2.配列の宣言時に型推論を使用する方法
```
var scores = new int[3];
```
int型の要素３つを代入することで、scoresはそれらを格納する配列であることが推論されています。

3.配列の宣言から値の代入まで全て同時に行う方法
配列の宣言時に代入する値が確定している場合のみ使える
```
int[] scores = {1, 5, 10};
```

### ArrayList
ArrayListとは？‥「可変長配列」を使用するための仕組みです。可変長配列とは、文字通り長さ（要素数）を変更できる配列のことです。
1.ライブラリをインポートする
```
import java.util.ArrayList;
```
2.ArrayListの宣言を行う
ArrayListの宣言と初期化は以下のように行います
```
ArrayList<データ型> scores = new ArrayList<データ型>();
```
下記のコードにでは以下のように記述
```
ArrayList<Integer> scores = new ArrayList<Integer>();
```
① 整数（Integer）を格納するArrayListを「score」という名称で宣言
② ArrayListの要素を作成

なお、要素のデータ型を右辺でも指定していますが、これは省略することが可能です。
```
ArrayList<Integer> scores = new ArrayList<>();
```
3.ArrayListに値を代入する
ArrayListに要素を追加するためにはaddメソッドを使用します。
記述は、add(要素として追加する値)のように行います。
先ほど実行した以下のコードでは、scoresという名称のArrayListに「1」を追加しました。
要素はArrayListの末尾に追加されます。
```
scores.add(1);
```
4.ArrayListから要素を取り出す
要素を取り出す際は、getメソッドを使用します。
記述は、get(取得したい要素のインデックス） のように行います。配列から要素を取り出す際と同様に、「1番目」の要素を取り出したい時は、インデックスとして「0」を指定します。
先ほど実行した以下のコードでは、scoresから、1番目の要素を取得しています。
```
scores.get(0)
```

```
import java.util.ArrayList;

class Main {
  public static void main(String[] args) {
    ArrayList<Integer> scores = new ArrayList<Integer>();

    scores.add(1);
    scores.add(5);
    scores.add(10);
    scores.add(15);

    System.out.println(scores.get(0));
    System.out.println(scores.get(1));
    System.out.println(scores.get(2));
    System.out.println(scores.get(3));
  }
}
```
