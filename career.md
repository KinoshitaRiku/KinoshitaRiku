# 木下 陸 ｜ インフラ・SRE

**全社規模のAWSガバナンス基盤を、計画策定から運用定着まで単独で完遂できるインフラ・SREです。**

約45アカウント / 約5OU / 約100名のマルチアカウント統制を、計画策定から運用引き継ぎまで単独主担当で構築

---

## 職務要約

直近では、全社AWS環境のガバナンス強化を目的に、**約45アカウント・5OU・約100名**を対象とした全社ランディングゾーン（AWS Control Tower / Organizations / IAM Identity Center / SCP）を設計・構築しました。計画策定、既存アカウントの移行、運用手順の整備、運用チームへの引き継ぎまでを**単独の主担当として完遂**し、認証・認可の一元化とセキュリティ統制の標準化を実現しています。

GitLab → GitHub Enterprise の全社移行では、技術選定から権限設計・運用ルール策定・CI/CD整備までをリードしています。**関係者の多い横断プロジェクトを、技術実装だけでなく合意形成と運用定着まで通して進められる**ことが差別化点です。医療・士業・不動産など、規制とセキュリティ要件の厳しい業界での実績が中心です。

**実務経験**: インフラ・SRE 2022年6月〜（約4年半） / エンジニア通算 2021年7月〜（約5年）

## 主要実績

### AWS Control Tower による全社統制基盤の構築・移行（単独主担当）

全社AWS環境のガバナンス強化を目的に、**約45アカウント / 約5OU / 約100名**を対象としたランディングゾーンを設計・構築。計画策定から移行・運用引き継ぎまでを単独で担当。（社内横断のインフラとSRE / 2024年2月〜）

- 導入前は、長期アクセスキーを持つIAM UserとAdmin権限が各自の判断で配布され、リージョン制限もない状態だった
- AWSリセラー経由と直契約のアカウントが混在し、発行・サポートの窓口がリセラー独自フローに依存していたため、AWS推奨の手順をそのまま適用できない前提のもとで設計した
- OU設計はAWSの推奨構成を基準に、リセラー側の運用制約と社内の組織実態を突き合わせて決定。IAM Identity Centerのグループ・許可セット、SCPによる統制を設計しTerraformで実装
- 既存アカウントは1件ずつリソースと使用リージョンを精査し、不要なものを整理したうえでEnroll。既存のセキュリティ設定の付け替えとログ基盤の移設も実施
- 社内にレビュー可能な担当者がいなかったため、方針と判断理由を文書化して合意を取りながら進行し、運用チームへ引き継いだ
- **成果**: 長期アクセスキーとAdmin権限の個別配布を廃止し、IAM Identity Centerによる認証・権限付与へ一元化。利用リージョンを制限し、把握外のリソースが生まれない状態にした

### GitLab → GitHub Enterprise 全社移行プロジェクトの主導

**150リポジトリ / 100名**を対象としたソースコード管理基盤の全社移行を、技術選定から運用ルール策定まで一貫して主導。（社内横断のインフラとSRE / 2024年2月〜）

- 社内に要望はあったが過去に断念されていた移行を、参画後の最初のタスクとして引き受け完遂
- 移行前の棚卸しで、認証情報やトークン類が履歴に残り続けていることを発見。GitHubへ移す前に git-filter-repo で履歴から削除し、あわせて該当する認証情報のローテーションを所有チームへ案内した
- 担当1名かつ利用者の大半がGitHub未経験という制約から、一括ではなく段階移行を選択し、運用の浸透と並走させた
- gitleaks を pre-commit と CI の両方に組み込み、ローカルをすり抜けた場合もCI側で検知できる形にした
- 複合アクション・再利用可能ワークフローで、AWS認証、PHPのフォーマッタ・リンタ・テスト、DBマイグレーションを共通化
- **成果**: 断念されていた全社移行を完遂し、認証情報を履歴から除いたうえで新基盤へ移行。権限・加入脱退・監査のルールを策定して運用チームへ移管

### Datadog による可観測性基盤の設計・構築

複数プロダクトを対象に、監視・可観測性基盤をゼロから設計・構築しTerraformでIaC化。（不動産契約システム / 2023年1月〜2025年9月）

