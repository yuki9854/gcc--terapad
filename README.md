# gccとterapadによるc言語開発環境の設定

## terapadを`tp ファイル名`で起動できるようにする

### "terapad.exe"を"tp.exe"へ名前変更

まず，スタートメニューからTrapadを右クリック→その他→ファイルの場所を開く

![スクリーンショット (58)](https://user-images.githubusercontent.com/72436563/118346648-f5880580-b577-11eb-8b51-2d9155cb5e99.png)

terapadのショートカットを右クリックし，プロパティを開く

![スクリーンショット (59)](https://user-images.githubusercontent.com/72436563/118346824-32a0c780-b579-11eb-9849-9143a5bd1386.png)

反転して青くなっているリンク先から，最後の`￥Terapad.exe`を消去してコピーし，エクスプローラーの検索欄に貼り付ける

![スクリーンショット (60)](https://user-images.githubusercontent.com/72436563/118346907-020d5d80-b57a-11eb-9c87-f6dcece4ce47.png)
![スクリーンショット (71)](https://user-images.githubusercontent.com/72436563/118346937-4ac51680-b57a-11eb-9eae-47cb28beb20c.png)

`TraPad.exe`を右クリックし，コピーする．

![スクリーンショット (65)](https://user-images.githubusercontent.com/72436563/118346975-94adfc80-b57a-11eb-9820-0de3b780fcc2.png)

同じフォルダ内に貼り付け("管理者の権限が必要です"とでるが，続行を選択)

![スクリーンショット (66)](https://user-images.githubusercontent.com/72436563/118346979-9bd50a80-b57a-11eb-8196-e2bed4af7be7.png)

エクスプローラーの表示タブを開き，

![スクリーンショット (74)_LI](https://user-images.githubusercontent.com/72436563/118347132-bcea2b00-b57b-11eb-83e0-b4f34c43cc9b.jpg)

ファイル名拡張子にチェック

![スクリーンショット (73)](https://user-images.githubusercontent.com/72436563/118347159-edca6000-b57b-11eb-8db1-7c1d3e0cd2df.png)

`TeraPad - コピー.exe`を右クリックし，名前を`tp.exe`に変更

![スクリーンショット (67)](https://user-images.githubusercontent.com/72436563/118347036-0be39080-b57b-11eb-9ab3-a42ec2fa62a9.png)

### Pathに追加
コマンドプロンプトでどのフォルダにいてもコマンド`tp ファイル名`が使えるようにする．
<br><br>
設定を開き，検索バーに"環境"と入力し"環境変数を編集"をクリック

![スクリーンショット (61)](https://user-images.githubusercontent.com/72436563/118347583-5ff07400-b57f-11eb-9de5-dd4511c0bbbc.png)

上の枠内の"Path"を選択し，`編集(E)...`をクリック

![スクリーンショット (62)](https://user-images.githubusercontent.com/72436563/118347664-e6a55100-b57f-11eb-9e01-88489b54a3ce.png)

`新規(N)`をクリックし，先ほど`￥Terapad.exe`を消去してコピーしたパスを貼り付ける.<br>
(`Windousキー　＋　V`で探してください．私の場合は`C:\Program Files (x86)\TeraPad`です)

![スクリーンショット (64)](https://user-images.githubusercontent.com/72436563/118347925-a941c300-b581-11eb-8515-66a370f57485.png)

すべてOKを押して終了です．  
コマンドプロンプトを開いて`tp + Enter`とうってterapadが起動したら成功です．

## gccコマンドを使いやすくする
gccコンパイラは仕様としてコンパイルしたときにできるファイル名が`a.exe`になる．ファイル名を指定するときは`gcc -o コンパイル後の実行ファイル(exe)名 コンパイルするファイル名(c)`というコマンドを打たなければならず少しbcc32cよりも使いにくい．そこで，バッチファイルをつかって上のコマンドを短縮することができる．

### "gccc.bat"を作成

まず、エクスプローラーを開いて`C:\`に移動する

![image](https://user-images.githubusercontent.com/72436563/118348789-93370100-b587-11eb-8468-69f9d023e1fc.png)

そこで空白部分を右クリック→新規作成→フォルダーでフォルダを新しく作る

![スクリーンショット (77)](https://user-images.githubusercontent.com/72436563/118348848-e27d3180-b587-11eb-8e00-92bd952dc877.png)

![スクリーンショット (78)](https://user-images.githubusercontent.com/72436563/118348857-017bc380-b588-11eb-8bea-70a6fbd342c3.png)

名前は"bin"にする

![スクリーンショット (79)](https://user-images.githubusercontent.com/72436563/118348872-16585700-b588-11eb-872a-acf46b2083dc.png)

フォルダを開いて，右クリック→新規作成→テキストドキュメントでテキストファイルを作成する

![スクリーンショット (80)](https://user-images.githubusercontent.com/72436563/118348912-4bfd4000-b588-11eb-8d2d-a752b89ee391.png)

名前を`gccc.txt`に変更する<br>
この名前はなんでもいいですが，**分かりやすい名前**で**短い**ほうがいいです<br>
"gccc.txt"以外に変えた場合は"gccc"をその名前に読み替えてください

![スクリーンショット (83)](https://user-images.githubusercontent.com/72436563/118348943-823abf80-b588-11eb-9f23-0df4ecb3037d.png)

開いて以下の文字列を入力する
```
@echo off
gcc -o %1 %1.c
```

![スクリーンショット (85)](https://user-images.githubusercontent.com/72436563/118348961-a3031500-b588-11eb-944b-3ef72e2a1255.png)

ファイルタブ→名前を付けて保存(A)

![スクリーンショット (86)](https://user-images.githubusercontent.com/72436563/118348989-d0e85980-b588-11eb-9a60-f0c0239b55de.png)

拡張子を".txt"から".bat"に変更して保存する

![スクリーンショット (88)](https://user-images.githubusercontent.com/72436563/118349011-fd03da80-b588-11eb-8374-6abe3e05ff2b.png)

### Pathの設定

検索バーをクリックし，`C:\bin`か下の画像のようになっていて，"gccc.bat"が入っていることを確認し(入ってなかったらここへ移動)，このパス`C:\bin`をコピー

![スクリーンショット (91)](https://user-images.githubusercontent.com/72436563/118349069-6edc2400-b589-11eb-9a36-5786eae74988.png)

さっきのように 環境変数の編集→Pathを選択して編集で下の画像までくる<br>
そして、下のように新規をクリックしてさっきコピーしたPath`C:\bin`を追加する<br>

![スクリーンショット (92)](https://user-images.githubusercontent.com/72436563/118349154-f3c73d80-b589-11eb-909e-67f0c1e9b563.png)

すべて"OK"を押して終了<br>
コマンドの指定方法は，下のコマンドように".c"をぬいたファイル名をつかいます
```
gccc ex02-01
```
コマンドプロンプトを開き，なにかコンパイルしてみてください
