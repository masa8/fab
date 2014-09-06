fabmoduleをmacにインストールしてModelaMDX-15で出力する
=====================================================

OS								: Mac OSX Version 10.9.3
USBtoRS232ケーブル:StarTechUSB to RS232 DB9 Serial Adapter Cable M/M (ICUSB232)
http://www.amazon.com/StarTech-RS232-Serial-Adapter-Cable/dp/B000067SNB/ref=sr_1_16?s=electronics&ie=UTF8&qid=1401599135&sr=1-16&keywords=star+tech+serial


 http://kokompe.cba.mit.edu/downloads.html
 XCode をインストール
 Command Line Tools for XCode をインストール
 Homebrewをインストール
 brew install boost cmake libpng giflib
 http://www.wxpython.org/download.php にアクセス
 wxPython3.0-osx-cocoa-py2.7 をクリック
 wxPython3.0-osx-3.0.0.0-cocoa-py2.7.dmgをクリック
 wxPython3.0-osx-cocoa-py2.7.pkgをクリックし、インストーラの指示通りにインストール
 http://kokompe.cba.mit.edu/downloads.html　のdownloadをクリック
 ダウンロードしたfab_srcフォルダをホームディレクトリ(/Users/<your home>)に移動
 Applications -> Utilities -> Terminal をクリック
 cd fab_src
 make fab とタイプしエンター
 make install
 fab とタイプしアプリが起動することを確認
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