- **成果**: APM・トレース・プロファイラによるバックエンド可観測性と、RUM・ソースマップによるフロントエンド可観測性を確立

### HCP Terraform の新規導入

Atlantisによる運用を、適用履歴の追跡と変更差分の事前確認ができる基盤へ移行。（健康管理システム / 2026年4月〜）

- **成果**: 未レビューの本番適用を仕組みで排除し、Plan/Apply のレビュー・承認フローを定着

## 専門領域

**1. クラウドガバナンス / マルチアカウント統制**
AWS Control Tower、Organizations、IAM Identity Center、SCPによる統制基盤の設計と実装。既存アカウントの移行計画策定から運用定着までを含む。

**2. IaC / CI-CD による自動化**
Terraform、Terragrunt、AWS CDK、SAM、Serverless Framework を要件に応じて使い分け。HCP Terraform の新規導入によるリモート実行・承認フロー整備の実績あり。GitHub Actions によるデプロイ自動化とコード品質管理。

**3. SRE / 可観測性・信頼性**
Datadog（APM・RUM・トレース・ログ基盤）およびCloudWatchによる監視設計、Incident Managerによるオンコール体制構築、ポストモーテム文化の醸成、コスト最適化。

## 技術スタック

| カテゴリ | 使用技術 |
| --- | --- |
| クラウド | AWS（メイン）, GCP |
| IaC | Terraform, Terragrunt, HCP Terraform (旧 Terraform Cloud), AWS CDK, AWS CloudFormation, AWS SAM, Serverless Framework |
| 統制・セキュリティ | Control Tower, Organizations, IAM Identity Center, SCP, IAM, SecurityHub, GuardDuty, Inspector, IAM AccessAnalyzer, AWS Health, WAF, KMS |
| 監視・可観測性 | Datadog (APM / RUM / Trace / Log), CloudWatch (Alarm / Dashboard / Logs), CloudTrail, AWS Config, Incident Manager, Athena |
| コンピュート・ネットワーク | VPC, EC2, ECS, ELB, Auto Scaling, CloudFront, Route53, Lambda, AWS Batch |
| データベース・ストレージ | Aurora (MySQL / PostgreSQL), Aurora Serverless, RDS, DynamoDB, Redis, S3, EFS, ECR |
| サーバーレス・連携 | Step Functions, EventBridge, API Gateway, AppSync, SQS, SNS, SES, ChatBot |
| CI/CD・SCM | GitHub Enterprise, GitHub Actions, GitLab CI, CodePipeline, CodeBuild, CodeDeploy, CodeCommit, pre-commit, gitleaks, git-filter-repo |
| データ・分析 | Glue, DataSync, Athena, BigQuery, Data Transfer, Looker Studio |
| 運用管理 | Systems Manager (SSM), AWS Budgets, Cost Anomaly Detection |
| コンテナ・開発環境 | Docker, Docker Compose, DevContainer, localstack, Vagrant, WSL2, venv, makefile |
| ミドルウェア | Nginx, Apache, Haproxy, postfix, dovecot, Supervisor, ClamAV, Zabbix |
| 言語 | TypeScript, Python, PHP, Shell, JavaScript, C#, Java, HTML, CSS |
| フレームワーク | Nuxt.js, Vue.js, Laravel, Django, Flask, .NET Framework |
| その他ツール | Backlog, Jira, Slack, Microsoft Teams, ChatWork, サイボウズ, Notion, Figma, draw.io, Cursor, Dify |

---

## 業務内容

### 健康管理システムのインフラ構築

**2026年4月 - 現在**｜ヘルスケア・医療｜準委任｜インフラ・SRE（設計〜運用）
**体制**: プロジェクト50名 / 担当チーム4名
**環境**: AWS, Aurora PostgreSQL（新システム）/ Aurora for MySQL（既存システム）, Terraform, Terragrunt, HCP Terraform, GitHub, Jira, Microsoft Teams

**IaC運用基盤の移行（Atlantis → HCP Terraform。適用履歴と変更差分を追跡できる運用へ再設計）**

