# VPCを作る

AWS Management Consoleにて、VPCを選択しよう。

![SELECT IS VPC](./image/select-a-vpc.png)

Create VPCボタンを押して、VPCを作成しよう。
ここでの名前"bacic"とする。

![CREATE VPC](./image/create-vpc.png)

Private DNS、つまるところAWSで作成した他のホストについてから
ホスト名を引けるようにするため、Private DNSを有効にする。

作成したVPCを一覧より選択し、右クリック(かそれに相当する行為)で
"Edit DNS Hostnames"オプションを呼びだそう。

![EDIT DNS HOSTNAME](./image/edit-dns-hostname.png)

"Edit DNS Hostanames"の"DNS Hostnames"が
"YES"と設定し保存すればOKだ。

![DNS HOSTNAME ENABLE](./image/dns-hostname-enable.png)


