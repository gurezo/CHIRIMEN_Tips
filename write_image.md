### Ubuntuでの操作
- Ubuntuの端末（terminal）を起動する

### android-tools-adbをインストールする  
```
$ sudo apt-get install -y android-tools-adb
```

### github から CHIRIMEN-toolsリポジトリをクローンする
```
git clone https://github.com/chirimen-oh/CHIRIMEN-tools.git
```

### 最新イメージを取得する
```
※2016XXXX：バージョン
$wget https://github.com/chirimen-oh/release/releases/download/CMN2015-1/CMN2015-1_B2GOS-2016XXXX.zip
```

### 最新イメージを解凍／展開する
```
$unzip CMN2015-1_B2GOS-2016XXXX.zip
```

### ルールを設定する
- ルールファイル（51-android.rules）の作成
```
$ sudo vi /etc/udev/rules.d/51-android.rules
```

- ルールファイル（51-android.rules）の編集
~~~~
SUBSYSTEM=="usb", ATTR{idVendor}=="2207", MODE="0666",GROUP="plugdev”
~~~~

### 設定を反映をする。
```
$ sudo udevadm control --reload
```

### CHIRIMEN BoardをPCとディスプレイに接続する
- OTG と印字されたコネクタにUSBケーブルをPCに接続する
- HDMI と印字されたコネクタにHDMIケーブルをディスプレイに接続する

### CHIRIMEN Boardを書き込みモードで起動する。
- recoverボタンを押しながら電源接続し、起動する。

### CHIRIMEN Boardをファーム書き込みコマンドを実行する。
- recoverボタンを押しながら電源接続し、起動する。
- コマンド実行
```
$ ./CHIRIMEN-tools/Linux_Upgrade_Tool_v1.21/upgrade_tool uf CMN2015-1_B2GOS-2016XXXX.img
```

### CHIRIMEN Boardの再起動まち