- 既存のAtlantis運用では、applyの実行履歴の追跡と変更差分の事前確認が難しく、変更の影響範囲を判断しにくい状態だった
- Atlantis / HCP Terraform を比較し、適用履歴の可視性・承認フロー・シークレット管理の観点からHCP Terraformを選定
- Terragruntを廃止し、Workspace単位で部分applyできるディレクトリ構成へ再設計。一括適用をやめ、変更範囲を限定できる形にした
- Organization / Workspace 構成、VCS連携、実行モード、変数・シークレット管理を設計
- Plan/Apply のレビュー・承認フローを整備し、未レビューの本番適用を仕組みで排除
- **成果**: 誰がいつ何を適用したかを追跡でき、差分を事前確認したうえで影響範囲を限定して反映できる運用へ移行

**新システムのインフラ設計・構築（提示された設計にCI/CDが未考慮だったため、要件を確認して補完）**

- CloudFront / ECS / Aurora PostgreSQL 構成の詳細設計と構築
- 参画時点の設計ではCI/CD・デプロイフローが考慮されていなかったため、要件をヒアリングして設計に反映
- 各サブシステムからの通知をSQSで疎結合化し、受信側が停止してもデータを失わない構成で新規構築

**その他の担当範囲**

- RI / Savings Plansの更新対応（前年の利用実績をもとに購入タイプ・期間・支払方法を見直し）
- EventBridge / Step Functions / Lambda / AWS Batch によるジョブ実行基盤の構築
- SecurityHubの検出事項の対応、WAF(WebACL)の構築（AWSマネージドルール中心、Count検証を経てBlockへ移行）
- WAFログのS3出力とAthenaでの分析、CloudWatch Alarmによる検知通知、検知時の運用手順の整備
- AppSyncの認証設定、GitHub / Jira / Microsoft Teams の連携

### 社内横断のインフラとSRE

**2024年2月 - 現在**｜士業・医業｜準委任｜要件定義〜運用｜自社開発
**環境**: AWS, PHP, Aurora for MySQL / MySQL / MariaDB / PostgreSQL / Aurora Serverless, CDK (TypeScript), Terraform, Docker

複数プロダクトのインフラ全般を横断的に担当し、全社基盤の整備からインシデント対応までを一貫して推進。

**クラウドガバナンス（約45アカウント / 約5OU / 約100名の全社統制基盤を、レビュー者不在の環境で単独設計・移行）**

導入前は、長期アクセスキーを持つIAM Userが各自の判断で発行され、Admin権限が広く配られた状態だった。リージョン制限がなく、想定外のリージョンに把握されていないリソースも存在。さらにAWSリセラー経由の契約とリセラーを介さない契約が混在し、アカウント発行もサポート窓口もリセラー独自のフローに依存していたため、AWSの標準手順をそのまま適用できない前提があった。

- OU設計は、AWSの推奨構成を基準にしつつ、リセラー側の運用制約と社内の組織実態を突き合わせて決定。推奨構成をそのまま採用せず、既存の部門・環境の分かれ方に合う構成へ調整した
- 既存アカウントの移行は「リセラーへの対応依頼 → OU移行 → Enroll」の順で1アカウントずつ実施。取り込み前に各アカウントのリソースと使用リージョンを精査し、不要なものを整理したうえで移行した
- 既存アカウントに入っていたリセラー独自のセキュリティ設定を精査し、Control Tower / SecurityHub 側の統制へ付け替え
- ログ集約先が別アカウントになるため、既存ログ基盤の移設も併せて実施
- 設計をレビューできる担当者が社内にいなかったため、方針と判断理由を文書化して関係者に共有し、合意を取りながら進行
- OU、IAM Identity Centerのグループ・許可セット、SCPによる統制を設計し、Terraformで実装
- マルチアカウント管理のジャンプアカウントをIAM Roleで設計・構築
- IAM UserのPolicy / MFAの見直し、各種OIDC連携の導入
- IAM PolicyによるAWSリージョン制限（SCPの代替）
- IAM Identity Centerの利用方法を利用者へ周知。運用を別チームへ引き継ぐため、構成と運用手順を精査して引き渡した
- **成果**: 長期アクセスキーとAdmin権限の個別配布をやめ、IAM Identity Centerによる認証・権限付与へ一元化。利用リージョンを制限し、把握外のリソースが生まれない状態にした

