# 技術スタック

| カテゴリ | 使用技術 |
| --- | --- |
| プログラミング言語 | HTML, CSS, JavaScript, TypeScript, PHP, Python, C#, Java |
| フレームワーク | Nuxt.js(TypeScript), Vue.js(JavaScript), Laravel(PHP), Django(Python), Flask(Python), .NET Framework(C#) |
| IaC | Terraform, Terraform Cloud, AWS CDK, AWS CloudFormation, AWS SAM, Serverless Framework |
| 仮想環境 | Vagrant, WSL2, venv, Docker, Docker Compose, DevContainer |
| AWS Compute & Network | VPC, EC2, ECS, ELB, Auto Scaling, CloudFront, Route53, Lambda, Batch |
| AWS Storage & Database | S3, ECR, RDS, DynamoDB, EFS |
| AWS Application Services | SES, SNS, SQS, APIGateway, EventBridge, WAF, ChatBot, Step Functions |
| AWS Security | IAM, SecurityHub, GuardDuty, Inspector, IAM AccessAnalyzer, AWS Health, WAF, KMS, Organizations |
| AWS Monitoring | CloudWatch, CloudTrail, AWS Config, Incident Manager |
| AWS DevOps | CodeCommit, CodeBuild, CodeDeploy, CodePipeline |
| AWS Data & Analytics | Glue, DataSync |
| AWS Management | Systems Manager (SSM), AWS Budgets, Cost Anomaly Detection |
| GCP | BigQuery, Data Transfer, Looker Studio |
| ミドルウェア | Apache, Nginx, Haproxy, postfix, dovecot, Redis, Supervisor, ClamAV, Zabbix |
| 開発ツール | ESLint, Prettier, pre-commit, gitleaks, git-filter-repo, localstack, rclone, makefile, fluent-bit, Composer |
| バージョン管理 | GitLab, GitHub, Subversion |
| 業務ツール | Datadog, Backlog, Slack, サイボウズ, ChatWork, Cursor, Visual Studio, Visual Studio Code, Figma, Microsoft Teams, Notion, draw.io |

# 業務内容

## 社内の横断的なインフラとSREを担当

### 期間

2024/02 - 現在

### 契約形態

準委任（業務委託）

### 担当業務\_概要

- 複数プロダクトのインフラ全般をAWSで要件定義、設計、構築、運用
- GitLab→GitHub Enterpriseの全社移行プロジェクトを主導
- 社内横断的なSRE業務（自動化、セキュリティ強化、コスト最適化、インフラ相談役）

### 担当役割

要件定義 ~ 運用

### 業界

士業、医業

### 開発体制

自社開発

### 技術スタック

- バックエンド: PHP
- インフラ: AWS
- DB: Aurora for Mysql, Mysql, MariaDB, PostgreSQL, Aurora Serverless
- IaC: CDK (Typescript)
- ローカル: docker, docker-compose, makefile

### コメント

GitLab→GitHub Enterpriseへの全社移行プロジェクトを主導し、  
セキュリティ設定や監査対応、運用ルール策定、CI/CD構築まで一貫して担当することで、  
技術実装だけでなく組織横断的なプロジェクトマネジメントの能力も養えました。

### 担当業務\_詳細

**ソースコード管理**

- GitLab CIを構築
- GitLabからGitHubへの移行
- GitHub Enterpriseを導入
- GitHub権限, ユーザー, リポジトリ, 通知のルール設定と運用
- GitHubセキュリティおよび監査ログを設定
- Dependabotを導入
- Dependabot Security UpdateによるPRベースブランチの自動変更
- GitHub Actions, 複合アクション, 再利用可能ワークフローを構築
- pre-commitによるコミット時のコード品質自動チェックを導入
- gitleaksによる機密情報の漏洩対策を導入
- git-filter-repoで既存リポジトリから機密情報を削除
- GitHub Organizationの加入, 脱退フローを整備
- GitHub Actions使用量の監視, 通知を自動化
- GitHubイベントのChatwork, Slack連携を整備
- GitHub運用ガイドラインを策定

**AWS**

- マルチアカウント管理のジャンプアカウントをIAM Roleで設計, 構築
- IAM UserのPolicy, MFAを見直し
- 各種OIDC連携を導入
- 不要なリソース削除によるコストカット, セキュリティ向上
- メールサーバを改修(EC2, EFS, Route53, postfix, dovecot)
- EC2の自動リカバリー機能を実装
- EFSによるEC2間ファイル共有を導入
- ECSの各種インシデント対応
- S3ウイルススキャンを導入
- EventBridge, Step FunctionsによるAWSリソース作成通知を構築
- MySQLプロセスのタイムアウト対応
- RDSエラー時の自動リカバリーを構築
- スロークエリログの調査, 対応
- スロークエリ管理の仕組みを構築
- EC2, ECS, Aurora, Aurora Serverlessのスペック最適化
- AWSセキュリティ設定, 運用, アラート対応(SecurityHub, GuardDuty等)
- AWS Healthによる障害, バージョンEOL検知
- IAM PolicyによるAWSリージョン制限(SCPの代替)
- CloudWatch Alarmによるメトリクス監視(EC2, ECS, RDS, Lambda等)
- DataSyncによるS3オブジェクト大量移行
- AWS初期設定のCDK, GitHub Actionsによる自動化
- Lambdaのパフォーマンスチューニング
- ECS, RDS, ELB, Lambda監視項目の社内ルール策定と構築
- Difyセルフホスト基盤を構築(ECS, RDS, S3, Redis等)
- CentOS7 EC2の延命対応(yum設定等)
- EC2アクセスをSSHからSSMに移行
- Incident Managerによるオンコール体制を構築
- バージョンアップ戦略を策定(MySQL, Lambda, PHP)
- AWSイベントのChatwork通知基盤を構築
- AWS通知をChatworkからSlackに移行
  - SQS, Lambdaによる自前実装(AWS Chatbotの代替)
- AWS Budgets, Cost Anomaly Detectionによるコスト異常検知, 調査

**Other**

- 各種インフラの相談役
- IaCツールの比較, 導入(Terraform未使用環境にCDK, CloudFormationを導入)
- CDKによるAWSインフラ構築
- ESLint, PrettierによるCDKコード品質管理
- CDKのCI/CDをGitHub Actionsで構築
- Dockerfile, docker-composeを導入
- makefileを導入
- VS Code設定を整理
- PHP, Composer, SupervisorのCI/CD構築によるデプロイ自動化
- PHP ValidateのCI/CD構築と最適化
- フロントエンド(Node.js)のCI/CDをGitHub Actionsで構築
- 各種作業の自動化(shell, CI/CD)
- rcloneによるS3→Google Drive大量ファイル移行
- ポストモーテムの運用ルール策定と文化醸成
- Difyのワークフロー構築と環境整備

---

## 不動産契約システムのインフラ構築

### 期間

2023/01 - 2025/09

### 契約形態

準委任（業務委託）

### 担当業務\_概要

- 新規や既存のインフラ全般をAWSで要件定義、設計、構築、運用
- Datadogを用いた監視を設計、構築、運用
- インフラに関する調査, 調整, 資料作成
- SRE業務

### 担当役割

調査

### 業界

人事・総務向けのBtoBサービス

### 開発体制

受託開発

### 技術スタック

- フロントエンド: SPA
- インフラ: AWS, GCP
- DB: Aurora for MySQL, MySQL, Aurora Serverless
- IaC: Terraform, SAM, SLS
- 監視: Datadog
- その他: GitHub, Docker

### コメント

複数プロダクトのインフラを同時並行で担当することで、  
様々なインフラパターンへの対応力が養われました。  
複数IaCツール（Terraform, SAM, SLS）の使い分けとDatadog監視基盤の構築を通じて、  
運用性と可観測性を重視したインフラ設計の重要性を学びました。

### 担当業務\_詳細

**IaC**

- Terraform, SAM, SLSのIaCでインフラ構築

**AWS**

- AWS各種推奨設定を調査, 検討, 構築
- フロントエンド(SPA)用のインフラを構築(CloudFront, S3)
- アプリのセキュリティ強化のためにWAFを構築
- 各種手作業をシェルスクリプトやLambda等で自動化
- RDS for Mysql, Aurora for Mysqlの構築
- DBパラメータを見直し(文字コードやcollation, log等)
- mysqlのマイナーバージョンアップ対応、自動化
- mysql5.7からmysql8.0系にバージョンアップ対応
- IAMの権限を整理, 構築
- IPアドレスの整理, 構築
- KMS, SSE-S3暗号化の見直し
- アプリのメンテナンスモードの構築と自動化(EventBridge, Lambda, WebACL)
- ECSロールバック対応
- 内部管理システムの作成(API Gateway, Lambda)
- ETLを構築(Glue, stepFunctions)
- OIDCの導入
- Organizationのセキュリティ周りを統合

**GCP**

- BigQuery, DataTransferを構築
- Looker Studioでデータ分析を表示

**Datadog**

- Intergration、CloudWatchStreamsを設定
- Logを出力、整理
- Monitorを設定
- ダウンタイムを設定
- ECSサーバーでdatadog-agent、fluent-bitを設定
- トレース、プロファイラー、APMを設定
- ブラウザログ、ソースマップ、RUMを設定
- Archive
- terraformでIaC化

**Other**

- Dockerfile, docker-composeの構築
- リリース作業, 作業手順書を作成
- 各種インシデント対応
- メンテナンスウィンドウの整備
- GitLabからGitHubに移行作業
- ブランチ, gitフローの見直し
- CI/CD(GitLabCI, GitHubActions, Terraform Cloud)の構築
- ログ(アクセスログ, CloudWatch)を設定
- localstack, localstackコンソールを整備
- local開発環境を整備(dev-container, workspace)
- 既存インフラを一通りterraform importでIaC化
- 全AWSアカウント共通の設定をIaC化

---

## マッチングアプリの新規インフラ構築

### 期間

2022/10 - 2022/12 (3ヶ月)

### 契約形態

準委任（業務委託）

### 担当業務\_概要

- Linuxのベースの既存インフラからAWS移行
- インフラをCloudFormationで構築
- 動作確認テスト

### 担当役割

設計 〜 構築

### 業界

マッチングアプリ

### 開発体制

受託開発

### 技術スタック

- 言語: PHP
- DB: MariaDB, MySQL
- その他: GitHub, Apache

### コメント

CloudFormation、シェルスクリプトの知識を取得できました。

### 担当業務\_詳細

- Networkの構築(VPC, Subnet...)
- EC2の構築
- EFSの構築
- ALBの構築
- Route53の構築
- RDSの構築
- ミドルウェアの設定(php, apache...)
- EC2の設定(ロケール, マウント, シンボリックリンク...)

---

## Linuxのベースのクラウド調査とAWS移行検討

### 期間

2022/07 - 2022/09 (2ヶ月)

### 契約形態

準委任（業務委託）

### 担当業務\_概要

- Linuxベースの既存インフラを調査
- 各サーバの用途や連携を紐解き、調査結果をまとめる
- AWS移行による、課題やリスク、対応策の洗い出し

### 担当役割

設計 ~ 構築

### 業界

マッチングアプリ

### 開発体制

受託開発

### 技術スタック

- 言語: PHP
- DB: MariaDB, MySQL
- その他: Docker, draw.io, GitHub, Nginx, Apache

### コメント

Linux、ミドルウェアの知識を取得できました。

### 担当業務\_詳細

- 各サーバのミドルウェア(Nginx, apache, haproxy, zabbix)を調査
- ロードバランスサーバのHaproxy、Nginxを調査
- webサーバのapacheを調査
- サービスのソースコード(php)を調査
- mysqlの設定や連携を調査
- キャッシュ・セッションの流れ・保有の仕方を調査
- 画像データの保有方法を調査
- cronの調査
- 全体構成図を作成
- AWS移行による、課題やリスク、対応策の洗い出し

---

## 既存インフラの調査・改修

### 期間

2022/06 - 2022/12 (7ヶ月)

### 契約形態

準委任（業務委託）

### 担当業務\_概要

- 既存AWS構成の調査
- 調査結果や各種提案資料の作成
- インフラの構築
- DB性能改善

### 担当役割

調査

### 業界

人事・総務向けのBtoBサービス

### 開発体制

受託開発

### 技術スタック

- 言語: Python
- DB: Aurora(PostgreSQL), DynamoDB
- その他: SVN, GitHub

### コメント

様々なAWSサービスを扱えて、多くのAWSの知識を積めました。  
個人事業主として初の案件で、フリーランスとしての様々な経験をさせていただきました。  
エンジニアとしても社会人としても多くの学びをさせていただきました。

### 担当業務\_詳細

- 約400本のLambdaを調査・整理
- Lambdaに関連するEventBridge, SQS, APIGatewayを調査
- AuroraとDynamoDBを調査
- CI/CDの調査
- インフラ全体構成図の作成
- IF一覧を作成
- データの扱い、性能、CICDに関する提案資料の作成
- postgresqlの性能改善(BULK, パーティショニング...)
- Network, Lambda, AWSBatch, EC2, RDS, ECRの構築
- CI/CDの構築(CodePipeline, CodeCommit, CodeBuild)
- IaC(SAM, Terraform, CloudFormation)

---

## 報告書作成支援システムの新規開発

### 期間

2022/02 - 2022/06 (5ヶ月)

### 契約形態

準委任（業務委託）

### 担当業務\_概要

- ヒアリング、コンサルティング
- webアプリケーションの作成
- pythonを用いた概念・技術検証

### 技術スタック

- フロントエンド: Vue.js(Nuxt.js)
- バックエンド: Python(Django)
- DB: Aurora(MySQL)
- その他: Nginx, Docker, GitHub, Google Cloud

### コメント

Pythonのライブラリや画像処理について知識を得られました。  
私が業務経験がある取引先の会社なため、  
お客様の声をダイレクトに聞きながら開発する経験をしました。

### 担当業務\_詳細

- 相手先の業務効率化に向けたヒアリング、コンサルティング
- DX化するための要件定義
- Java, Python, Nuxt.jsをDockerで構築(一部WSL2構築)
- Javaでwordを操作(ライブラリ：Apache POI)
- Pythonでwordを操作(ライブラリ：python-docx)
- PythonでPDFの操作(ライブラリ：複数)
- Pythonで画像から表を抽出や傾きを補正する処理（ライブラリ：OpenCV）
- その他Pythonの構築
- GoogleのVision APIで画像から文字の抽出
- Nuxt.jsでフロントエンドの作成
- AWSでのインフラの構築

---

## 物流会社の在庫管理をDX化する新規開発

### 期間

2021/12 - 2022/04 (4ヶ月)

### 契約形態

正社員

### 担当業務\_概要

- ヒアリング、コンサルティング
- webアプリケーション作成
- windowsアプリケーションの作成
- インフラを構築

### 技術スタック

- フロントエンド: HTML, CSS(Jinja, Bootstrap)
- バックエンド: Python(Flask), C#(.NET Framework)
- DB: Aurora(MySQL)
- その他: GitHub, Docker, Nginx

### コメント

ヒアリングや仕様検討の能力が鍛えられました。

### 担当業務\_詳細

- 属人化した会社システムの解消向けてヒアリング、コンサルティング
- AWSでインフラ構築
- Pythonでwebアプリの作成
- C#でWindowsアプリの作成
- 外部Windowsアプリを自動操作

---

## 建設会社の業務効率化するWindowsアプリケーションの新規開発

### 期間

2021/10 - 2022/02 (5ヶ月)

### 契約形態

正社員

### 担当業務\_概要

- 依頼先の業務効率化に向けたヒアリング、コンサルティング
- Windowsアプリケーションの開発

### 技術スタック

- 言語: C#
- フレームワーク: .NET Framework
- その他: GitHub

### コメント

人生で最初で最後かもしれないWindowsアプリ開発を経験できたので、  
振り返ると面白い経験ができました。

### 担当業務\_詳細

- Windowsアプリケーションのファイル構成を調査
- Windowsアプリケーションの環境構築からインストーラの作成
- 外部Windowsアプリケーションを自動で動かすRPA
- Microsoft.Office.Interop.Excelを用いたC#によるExcel操作
- Excel操作やRPA等に伴うメモリの問題の解消
- 作図に用いられるDXFファイルの操作

---

## ソーシャルゲームの新規開発、保守開発

### 期間

2021/07 - 2021/09 (2ヶ月)

### 契約形態

契約社員

### 担当業務\_概要

- Laravelを用いた新規開発、保守開発

### 技術スタック

- フロントエンド: HTML, CSS, JavaScript
- バックエンド: PHP(Laravel)
- DB: MySQL(Aurora), Redis
- インフラ: AWS
- その他: GitLab, Vagrant, Apache

### コメント

未経験からの参画であり、基礎的な概念からバックエンドの構築まで学べました。

### 習得スキル

- GitLabによるチーム開発
- Laravel(PHP)によるバックエンド開発
- MySQLを用いたDBの知識
