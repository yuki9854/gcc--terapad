# gccとterapadの連携環境の構築
## terapadを`tp ファイル名`で起動できるようにする

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

設定を開き，検索バーに"環境"と入力し"環境変数を編集"をクリック

![スクリーンショット (61)](https://user-images.githubusercontent.com/72436563/118347583-5ff07400-b57f-11eb-9de5-dd4511c0bbbc.png)

上の枠内の"Path"を選択し，`編集(E)...`をクリック

![スクリーンショット (62)](https://user-images.githubusercontent.com/72436563/118347664-e6a55100-b57f-11eb-9e01-88489b54a3ce.png)

`新規(N)`をクリックし，先ほど`￥Terapad.exe`を消去してコピーしたパスを貼り付ける.<br>
(`Windousキー　＋　V`で探してください．私の場合は`C:\Program Files (x86)\TeraPad`です)

![スクリーンショット (64)](https://user-images.githubusercontent.com/72436563/118347925-a941c300-b581-11eb-8515-66a370f57485.png)

すべてOKを押して終了です．  
コマンドプロンプトを開いて`tp + Enter`とうってterapadが起動したら成功です．

####