**ソースコード管理（過去に断念されていた GitLab → GitHub Enterprise の全社移行を、150リポジトリ / 100名規模で完遂）**

社内に移行の要望は以前からあったものの、過去に着手して断念された経緯があった。参画後の最初のタスクとして引き受け、移行の実務担当は自分1名、かつ利用者の大半がGitHubの使用経験なしという制約があった。

- 移行前の棚卸しで、認証情報やトークン類がリポジトリの履歴に残り続けていることを発見。GitHubへ移す前に git-filter-repo で履歴から削除し、汚れた状態のまま新基盤へ持ち込まない形にした。履歴からの削除では漏洩した認証情報自体は無効化されないため、該当する認証情報のローテーションを所有チームへ案内した
- 一括ではなく段階移行を選択。担当が1名で、かつ利用者の大半がGitHub未経験だったため、運用の浸透と移行を並走させられる進め方にした
- 移行対象は履歴に絞り、CIは各チームへ引き継ぎ。自力で移せないものは個別に巻き取って対応した
- GitHub未経験者が大半だったため、使い方の周知とドキュメント整備をあわせて実施
- gitleaks を pre-commit と CI の両方に組み込み、ローカルをすり抜けた場合もCI側で検知できる形にした
- 複合アクション・再利用可能ワークフローで、AWS認証、PHPのフォーマッタ・リンタ・テスト、DBマイグレーションを共通化
- GitHub Enterprise導入、権限・ユーザー・リポジトリ・通知のルール設定、セキュリティおよび監査ログの設定
- Dependabot導入、Security UpdateによるPRベースブランチの自動変更
- Organizationの加入・脱退フローと運用ガイドラインを策定し、運用チームへ移管。Actions使用量の監視・通知を自動化
- **成果**: 過去に断念されていた全社移行を完遂。認証情報を履歴から除いたうえで新基盤へ移し、CIの共通部品化とルールの運用チームへの移管まで実施

**信頼性・可観測性**

- Incident Managerによるオンコール体制を構築
- CloudWatch Alarmによるメトリクス監視（EC2, ECS, RDS, Lambda等）
- ECS / RDS / ELB / Lambda の監視項目について社内ルールを策定し横展開
- EC2の自動リカバリー、RDSエラー時の自動リカバリーを実装
- スロークエリログの調査・対応および管理の仕組み化
- ポストモーテムの運用ルール策定と文化醸成
- AWS通知をChatworkからSlackへ移行（SQS + Lambdaによる自前実装 / AWS Chatbotの代替）

**セキュリティ・運用**

- AWSセキュリティ設定・運用・アラート対応（SecurityHub, GuardDuty等）
- S3ウイルススキャンの導入、AWS Healthによる障害・バージョンEOL検知
- バージョンアップ戦略の策定（MySQL, Lambda, PHP）
- EC2アクセスをSSHからSSMへ移行、CentOS7 EC2の延命対応
- メールサーバの改修（EC2, EFS, Route53, postfix, dovecot）、EFSによるEC2間ファイル共有
- ECSの各種インシデント対応、MySQLプロセスのタイムアウト対応
- AWS Budgets / Cost Anomaly Detectionによるコスト異常検知・調査、不要リソース削除

**IaC・CI/CD・開発基盤（インフラ専任のいないチームに合わせ、Terraformではなく CDK (TypeScript) を採用）**

社内にTerraformの使用実績がなく、一部でCloudFormationが使われている状態だった。プロジェクトにインフラ専任チームがなく、構築後はアプリ開発メンバーが触ることになるため、自分が普段使っているTerraformではなく、メンバーが慣れているTypeScriptで書けるCDKを提案し、合意を得て採用した。既存のCloudFormationはそのまま残し、新規構築をCDKに統一した。

