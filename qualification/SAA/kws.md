# メモ

## わからん言葉
* [X] IPS（Intrusion Prevention System)
  * 不正侵入防止システム
* [X] IDS（Intrusion Detection System）
  * 不正検知システム
* [X] promiscuous mode
  * promiscuous：無差別
  * コンピュータのネットワークインターフェースの動作モードの１つ
  * 電気に受信した全てのデータを読み込むモード

## ELB [2]
* AutoScalingの設定でELBヘルスチェックを有効にするのが最善
* ELBヘルスチェックを有効にしない場合、EC2ステータスはELBが正常でないと判断したインスタンスも正常であると判断する

## Redshift [4]
* シングルAZ配置のみをサポート
* 列指向データベース

## DynamoDB [82]
* シームレスにスケーリング

## CloudTrail
* 操作ログを取得

## VPC
* １つのリージョンに作成できるサブネット : 200

## IAM
* アクセスレベルを基準にモニタリングする必要あり
* Access Analyzerは、アクセス権限の最小化構成をモニタリング

## EC2
* インスタンスタイプ
  * I3 … ストレージ最適化インスタンス
  * R5 … メモリ最適化
  * T2 … 汎用インスタンス