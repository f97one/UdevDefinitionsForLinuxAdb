UdevDefinitionsForLinuxAdb
==========================

## 0. What is this?
LinuxでAndroidの開発を行うにあたって必要な、実機接続時のベンダID設定

## 1. tested environments

* Debian GNU/Linux 7.1 amd64
* Android SDK for Linux r22.2.1
* JDK7u40 for Linux x64

## 2. before installing

adbによるUSB接続の使用にはroot権限が必要だが、適切なアクセス権をudevのルールファイルに書くことで、これを回避できる。<br />
このため、アクセス権を与えるグループを追加し、そこにユーザーを組み入れる。

ここではアクセス権を与えるグループをandroiders、組み入れるユーザー名をf97oneとしている。

```
 # groupadd androiders
 # usermod -G androiders f97one
```

## 3. how to install

同梱の `51-android.rules` を、/etc/udev/rules.d/ 以下に配置する。<br />
その後、ルールファイルをリロードする。

```
 $ sudo cp -iv ./51-android.rules /etc/udev/rules.d/
 $ sudo udevadm control --reload-rules
```

EclipseのDDMSパースペクティブを開き、USBデバッグを有効にしたデバイスを接続／切断してデバイスが正常に認識できることを確認すること。

## 4. See also:

[Using Hardware Devices | Android Developers](http://developer.android.com/intl/ja/tools/device.html)

