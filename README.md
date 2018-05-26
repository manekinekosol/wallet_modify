## ブランチ元について
Firefly Walletという海外のプロジェクトからブランチを切っています。
https://github.com/firefly/wallet

ざっくりいうとArduinoにairgap walletを実装するようなものです。


## 困っていること
元の実装は専用のアプリケーションと連携してトランザクションに対する署名を送るものですが、Arduino側のBluetoothとかディスプレイの設定とかあります。そこで最も単純なものとして、機能を削って、シリアル通信で署名を送受信するシンプルなものにしました。
といっても、用意されている関数をいじったりはせず、実行系のファイルfirefly.inoの最終部分のみをいじりました。

これをArduino IDE（開発ツール）で実行しようとすると、関数が複数定義されているというエラーで
コンパイルが通りません。C言語のコンパイル上の問題で、includeしているライブラリが競合してしまっている様です。
しかし、元のファイルに関数を書き加えたわけではなく、ちょっとした環境やコンパイル（分割コンパイルとか）による問題
だと思っています。

知見がある方、、、、どうかお助けを。
