fabmoduleでModela MDX-15を使う
==============================

環境
----
 * OS: Mac OSX Version 10.9.3
 * USBtoRS232ケーブル: [StarTechUSB to RS232 DB9 Serial Adapter Cable M/M (ICUSB232)](http://www.amazon.com/StarTech-RS232-Serial-Adapter-Cable/dp/B000067SNB/ref=sr_1_16?s=electronics&ie=UTF8&qid=1401599135&sr=1-16&keywords=star+tech+serial)


fabmoduleのインストール
-----------------------
 1. [Fab Moduleサイト(mit.edu)](http://kokompe.cba.mit.edu/downloads.html)で手順を確認する
 2. XCode をAppStoreからインストールする
 3. Command Line Tools for XCode をインストールする[(参考)](http://qiita.com/3yatsu/items/47470091277d46f3fde2)
 4. Homebrewをインストール[(参考)](http://qiita.com/b4b4r07/items/6efebc2f3d1cbbd393fc)
 僕は、上記環境がそろっていました。以下作業内容詳細です。

 5. brew install boost cmake libpng giflib　とタイプしインストールする
 6. http://www.wxpython.org/download.php にアクセスする
 7. wxPython3.0-osx-cocoa-py2.7 をクリックしダウンロードする
 8. wxPython3.0-osx-3.0.0.0-cocoa-py2.7.dmgをクリックする
 9. wxPython3.0-osx-cocoa-py2.7.pkgをクリックし、インストーラの指示通りにインストールする
 10. http://kokompe.cba.mit.edu/downloads.html　のdownloadをクリックする
 11. ダウンロードしたfab_srcフォルダをホームディレクトリ(/Users/<your home>)に移動する
 12. Applications -> Utilities -> Terminal をクリックする
 13. cd fab_src　としfab_srcフォルダに移動する
 14. make fab とタイプしエンターしfabmoduleを作成する
 15. make install　とタイプしfabmoduleをインストールする
 16. fab とタイプし、ウインドウが表示されが起動することを確認する

Modela接続準備
--------------
 http://www.startech.com/Downloads を開く
 Enter Product IDに ICUSB232V2 とタイプしSerchボタンをクリック
 http://www.startech.com/Cards-Adapters/Serial-Cards-Adapters/USB-to-RS232-Serial-Adapter-Cable~ICUSB232V2#dnlds
 Prolific_PL2303.zip をクリックしダウンロード
 Prolific_PL2303/Mac/Mac OS 10.6_10.7/PL2303_1.4.0.dmg をクリック
 PL2303_1.4.0をクリックしインストーラの指示通りにインストール
 macの再起動
 Modela MDX-15とmacをUSBtoSerialで接続する
 Applications -> Utilities -> Terminal をクリック
 ls /dev/tty.usb* とタイプし　/dev/tty.usbserialと表示されることを確認
 sudo easy_install pip とタイプしpythonのパッケージ管理システムをインストール
 sudo pip install pyserialとタイプしpythonのserialパッケージをインストール
 /usr/local/bin/rml_send_gui　というテキストファイルの中の/dev/ttyUSB0と記載されている箇所を/dev/tty.usbserialにすべて変更
 /usr/local/bin/fab_sendというテキストファイルの中の/dev/ttyUSB0と記載されている箇所を/dev/tty.usbserialに変更
 
 fabとタイプする
 使い方はこちらがすごくわかりやすかったです。
 http://qiita.com/mio_k/items/231fec28b5491345e469