- CDKによるインフラ構築、GitHub ActionsによるCI/CD、ESLint / PrettierによるCDKコード品質管理
- AWS初期設定のCDK + GitHub Actionsによる自動化
- PHP・Composer・Supervisorのデプロイ自動化、フロントエンド（Node.js）のCI/CD構築
- Dify セルフホスト基盤の構築（ECS, RDS, S3, Redis）およびワークフロー整備
- Lambdaのパフォーマンスチューニング、DataSyncによるS3オブジェクト大量移行、rcloneによるS3→Google Drive移行
- 社内インフラ全般の相談役

### 不動産契約システムのインフラ構築

**2023年1月 - 2025年9月**｜不動産｜準委任｜設計〜運用｜受託開発
**環境**: AWS, GCP, SPA, Aurora for MySQL / MySQL / Aurora Serverless, Terraform, SAM, Serverless Framework, Datadog, GitHub, Docker

複数プロダクトのインフラを並行して担当し、IaCツールの使い分けと監視基盤の構築を通じて運用性・可観測性を重視した設計を推進。

**監視・可観測性（監視基盤をゼロから設計・構築しTerraformでIaC化）**

- Integration / CloudWatch Streamsの設定、ログの出力・整理、Monitor・ダウンタイムの設定
- ECS上でのdatadog-agent / fluent-bit構成、トレース・プロファイラ・APMの導入
- ブラウザログ・ソースマップ・RUMによるフロントエンド可観測性の確立、Archiveの設定

**AWS / インフラ**

- AWS各種推奨設定の調査・検討・構築、SPA向けインフラの構築（CloudFront, S3）
- アプリのセキュリティ強化のためWAFを構築
- RDS for MySQL / Aurora for MySQLの構築、DBパラメータの見直し（文字コード、collation、ログ）
- MySQLのマイナーバージョンアップ対応と自動化、MySQL 5.7 → 8.0 のバージョンアップ対応
- IAM権限・IPアドレスの整理と構築、KMS / SSE-S3暗号化の見直し、Organizationsのセキュリティ統合
- メンテナンスモードの構築と自動化（EventBridge, Lambda, WebACL）、ECSロールバック対応
- 内部管理システムの作成（API Gateway, Lambda）、ETLの構築（Glue, Step Functions）、OIDCの導入
- 各種手作業をシェルスクリプトやLambda等で自動化

**GCP**

- BigQuery / Data Transferの構築、Looker Studioによるデータ分析の可視化

**IaC・開発基盤**

- Terraform / SAM / Serverless Framework を要件に応じて使い分けてインフラ構築
- 既存インフラを一通り terraform import でIaC化、全AWSアカウント共通設定のIaC化
- GitLab → GitHub移行、ブランチ・Gitフローの見直し
- CI/CD構築（GitLab CI, GitHub Actions, Terraform Cloud）、ログ（アクセスログ, CloudWatch）の設定
- localstack / DevContainerによるローカル開発環境の整備
- リリース手順書の作成、メンテナンスウィンドウの整備、各種インシデント対応

### 既存インフラの調査・改修 / DB性能改善

**2022年6月 - 2022年12月**｜人事・総務向けBtoB SaaS｜準委任｜調査・構築｜受託開発
**環境**: AWS, Python, Aurora (PostgreSQL), DynamoDB, SAM, Terraform, CloudFormation, SVN, GitHub

- **約400本のLambda**および関連するEventBridge / SQS / API Gatewayを調査・整理
- Aurora / DynamoDBの構成調査、インフラ全体構成図およびIF一覧の作成
- データの扱い・性能・CI/CDに関する改善提案資料を作成
- PostgreSQLの性能改善（BULK処理、パーティショニング）
- Network / Lambda / AWS Batch / EC2 / RDS / ECRの構築
- CI/CD構築（CodePipeline, CodeCommit, CodeBuild）、IaC（SAM, Terraform, CloudFormation）

### マッチングアプリのインフラ調査・AWS移行

**2022年7月 - 2022年12月**｜マッチングアプリ｜準委任｜調査〜構築｜受託開発
**環境**: AWS, CloudFormation, PHP, MariaDB, MySQL, Nginx, Apache, Haproxy, Zabbix, Docker, draw.io

オンプレLinux環境の調査からAWS移行までを、調査フェーズと構築フェーズの2期にわたって担当。

