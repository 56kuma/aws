# AWS公式

* Skill Builder から無料で受けられるやつ

## 問題を解く中での知らない言葉

### No.2

* [X] 動的ホストポートマッピング
  * ロードバランサーに対する振り分けとして、プロトコル+ポートが指定できるようになった。
* [X] パスベースのルーティング
  * リクエストのURLに含まれる文字列パターンを見て、ELBが振り分けをする。

### No.5

* [X] スケールイン
  * サーバの台数を減らすこと。増やすのはスケールアウト。
* [X] クールダウン期間
  * AutoScalingの発動直後、余分にEC2を追加/削減してしまうのを防ぐための待ち時間
* [X] スティッキーセッション（セッションアフィニティ）

### No.6

* スポットインスタンスを削除するには、スポットリクエストをキャンセル -> スポットインスタンスを終了

### Mo.7

* [X] リンクローカルアドレス
  * 169.254.169.254
  * インスタンスメタデータ*1を取得するためのアドレス
    * *1 ami-id とか。
  * curlコマンドで取得できる
    > curl <http://169.254.169.254/latest/meta-data/>

### No.8

* [X] S3 Transfer Acceleration
  * エッジロケーションを使用してデータをS3にコピーすることで迅速なアップロードを容易にする
* S3では1回のPUTオペレーションで最大5GBのオブジェクトをアップロード可能
* [X] マルチパートアップロード
  * ファイルをみじん切りにしてアップロードするイメージ
  * 最大5Tまで対応

### No.9

* 汎用SSD
  * ボリュームごとに 16,000 IOPSに制限されている。
* プロビジョンドIOPS SSD
  * 最大 64,000 IOPS

* IOPSはピンポイントでストレージの書き込み読み込み性能を表すが、スループットはネットワーク通信速度的な指標で、ややスコープが広い

### No.10

* [X] Site-to-Site VPN
  * VPCとユーザのオンプレミスネットワークの間との接続。
* [X] カスタマーゲートウェイ
  * オンプレミスネットワーク（Site-to-Site VPN 接続のユーザ側）で所有または管理している物理アプライアンスまたは、ソフトウェアアプライアンス。
  * ユーザまたはネットワーク管理者は、Site-to-Site VPN 接続で動作するようにデバイスを設定する必要がある。
  * [AWS ユーザーガイド](https://docs.aws.amazon.com/ja_jp/vpn/latest/s2svpn/your-cgw.html)
* [X] 仮想プライベートゲートウェイ
  * VPCにアタッチされ、AWSでSite-to-Site VPN接続を作成する。
  * サイト間VPN接続のAmazon側にあるVPNコンセントレーター。Amazon側のゲートウェイとして、トランジットゲートウェイでも実現可能。

### No.11

* [X] DynamoDB
  * キーバリューのレコードをサポートするNoSQL
  * ミリ秒単位の応答時間を提供
* [X] DynamoDB アクセラレータ
  * マイクロ秒単位の応答時間を提供
  * DynamoDBの前段にキャッシュクラスタを構成

### No.12

* 「ロールを使用してアクセス許可を委任する」が、セキュリティのベストプラクティス。

### No.13

* [X] Amazon Cognito
  * Incognito（変数の、匿名の）の"in"を取り、対義語にしたイメージ
  * Webおよびモバイルアプリの認証、承認、およびユーザ管理を提供

### No.14

* [X] AWS Shield
  * DDOSから守る。
  * AWS WAF は、Web Application Firewall であるため、SQLインジェクションやクロスサイトスクリプティングから守る。

### No.15

* [X] AWS Firewall Manager
  * 多数のアカウントとアプリケーションにわたって中央でAWS WAFルールを設定/管理することを用意にするセキュリティ管理サービス
  * AWS Organizationsの多数のアカウントに横断的に、Applicaiton Load Balancers と Amazon CroudFrontのディストリビューションに対するAWS WAFルールを簡単にロールアウトできる

### No.16

* [X] S3 Gracier
  * 迅速（高速）取り出し ▶ 使用すると、1~5分でアクセスできる。
  * 標準取り出し ▶ 3~5時間
  * 大容量取り出し ▶ 5~12時間、最も安価
* [X] S3 IA（Infrequent access）
  * 低頻度アクセス
  * 従量課金
  * 随時取り出し可能

### No.17

* [X] SSDバックドストレージ最適化(i3)
  * 365,000を超えるランダムIOPSを提供
* [X] インスタンスストア
  * 揮発性ブロックストレージ
  * データが永続化されない
  * EBSより高IOPS、高スループット、低レイテンシー
  * スナップショット取得は不可能
  * 再起動ではデータは維持される
  * 費用はEC2に含まれる、ちょっと効果になる

### No.19

* OLTP（オンライントランザクション処理）
* [X] AWS Fargate
  * アプリケーションがアイドル状態のときにコストは発生しない
* [X] Aurora Serverless
  * オンデマンドの自動スケーリング設定
  * 自動起動、シャットダウン、容量のスケールアップまたはスケールダウンを行う

### No.20

* [X] AWS Snowball Edge Storage Optimized
  * 80TBが移行対象の場合、リージョンが東京だと、800USDが費用となる。
