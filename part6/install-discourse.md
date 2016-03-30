# Discourseのインストール

テスト用のアプリケーションとして
Discourseをインストールする。

[Discourse](http://www.discourse.org/)

# 今回取り扱うリビジョン

master branchのものを取り扱うが、
commitは以下のハッシュのものを利用する

[e29806b9d3c9131cd09c9558f6a9ee23323731e9](https://github.com/discourse/discourse/tree/e29806b9d3c9131cd09c9558f6a9ee23323731e9)

# Discourse用のディレクトリを作成する

/var/www というディレクトリを作成する。

```
> sudo mkdir -p /var/www
> sudo chown ubuntu:ubuntu /var/www
```

# ソースコードのダウンロード

Discourseのソースコードをダウンロードする。

```
> cd /var/www
> git clone https://github.com/discourse/discourse.git
```

# bundle installの実行

bundle installを実行する
そのためにbundlerをインストールしよう。

```
> sudo gem install bundler
```

続いて、bundle install を実行する

```
> cd discourse
> bundle install --path vendor/bundle
```

# Discourseの立ち上げテスト

Discourseは、database.ymlについて
developmentしかない。
productionの設定は後で行うとして、
今は接続が行えるか確認できるようにしていく

(編集中)
