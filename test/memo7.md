# ハードウェア
システムを構成する２大要素「ソフトウェア」「ハードウェア」のうちの「ハードウェア」について。そのハードウェアの中で最も重要なのは「半導体メモリ」

# 半導体と半導体メモリ
* 半導体とは‥電気を通す「導体」と電気を通さない「絶縁体」の中間の性質を持つ物質。半導体は温度を変えたり、不純物を加えたりすることで、電気抵抗が変化する。
* 半導体メモリとは‥半導体の性質を利用してデータを保存する装置。電気を使ってデータを保存する記憶装置の部品として使われている
* 記憶装置にデータを保存する方法‥磁気（HDDなど）や光（CD、DVDなど）、電気（USBメモリなど）がある
## 半導体メモリの種類
「RAM」「ROM」「DRAM」「SRAM」「SDRAM」「フラッシュ」の６種類が試験で頻出
## RAMとROMの違い
* RAM（ラム：Random Acsess Memory）とは‥揮発性メモリのこと。ここでいう揮発性とは電源が切れるとデータが消滅してしまう半導体メモリのこと。（主記憶装置やキャッシュメモリはRAMに分類されるDRAMやSRAMを用いた記憶装置）
* ROM（ロム：Read Only Memory）とは‥不揮発性メモリのこと。電源を切ってもデータが保持される半導体メモリのこと。
## RAMの種類
DRAMとSRAMがある
* リフレッシュとは‥データが消えないように１秒間に何度も繰り返し電荷を加えること。
### DRAM* リフレッシュとは‥データが消えないように１秒間に何度も繰り返し電荷を加えること。
* DRAM（ディラム：Dynamic RAM）とは‥<br>絶えずリフレッシュを繰り返しているRAM。主に主記憶装置（メインメモリ）で使用される半導体メモリ。DRAMに蓄えられる電化はものすごく小さいので常にリフレッシュをしていないとデータが消えてしまうが、回路が単純で小さいので安価で製造することができる。
* SDRAM（Synchronous DRAM)とは‥クロックと同期して動作する半導体メモリ。Synchronousとは同期という意味。
### SRAM
* SRAMとは‥リフレッシュする必要がないRAM。主にキャッシュメモリで使用されている。リフレッシュが不要であるため非常に高速に動作するが高価である。
## ROMの種類
いくつかあるがフラッシュメモリが頻出である
### フラッシュメモリ
* フラッシュメモリとは‥電気的にデータの書き換えができるROM。「SSD」「USBメモリ」の中身で使用されている。
* フラッシュメモリの仕組み‥「ページ」と呼ばれる、ビットをひとまとめにした単位でデータの読み書きを行う。またデータの消去は「ブロック」と呼ばれるページをひとまとめにした単位

# 電子回路
「DRAM」や「SRAM」を構成している電子部品に関する知識が出題されるので、DRAMには「コンデンサ」、SRAMには「フリップフロップ回路」という部品が使われているなどその辺りを重点的に学習する必要がある
## メモリセル
* メモリセルとは‥半導体メモリの中で「０」または「１」という情報を保存する入れ物。半導体メモリの構造における最小単位であり、別の言い方をすると「半導体メモリは無数の、メモリセルによって構成されている」という
## コンデンサ
主記憶装置に使われることが多いDRAMはメモリセルがコンデンサで作られている（メモリセルの中にコンデンサが１つずつ入っている）
## フリップフロップ回路
キャッシュメモリに使われることが多いSRAMは、メモリセルがフリップフロップ回路で作られている。
* フリップフロップ回路とは‥１ビットの情報（０または１）を保存できる順序回路。特徴は電圧を保持し続けられる点である。コンデンサのように頻繁にリフレッシュする必要がなく、高速に動作するので、処理速度を求められるキャッシュメモリに採用されている
* 順序回路とは‥現在の入力だけでなく、過去の入力によって出力が決まる論理回路（論理演算を行う電子部品）
### コンデンサとフリップフロップ回路の違い

| 回路 | 半導体メモリ | 用途 | 価格 | リフレッシュ |
| :---: | :---: | :---: | :---: | :---: |
| コンデンサ | DRAM | 主記憶装置 | 安い | 必要 |
| フリップフロップ回路 | SRAM | キャッシュメモリ | 高い | 不要 |

## その他のハードウェア関連の用語
* チャタリングとは‥機械式スイッチのオン/オフが切り替わる短い間に、意図しないオン/オフが繰り返される現象。例えばマウスを一度しかクリックしていないのにダブルクリックと認識されたりするような現状のこと
* ７セグメントLEDとは‥８個のLEDを組み合わせて数字を表現するディスプレイ。７つのLEDで数字を表しますが、小数点を表すドットのLEDもあるので、LEDは合計で８つある。
#### ７セグメントLEDの種類
| 名前 | 解説 |
| :---: | :---: |
| アノードコモン型 | ポート（接続口）から出力される電圧が低い時に光る |
| カソードコモン型 | ポート（接続口）から出力される電圧が高い時に光る |