- 各サーバのミドルウェア（Nginx, Apache, Haproxy, Zabbix）および連携を調査し、全体構成図を作成
- キャッシュ・セッション管理、画像データ保有方式、cronの調査
- AWS移行における課題・リスク・対応策を洗い出し
- CloudFormationで移行先インフラを構築（VPC, Subnet, EC2, EFS, ALB, Route53, RDS）
- ミドルウェア設定（PHP, Apache）およびEC2設定（ロケール、マウント、シンボリックリンク）

### アプリケーション開発

**2021年7月 - 2022年6月**

インフラ・SRE専業に移行する以前は、Webおよび業務システムの開発を担当。上流のヒアリング・要件定義から実装まで経験。

| 期間 | 内容 | 環境 |
| --- | --- | --- |
| 2022/02 - 2022/06 | 報告書作成支援システムの新規開発。業務効率化のヒアリング・要件定義から、Python（OpenCV / python-docx）による画像処理・帳票処理、Google Vision APIによるOCR、Nuxt.jsでのフロントエンド実装、AWSインフラ構築まで担当 | Nuxt.js, Python (Django), Java (Apache POI), Aurora(MySQL), Nginx, Docker, Google Cloud |
| 2021/12 - 2022/04 | 物流会社の在庫管理システムのDX化。属人化した業務のヒアリングからWebアプリ・Windowsアプリの開発、AWSインフラ構築まで担当 | Python (Flask), C# (.NET Framework), Aurora(MySQL), Docker, Nginx |
| 2021/10 - 2022/02 | 建設会社向け業務効率化Windowsアプリの新規開発。RPAによる外部アプリ自動操作、Excel操作（Microsoft.Office.Interop.Excel）、DXFファイル操作、インストーラ作成 | C#, .NET Framework |
| 2021/07 - 2021/09 | ソーシャルゲームの新規・保守開発 | PHP (Laravel), MySQL(Aurora), Redis, AWS, GitLab, Vagrant, Apache |

---

## 職務経歴

| # | 企業名 | 期間 | 契約・雇用形態 | 担当職種 |
| --- | --- | --- | --- | --- |
| 1 | 個人事業主 | 2022/06 - 現在 | 準委任契約 | インフラ・SRE（自社開発、受託開発、インフラ構築） |
| 2 | 株式会社アンタス | 2021/09 - 2022/06 | 正社員 | バックエンド、インフラ、Windows（受託開発、業務効率化） |
| 3 | 株式会社インフィニットループ | 2021/07 - 2021/09 | アルバイト | フロントエンド、バックエンド（Webゲーム制作） |
| 4 | 株式会社三水コンサルタント | 2020/04 - 2021/01 | 正社員 | 技術者（コンサルティング、下水道計画）※ITエンジニア職ではありません |

## 自己PR

インフラの構築だけでなく、**組織全体の開発基盤をどう整えるか**という視点で仕事を進めることを重視しています。

AWS Control Towerの全社導入やGitHub Enterpriseへの移行では、技術的な設計・実装に加え、関係部署との調整、運用ルールの策定、運用チームへの引き継ぎまでを担当しました。導入して終わりではなく、**自分がいなくても回る状態を作る**ところまでを責任範囲と考えています。

また、規制やセキュリティ要件の厳しい業界（医療・士業・不動産）での経験が長く、セキュリティ統制とコスト最適化を両立させる設計を得意としています。技術選定においては、Terraform / CDK / CloudFormation / SAM を要件と組織のスキルセットに応じて使い分ける判断を重ねてきました。

## 基本情報・保有資格

| 項目 | 内容 |
| --- | --- |
| 氏名 | 木下 陸 |
| 生年 | 1997年 |
| 所在地 | 東京都渋谷区 |
| 学歴 | 国立大学法人 室蘭工業大学 建築社会基盤系学科 土木コース |

| 資格 | 取得 |
| --- | --- |
| AWS Certified Solutions Architect - Associate (SAA) | 2023/08 |
| AWS Certified Cloud Practitioner (CLF) | 2020/08 |
| ITパスポート | 2022/01 |

バッジ一覧: <https://www.credly.com/users/riku-kinoshita.ee2ca6f6/badges>
