# AWS 3-Tier Webアプリ基盤（Terraform）

東京都デジタル人材育成支援事業「インフラ・AWSコース」で学んだ知識を基に構築した、シンプルな3-Tierアーキテクチャです。

## アーキテクチャ概要
- **Presentation Tier**: Application Load Balancer + EC2（Webサーバー）
- **Application Tier**: EC2インスタンス（将来的にアプリをデプロイ）
- **Data Tier**: RDS MySQL（プライベートサブネット）

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
