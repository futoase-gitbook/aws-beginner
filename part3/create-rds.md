# RDSの作成

RDSを作成する。RDBMSはPostgreSQLを選択する。

![CREATE RDS 01](./image/create-rds-01.png)

# RDS Dashboardより作成開始

RDS Dashboard > Instances から、
"Launch DB Instance"ボタンを押す

![CREATE RDS 02](./image/create-rds-02.png)

"PostgreSQL"を選択して"Select"ボタンを押す

## Production | Dev/Testの選択

![CREATE RDS 03](./image/create-rds-03.png)

Production向けか、Dev/Test向けか問われる。
今回はProduction向けを選択しよう。

## Setting

![CREATE RDS 04](./image/create-rds-04.png)

...といいつつも今回はケチケチ運用で、

- MZなし
- SSDもGeneral Purpose
- t2.microで運用

みたいな感じにしていく。

![CREATE RDS 05](./image/create-rds-05.png)

## Advanced Settings

Security Groupなどの設定。
については今まで作成しておいた
Security GroupやVPCを選択する。

![CREATE RDS 06](./image/create-rds-06.png)

"Launch DB Instance"ボタンを押せばRDS作成は終わる。

以上で作成完了。

![CREATE RDS 07](./image/create-rds-07.png)

RDSインスタンスが立ち上がるのを待とう。

![CREATE RDS 08](./image/create-rds-08.png)

# 終わり

しばらく待てば、RDSインスタンスが立ち上がる。
以上でRDSの作成は完了。

![CREATE RDS 09](./image/create-rds-09.png)
