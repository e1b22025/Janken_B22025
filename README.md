# 目次
- [セットアップマニュアル][label1] 
- [ユーザーマニュアル][label2]
- [実行方法][label3]
- [遊び方][label4]
- [その他][label5]
- [貢献者][label6]

[label1]: #セットアップマニュアル
# セットアップマニュアル
**サーバのアクセス**
1)bashを起動後、下記のsshコマンドで実行します。
```
$ ssh isdev24@[IPアドレス]
```
アクセスが完了するとメッセージが表示されます。
2)アクセスが出来たら以下のコマンドでsshアクセスログを確認します。
```
$ sudo cat /var/log/auth.log
```
コマンドを入力するとパスワードの入力を求められる。
**タイムゾーンの変更**
1)タイムゾーンを設定するためにtimedatecltコマンドのset-timezoneオプションを使用する．使用後timedatecleを利用し確認する．以下にコマンドを示す．
```
isdev24@ubuntuXXX:~$ sudo timedatectl set-timezone Asia/Tokyo
```
```
isdev24@ubuntuXXX:~$ timedatectl
```
**Javaのインストール**
1)次のコマンドを実行しJava Corretoをインストールする準備をする。
```
$ wget -O - https://apt.corretto.aws/corretto.key | sudo gpg --dearmor -o /usr/share/keyrings/corretto-keyring.gpg && echo "deb [signed-by=/usr/share/keyrings/corretto-keyring.gpg] https://apt.corretto.aws stable main" | sudo tee /etc/apt/sources.list.d/corretto.list

```
2)実行後、Press[ENTER] to countine or Ctrl-c to cancel.が表示さる。それ以降に進むにはENTERキーを押してください。
3)次に以下のaptコマンドを利用してインストールをする
```
$ sudo apt-get update; sudo apt-get install -y java-21-amazon-corretto-jdk
```
4)javaのインストールを確認するために以下のコマンドを実行する。
```
$ java -version
```
**Webアプリケーションの公開**
1)以下のコマンドでホームディレクトリに移動する。
```
$cd
```
2)移動後ホームディレクトリに移動できているかの確認を以下のコマンドで行う。
```
$pwd
```
3)ブラウザでGithubにアクセスし対象のリポジトリのURLをコピーする(git@github.com:Halto709/yonhaya.git)。そこ後以下のコマンドでクローンする。
```
$ git clone git@github.com:Halto709/yonhaya.git
```
4)リポジトリが正しくクローン出来たか確認するために以下のコマンドを実行する。
```
isdev24@ubuntuXXX:~$ ls
```
コマンドを実行すると**yonhaya**というリポジトリがあるか確認する。
5)以下のコマンドを利用しリポジトリを移動する。
```
$cd yonhaya
```
6)最後にプロジェクトの実行のために以下のコマンドを実行する。
```
$  bash ./gradlew bootrun
```
実行後、ブラウザで対象にURLにアクセスし確認する。

[label6]
[label6]: #author
# Author
Z2635
Z2722
Z2386
Z2444


