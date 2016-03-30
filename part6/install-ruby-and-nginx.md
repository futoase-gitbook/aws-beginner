# Rubyやnginxなどのインストール

Ruby on Railsアプリケーションを利用するので、
Ruby及びnginxをインストールする。
環境構築簡略化のためrbenvや、nginxのソースコードからの
ビルド、インストールについては行わず、
apt packageからインストールすることにする。
web-01, web-02それぞれで作業を行うのは面倒くさい。
ので、web-01で作業をしてAMIをコピーしてしまおう。
AMIのコピーについては後で書く。

## build-essential, git, libpq-devをインストール

makeコマンドなどができたてのインスタンス(Ubuntu 14.04)にはないので
build-essentialパッケージをインストールする。

```
> sudo apt-get install build-essential git libpq-dev
```

## Ruby 2.3をインストール

Brightbox社がRubyのapt packageを公開している。

[Ruby packages for Ubuntu](https://www.brightbox.com/docs/ruby/ubuntu/)

ここに記載されている通り、操作していく。

```
> sudo apt-get install software-properties-common
> sudo apt-add-repository ppa:brightbox/ruby-ng
> sudo apt-get update
```

Ruby 2.3をインストールする。

```
> sudo apt-get install ruby2.3 ruby2.3-dev
```

## pumaのインストール

Rack Application用のMiddlewareである
[puma](http://puma.io/)をインストールする。

```
> sudo gem2.3 install puma
```

## nginxのインストール

nginxのインストールを行う。
パッケージをnginxのsource listからいただくようにする。

[nginx: Linux packages](http://nginx.org/en/linux_packages.html)

### apt program keyringのインストール

[nginx_signing.key](http://nginx.org/keys/nginx_signing.key)より
apt program keyringをダウンロードし、インストールする。

```
> curl -O http://nginx.org/keys/nginx_signing.key
> sudo apt-key add nginx_signing.key
> OK
```

/etc/apt/sources.listの編集

mainlineを利用するようにする。

```
deb http://nginx.org/packages/mainline/ubuntu/ trusty nginx
deb-src http://nginx.org/packages/mainline/ubuntu/ trusty nginx
```

nginxパッケージのインストール

2016年3月時点でインストールされるパッケージは
nginx-1.9.12。

```
> sudo apt-get install nginx
Reading package lists... Done
Building dependency tree
Reading state information... Done
The following NEW packages will be installed:
  nginx
0 upgraded, 1 newly installed, 0 to remove and 68 not upgraded.
Need to get 628 kB of archives.
After this operation, 2,355 kB of additional disk space will be used.
Get:1 http://nginx.org/packages/mainline/ubuntu/ trusty/nginx nginx amd64 1.9.12-1~trusty [628 kB]
...
```
