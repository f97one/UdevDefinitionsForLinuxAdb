UdevDefinitionsForLinuxAdb
==========================

## 0. What is this?
LinuxでAndroidの開発を行うにあたって必要な、実機接続時のベンダID設定

## 1. tested environments

* Debian GNU/Linux 7.1 amd64
* Android SDK for Linux r22.2.1
* JDK7u40 for Linux x64

## 2. before installing

adbによるUSB接続の使用にはroot権限が必要だが、適切なアクセス権をudevのルールファイルに書くことで、これを回避できる。
このため、アクセス権を与えるグループを追加し、そこにユーザーを組み入れる。

ここではアクセス権を与えるグループをandroiders、組み入れるユーザー名をf97oneとしている。

```
 # groupadd androiders
 # usermod -G androiders f97one
```


