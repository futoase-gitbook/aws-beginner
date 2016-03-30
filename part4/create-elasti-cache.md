# ElastiCacheの作成

ElastiCacheの作成を行う。

# Cache Subnet Groupの作成

ElastiCache向けのSubnet Groupを別途作成する必要がある。
ElastiCache Dashboardより "Cache Subnet Groups"を選択し、
"Create Cache Subnet Group"ボタンを押す。

![CREATE SUBNET ELASTI CACHE 01](./image/create-subnet-for-elasti-cache-01.png)

"basic" VPCを選択する

![CREATE SUBNET ELASTI CACHE 02](./image/create-subnet-for-elasti-cache-02.png)

Availabilty ZoneのSubnetを割り当てていく

![CREATE SUBNET ELASTI CACHE 03](./image/create-subnet-for-elasti-cache-03.png)

ap-northeast-1aとap-northeast-1cそれぞれに
"basic-redis"向けのSubnetを選択する。
SubnetIDでしか出てこないのでVPCでのSubnet一覧で確認しながら設定していく。
![CREATE SUBNET ELASTI CACHE 04](./image/create-subnet-for-elasti-cache-04.png)

作り終えたら早速ElastiCacheの作成にとりかかる。

![CREATE SUBNET ELASTI CACHE 05](./image/create-subnet-for-elasti-cache-05.png)

# RedisのElastiCacheインスタンスを立てる

![CREATE ELASTI CACHE 02](./image/create-elasti-cache-02.png)

RedisのElastiCacheインスタンスを立てる。
Redisを選択し、"Next"ボタンを押す。

![CREATE ELASTI CACHE 03](./image/create-elasti-cache-03.png)

## キャッシュクラスタの設定

Replication Group Nameは"basic-redis"など設定していく。
Security Groupは先程作成しておいた"basic-redis"を選択しよう。
Read Replicaの数は2台にしておく。
S3のバックアップはしないようにする。必要になったらあとでするようにしよう。
Backupについては省く。

![CREATE ELASTI CACHE 04](./image/create-elasti-cache-04.png)

内容に問題がなければ、"Launch Replication Group"ボタンを押す。
問題がなければ"Next"ボタンを押す。

![CREATE ELASTI CACHE 05](./image/create-elasti-cache-05.png)

無事Cache Clusterが作成されればOK。

![CREATE ELASTI CACHE 06](./image/create-elasti-cache-06.png)

これでElastiCacheの作成は終了
