# AWSでのネットワーク構築(2016年Q1)

これはAWSでのネットワーク構築についてのメモ書き。

以前[Qiitaに記事](http://qiita.com/futoase/items/9c23306c1db790f35b87)を書いたのだが、やけに記事が縦に長くなってしまった。gitbookとしてまとめなおした。概念について理解できるレベルで書き留めておけば、将来の自分が見ても役に立つだろうと思うので残しておく。

# 注意点

2016年Q1時点での情報なので、すぐに内容は陳腐化すると思う。AWS Management ConsoleのUI変化は激しいし、AWSそのものの変化、改善も大変激しい。AWS lambdaなどのAWSが提供しているサービスについて深く説明していない。取り扱ってもいない。

# 前提としていること

- すでにAWSにアカウントを作成している
- すでにAWSに登録しているアカウントに対してクレジットカードの関連付けを行っている
- AWS Management Consoleが何かわかっている
- AWS Management Consoleへのアクセスには一般のウェブブラウザを利用する
- APIを基本とした動作、設定については書いていない
- やろうとしてることは、僅かなお金とはいえ、コストがかかるということ。
- AWSのEC2インスタンスCPU利用料金の無償枠があるものの、コストはかかることは認識していただきたい

# この文書で保証しないこと

- 作成したEC2インスタンス、RDSなどのAWSを利用することにかかった料金は保証しない。
- 第三者からのEC2インスタンス及びVPC内への攻撃
- 作成したEC2インスタンスの運用保守に関しての責任

# 文書のライセンス

- [CCライセンス](http://creativecommons.org/licenses/by/4.0/legalcod)とする

# LICENSE

[![CC v4.0 LOGO](https://i.creativecommons.org/l/by/4.0/88x31.png)](http://creativecommons.org/licenses/by/4.0/)
