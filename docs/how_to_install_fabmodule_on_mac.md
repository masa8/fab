fabmoduleでModela MDX-15を使う
==============================

環境
----
 * OS: Mac OSX Version 10.9.3
 * USBtoRS232ケーブル: [StarTechUSB to RS232 DB9 Serial Adapter Cable M/M (ICUSB232)](http://www.amazon.com/StarTech-RS232-Serial-Adapter-Cable/dp/B000067SNB/ref=sr_1_16?s=electronics&ie=UTF8&qid=1401599135&sr=1-16&keywords=star+tech+serial)


fabmoduleのインストール
-----------------------
1. [Fab Moduleサイト(mit.edu)](http://kokompe.cba.mit.edu/downloads.html)で手順を確認する
2. XCode をAppStoreからインストールする[(参考)](https://itunes.apple.com/jp/app/xcode/id497799835?mt=12)
3. Command Line Tools for XCode をインストールする[(参考)](http://qiita.com/3yatsu/items/47470091277d46f3fde2)
4. Homebrewをインストール[(参考)](http://qiita.com/b4b4r07/items/6efebc2f3d1cbbd393fc)
5. Applications -> Utilities -> Terminal をクリックしターミナルを起動する
6. brew install boost cmake libpng giflib　とタイプしfabmoduleの作成に必要なライブラリをインストールする
7. wxPythonをダウンロードするため、http://www.wxpython.org/download.php にアクセスする
8. wxPython3.0-osx-cocoa-py2.7 をクリックする
9. wxPython3.0-osx-3.0.0.0-cocoa-py2.7.dmgをクリックする
10. wxPython3.0-osx-cocoa-py2.7.pkgをクリックする
11. インストーラの指示通りにインストールする
12. http://kokompe.cba.mit.edu/downloads.html にアクセスする
13. downloadリンクをクリックしfabmoduleのソースコードをダウンロードする
14. ダウンロードしたfab_srcフォルダをホームディレクトリ(/Users/<your home>)に移動する
15. Applications -> Utilities -> Terminal をクリックする
16. cd fab_src とタイプしfab_srcフォルダに移動する
17. make fab とタイプしエンターしfabmoduleを作成する
18. make install　とタイプしfabmoduleをインストールする
19. fab とタイプし、ウインドウが表示されアプリが起動することを確認する


Note: Step2,3は既に私のマシンにインストール済みでしたので参考サイトのリンクのみ記載しました

Modela接続準備
--------------
1. http://www.startech.com/Downloads を開く
2. EnterProductIDに ICUSB232V2 とタイプしSerchボタンをクリックする
3. 表示される[サイト](http://www.startech.com/Cards-Adapters/Serial-Cards-Adapters/USB-to-RS232-Serial-Adapter-Cable~ICUSB232V2#dnlds)を確認する
4. Prolific_PL2303.zip をクリックしダウンロードする
5. Prolific_PL2303/Mac/Mac OS 10.6_10.7/PL2303_1.4.0.dmg をクリックする
6. PL2303_1.4.0をクリックしインストーラの指示通りにインストールする
7. macを再起動する
8. Modela MDX-15とmacをUSBtoSerialで接続する
9. Applications -> Utilities -> Terminal をクリックする
10. ls /dev/tty.usb* とタイプし　/dev/tty.usbserialと表示されることを確認する
11. sudo easy_install pip とタイプしpythonのパッケージ管理システムをインストールする
12. sudo pip install pyserialとタイプしpythonのserialパッケージをインストールする
13. /usr/local/bin/rml_send_gui　というテキストファイルの中の*/dev/ttyUSB0*と記載されている箇所を*/dev/tty.usbserial*にすべて変更する
14. /usr/local/bin/fab_sendというテキストファイルの中の*/dev/ttyUSB0*と記載されている箇所*/dev/tty.usbserial*に変更する
 
fabmoduleでModelaMDX-15を動かす
-------------------------------
1. ターミナルでfabとタイプしfabmoduleを起動する
2. [こちらのサイト(qiita.com)](http://qiita.com/mio_k/items/231fec28b5491345e469)を参考に動かす
 
