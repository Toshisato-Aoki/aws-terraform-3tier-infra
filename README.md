# AWS 3-Tier Webアプリ基盤（Terraform）

東京都デジタル人材育成支援事業「インフラ・AWSコース」で学んだ知識を基に構築した、シンプルな3-Tierアーキテクチャです。

## アーキテクチャ概要
- **Presentation Tier** : EC2（Webサーバー）
- **Application Tier** : EC2インスタンス（将来的にアプリをデプロイ）
- **Data Tier** : RDS MySQL（プライベートサブネット）

## 使用技術
- Terraform（v1.9+）
- AWS（VPC, EC2, RDS, Security Group, NAT Gateway）
- 東京リージョン（ap-northeast-1）

## 工夫点
- Public/Privateサブネットの適切な分離でセキュリティ強化
- 最小権限のSecurity Group設定
- 再利用可能なモジュール活用（terraform-aws-modules）

## 構築コマンド
```bash
terraform init
terraform plan
terraform apply

## 設計意図
・Web層とDB層を分離し、最小限の通信のみ許可することで基本的なセキュリティを意識しました。
・Public / Private サブネットを分け、RDS は Private Subnet に配置しました。
・Terraform により、同じ構成を再現可能な形で管理することを重視しました。

## 学んだこと
・VPC、サブネット、ルーティング、NAT Gateway の関係
・Security Group によるアクセス制御の考え方
・IaCで構成管理する際の再現性と修正しやすさ

## 今後の改善予定
・ALBの追加
・Auto Scalingの追加
・CloudWatchによる監視設定
・モジュール分割による保守性向上
