# AWS上に構築したシンプルなインフラ（Terraform）

東京都デジタル人材育成支援事業「インフラ・AWSコース」で学んだ内容をもとに、Terraformを用いてAWS上にVPC、EC2、RDSを構築したポートフォリオです。  
Public / Private サブネットの分離やNAT Gatewayの利用を通じて、AWSネットワーク構成の基礎理解を深めることを目的に作成しました。

## アーキテクチャ概要
- VPC
- Public Subnet / Private Subnet
- NAT Gateway
- EC2
- RDS MySQL

## 使用技術
- Terraform
- AWS（VPC, EC2, RDS, Security Group, NAT Gateway）
- terraform-aws-modules/vpc/aws
- ap-northeast-1

## 工夫した点
- Public / Privateサブネットを分離し、役割に応じた配置を意識しました
- VPCモジュールを活用し、構成をシンプルに管理しました
- Terraformで再現可能な形で構築できるようにしました

## 構築コマンド
```bash
terraform init
terraform plan
terraform apply
```

## 学んだこと
- VPC、サブネット、ルートテーブル、NAT Gateway の関係
- Public / Private サブネットを分けることで役割ごとの配置を意識する考え方
- EC2 と RDS を適切な場所に配置する基本的な考え方
- Terraform を用いてAWSリソースをコードで管理する流れ

## 今後の改善予定
- ALBの追加
- Web層とApp層の分離
- CloudWatch監視の追加
- 認証情報の安全な管理
- ファイル分割による保守性向上

## ディレクトリ構成
```text
.
├── README.md
└── main.tf
