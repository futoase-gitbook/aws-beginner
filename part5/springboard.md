# 踏み台サーバ

踏み台サーバ、とただ表現するだけだと
攻撃に利用される恐れのあるサーバみたいな感じになる。
ここでは、"踏み台サーバ"とは
SSHを利用しログインを行ったあと、
各種EC2インスタンスにログインを行うための
入り口用サーバとして利用するサーバとして用語を使う

## 踏み台サーバの必要性

踏み台サーバがなければ、今まで作ってきた
RDS及びElastiCacheインスタンス、
EC2インスタンスへのアクセスも行えない。
publicにつながっているとはいえ80番台のportしか開いていなく、
SSHによってログインを行うこともできない。
VPC内に構築したサーバへのログインを行うため、
踏み台サーバの構築が必要となる。

## ここで取り扱ってないもの

- VPNサーバの構築
- SSH以外のログイン方法・ユーザ認証方式(Active Directoryなど)
- 攻撃に強いサーバの構築
