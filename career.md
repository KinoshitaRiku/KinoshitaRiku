# 技術スタック

| カテゴリ | 使用技術 |
| --- | --- |
| プログラミング言語 | HTML, CSS, JavaScript, TypeScript, PHP, Python, C#, Java |
| フレームワーク | Nuxt.js, Vue.js(JavaScript), Laravel(PHP), Django(Python), Flask(Python), .NET Framework(C#) |
| IaC | Terraform, Terraform Cloud, AWS CDK, AWS CloudFormation, AWS SAM, Serverless Framework |
| 仮想環境 | Vagrant, WSL2, venv, Docker, Docker Compose, DevContainer |
| AWS Compute & Network | VPC, EC2, ECS, ELB, Auto Scaling, CloudFront, Route53, Lambda, Batch |
| AWS Storage & Database | S3, ECR, RDS, DynamoDB |
| AWS Application Services | SES, SNS, SQS, APIGateway, EventBridge, WAF, ChatBot |
| AWS Security | IAM, SecurityHub, GuardDuty, Inspector, IAM AccessAnalyzer, AWS Health, WAF |
| AWS Monitoring | CloudWatch, CloudTrail, AWS Config, Incident Manager |
| AWS DevOps | CodeCommit, CodeBuild, CodeDeploy, CodePipeline |
| その他サービス | GitLab, GitHub, GCP |
| 業務ツール | Datadog, Backlog, Slack, サイボウズ, ChatWork, Curosr, Visual Studio, Visual Studio Code, Figma, Subversion, Microsoft Teams, Notion, draw.io |

# 業務内容

## 社内の横断的なインフラとSREを担当

### 期間
2024/02 - 現在

### 担当業務_概要
- 新規、既存のインフラ全般をAWSで要件定義、設計、構築、運用
- GitHubの導入と運用
- SRE業務

### 技術スタック
- バックエンド: PHP
- インフラ: AWS
- DB: Aurora for Mysql, Mysql, MariaDB
- IaC: CDK (Typescript)
- ローカル: docker, docker-compose, makefile

### 担当業務_詳細

**ソースコード管理**
- GitLab CIを構築
- GitLabからGitHubへの移行
- GitHub Enterpriseを導入
- GitHub 権限, ユーザー, リポジトリ, 通知のルール設定と運用
- GitHub セキュリティや監査ログを設定
- dependabotの導入
- dependabot security updateにより、作成されるPRのベースブランチを自動で変更
- GitHubActions, 複合アクション, 再利用ワークフローを構築
- コミット時にコード品質を自動で確保するためにpre-commitを導入
- 機密情報の漏洩対策のためにgitleaksを導入
- 既存リポジトリから機密情報を削除するためにgit-filter-repoを使用
- GitHub Organizationの加入と脱退をGoogle Apps Scriptで自動化
- GitHub Actionsの使用量が無料枠を超えないか把握するために、GitHub ActionsからGoogle SpredSheetへの記入と通知を自動化
- PHP, ComposerのCICDを構築し、デプロイの自動化と作業の短縮

**AWS**
- ジャンプアカウント(複数のAWS アカウント管理)を設計、構築
- IAM UserのIAM Policy, MFAを見直しと設定
- AWSのコストカットやセキュリティ向上のために、不要なリソースを削除
- メールサーバを改修(EC2, EFS, Route53, postfix, dovecot)
- EC2間のファイル共有としてEFSを導入
- S3ウイルススキャンを導入(ClamAV)
- GuardDutyでウイルスの感染があるEC2が検出されたので、ClamAVを用いて検査
- AWSリソース作成時に通知する仕組みを構築
- RDSエラー時の自動対応を構築
- EC2, Aurora, Aurora Serverlessのスペック見直し
- AWSセキュリティ設定, 運用(SecurityHub, GuardDuty等)
- AWSリージョン制限(SCPが使えないのでIAM Policyで制限)
- CloudWatchで各種メトリクス監視(EC2, ECS, RDS, Lambda)
- DataSyncでS3のオブジェクト移行
- OIDCの導入
- AWSの初期設定を手動からCDKとGitHubActionsで自動化
- CentOS7のEC2を延命治療 (yumを使用できるように設定...)
- EC2へのアクセスで鍵の管理をなくすためにSSHからSSMに変更
- スロークエリをCloudWatch Logs サブスクリプションで検知し、Lambdaで通知する仕組みを構築
- Incident Managerでオンコールを構築
- バージョンアップ戦略を設定

**Other**
- 各種インフラの相談役
- IaCの比較, 導入
- CDKでAWSを構築
- ESLintとPretterを導入
- CDKのデプロイ自動化
- Dockerfile, docker-composeの導入
- makefileの導入
- vscodeの設定を整理
- 各種作業の自動化(shell, CICD)
- S3からGDriveの大量ファイル移行(rclone)
- 社内で似たインシデントが発生しているので、ポストモーテムの運用ルールを作成と文化の普及

---

## 不動産契約システムのインフラ構築

### 期間
2023/01 - 現在

### 担当業務_概要
- 新規や既存のインフラ全般をAWSで要件定義、設計、構築、運用
- インフラに関する調査, 調整, 資料作成

### 技術スタック
- フロントエンド: SPA
- インフラ: AWS, GCP
- DB: Aurora for MySQL, MySQL
- IaC: Terraform, SAM, SLS
- 監視: Datadog
- その他: GitHub, Docker

### 担当業務_詳細

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
- 管理システムを作成(API Gateway, Lambda)
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

### 担当業務_概要
- Linuxのベースの既存インフラからAWS移行
- インフラをCloudFormationで構築
- 動作確認テスト

### 技術スタック
- 言語: PHP
- DB: MariaDB, MySQL
- その他: GitHub, Apache

### コメント
CloudFormation、シェルスクリプトの知識を取得できました。

### 担当業務_詳細
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

### 担当業務_概要
- Linuxのベースの既存インフラを調査
- 各サーバの用途や連携を紐解き、調査結果をまとめる
- AWS移行による、課題やリスク、対応策の洗い出し

### 技術スタック
- 言語: PHP
- DB: MariaDB, MySQL
- その他: Docker, draw.io, GitHub, Nginx, Apache

### コメント
Linux、ミドルウェアの知識を取得できました。

### 担当業務_詳細
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

### 担当業務_概要
- 既存AWS構成の調査
- 調査結果や各種提案資料の作成
- インフラの構築
- DB性能改善

### 技術スタック
- 言語: Python
- DB: Aurora(PostgreSQL), DynamoDB
- その他: SVN, GitHub

### コメント
様々なAWSサービスを扱えて、多くのAWSの知識を積めました。個人事業主として初の案件で、フリーランスとしての様々な経験をさせていただきました。とてもエンジニアとしても社会人としても多くの学びをさせていただきました。

### 担当業務_詳細
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

### 担当業務_概要
- ヒアリング、コンサルティング
- webアプリケーションの作成
- pythonを用いた概念・技術検証

### 技術スタック
- フロントエンド: Vue.js(Nuxt.js)
- バックエンド: Python(Django)
- DB: Aurora(MySQL)
- その他: Nginx, Docker, GitHub, Google Cloud

### コメント
Pythonのライブラリや画像処理について知識を得られました。私が業務経験がある取引先の会社なため、お客様の声をダイレクトに聞きながら開発する経験をしました。

### 担当業務_詳細
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

### 担当業務_概要
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

### 担当業務_詳細
- 属人化した会社システムの解消向けてヒアリング、コンサルティング
- AWSでインフラ構築
- Pythonでwebアプリの作成
- C#でWindowsアプリの作成
- 外部Windowsアプリを自動操作

---

## 建設会社の業務効率化するWindowsアプリケーションの新規開発

### 期間
2021/10 - 2022/02 (5ヶ月)

### 担当業務_概要
- 依頼先の業務効率化に向けたヒアリング、コンサルティング
- Windowsアプリケーションの開発

### 技術スタック
- 言語: C#
- フレームワーク: .NET Framework
- その他: GitHub

### コメント
人生で最初で最後かもしれないWindowsアプリ開発を経験できたので、
振り返ると面白い経験ができました。

### 担当業務_詳細
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

### 担当業務_概要
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