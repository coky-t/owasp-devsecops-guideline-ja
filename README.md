# OWASP DevSecOps Guideline ja

This is the unofficial Japanese translation of the [OWASP DevSecOps Guideline](https://github.com/OWASP/DevSecOpsGuideline).

### Originator

- Project Site - <https://owasp.org/www-project-devsecops-guideline/>
- Project Repository - <https://github.com/OWASP/www-project-devsecops-guideline>
- Document Repository - <https://github.com/OWASP/DevSecOpsGuideline>

## OWASP DevSecOps ガイドライン 日本語版

* [README](document/README.md)

### 新版

- [0-概論 (Intro)](document/documents/0-Intro)
  - [0-1-序文 (Intro)](document/documents/0-Intro/0-1-Intro.md)
  - [0-2-概要 (Overview)](document/documents/0-Intro/0-2-Overview.md)
- [1-導入 (Init)](document/documents/1-Init)
  - [1-1-チーム形成 (Shape-the-team)](document/documents/1-Init/1-1-Shape-the-team)
    - [1-1-1-セキュリティ担当者 (Security-champions)](document/documents/1-Init/1-1-Shape-the-team/1-1-1-Security-champions.md)
  - [1-2-トレーニング (Training)](document/documents/1-Init/1-2-Training)
    - [1-2-1-セキュアコーディング (Secure-coding)](document/documents/1-Init/1-2-Training/1-2-1-Secure-coding.md)
    - [1-2-2-セキュリティ CI/CD (Security-CICD)](document/documents/1-Init/1-2-Training/1-2-1-Security-CICD.md)
- [2-コミット前 (Pre-commit)](document/documents/2-Pre-commit)
  - [2-1-プレコミット (Pre-commit)](document/documents/2-Pre-commit/2-1-Pre-commit.md)
  - [2-2-脅威モデリング (Threat-modeling)](document/documents/2-Pre-commit/2-2-Threat-modeling.md)
  - [2-3-リポジトリ堅牢化 (Repository-hardening)](document/documents/2-Pre-commit/2-3-Repository-hardening.md)
  - [2-4-シークレット管理 (Secrets-Management)](document/documents/2-Pre-commit/2-4-Secrets-Management.md)
  - [2-5-コードのリンティング (Linting-code)](document/documents/2-Pre-commit/2-5-Linting-code.md)
- [3-コミット CI (Commit-CI)](document/documents/3-Commit-CI)
  - [3-2-インタラクティブアプリケーションセキュリティテスト (Interactive-Application-Security-Testing)](document/documents/3-Commit-CI/3-2-Interactive-Application-Security-Testing.md)
  - [3-1-静的解析 (Static-analysis)](document/documents/3-Commit-CI/3-1-Static-analysis)
    - [3-1-1-静的アプリケーションセキュリティテスト (Static-Application-Security-Testing)](document/documents/3-Commit-CI/3-1-Static-analysis/3-1-1-Static-Application-Security-Testing.md)
    - [3-1-2-ソフトウェアコンポジション解析 (Software-Composition-Analysis)](document/documents/3-Commit-CI/3-1-Static-analysis/3-1-2-Software-Composition-Analysis.md)
    - [3-1-3-コンテナセキュリティ (Container-Security)](document/documents/3-Commit-CI/3-1-Static-analysis/3-1-3-Container-Security)
      - [3-1-3-1-コンテナスキャン (Container-scanning)](document/documents/3-Commit-CI/3-1-Static-analysis/3-1-3-Container-Security/3-1-3-1-Container-scanning.md)
      - [3-1-3-2-コンテナ堅牢化 (Container-hardening)](document/documents/3-Commit-CI/3-1-Static-analysis/3-1-3-Container-Security/3-1-3-2-Container-hardening.md)
    - [3-1-4-Infastructure as Code (Infastructure-as-code)](document/documents/3-Commit-CI/3-1-Static-analysis/3-1-4-Infastructure-as-code.md)
- [4-継続的デリバリ CD (Continuous-delivery-CD)](document/documents/4-Continuous-delivery-CD)
  - [4-1-動的アプリケーションセキュリティテスト (Dynamic-Application-Security-Testing)](document/documents/4-Continuous-delivery-CD/4-1-Dynamic-Application-Security-Testing.md)
  - [4-2-モバイルアプリケーションセキュリティテスト (Mobile-Application-Security-Test)](document/documents/4-Continuous-delivery-CD/4-2-Mobile-Application-Security-Test.md)
  - [4-3-API セキュリティ (API-Security)](document/documents/4-Continuous-delivery-CD/4-3-API-Security.md)
  - [4-4-設定ミスのチェック (Miss-Configuration-Check)](document/documents/4-Continuous-delivery-CD/4-4-Miss-Configuration-Check.md)
- [5-デプロイ CD 稼働開始 (Deploy-CD-Golive)](document/documents/5-Deploy-CD-Golive)
  - [5-1-鍵と証明書の管理 (Key-and-certificate-management)](document/documents/5-Deploy-CD-Golive/5-1-Key-and-certificate-management.md)
  - [5-2-クラウドネイティブアプリケーション保護プラットフォーム (Cloud-Native-Application-Protection-Platform)](document/documents/5-Deploy-CD-Golive/5-2-Cloud-Native-Application-Protection-Platform.md)
- [6-運用 (Operation)](document/documents/6-Operation)
  - [6-1-稼働時テスト|継続的テスト (Runtime|Continuous-test)](document/documents/6-Operation/6-1-Runtime|Continuous-test)
    - [6-1-1-インフラスキャン (Infra-scanning)](document/documents/6-Operation/6-1-Runtime|Continuous-test/6-1-1-Infra-scanning)
      - [6-1-1-1-クラウドリソース (Could-resources)](document/documents/6-Operation/6-1-Runtime|Continuous-test/6-1-1-Infra-scanning/6-1-1-1-Could-resources.md)
      - [6-1-1-2-K8S リソース (K8S-resources)](document/documents/6-Operation/6-1-Runtime|Continuous-test/6-1-1-Infra-scanning/6-1-1-2-K8S-resources.md)
    - [6-1-2-イメージスキャン (Image-scanning)](document/documents/6-Operation/6-1-Runtime|Continuous-test/6-1-2-Image-scanning.md)  
  - [6-2-侵害と攻撃のシミュレーション (Breach-and-attack-simulation)](document/documents/6-Operation/6-2-Breach-and-attack-simulation.md)
  - [6-3-ログ記録と監視 (Logging-and-Monitoring)](document/documents/6-Operation/6-3-Logging-and-Monitoring.md)
  - [6-4-ペンテスト (Pentest)](document/documents/6-Operation/6-4-Pentest.md)
  - [6-5-脆弱性開示ポリシーとバグバウンティ (VDP|Bug-bounty)](document/documents/6-Operation/6-5-VDP|Bug-bounty.md)
- [7-ガバナンス (Governance)](document/documents/7-Governance)
  - [7-1-コンプライアンス監査 (Compliance-Auditing)](document/documents/7-Governance/7-1-Compliance-Auditing)
    - [7-1-1-コンプライアンス監査 (Compliance-Auditing)](document/documents/7-Governance/7-1-Compliance-Auditing/7-1-1-Compliance-Auditing.md)
    - [7-1-2-Policy as Code (Policy-as-code)](document/documents/7-Governance/7-1-Compliance-Auditing/7-1-2-Policy-as-code.md)
    - [7-1-3-セキュリティベンチマーク (Security-benchmarking)](document/documents/7-Governance/7-1-Compliance-Auditing/7-1-3-Security-benchmarking.md)
  - [7-2-データ保護 (Data-protection)](document/documents/7-Governance/7-2-Data-protection.md)
  - [7-3-レポーティング (Reporting)](document/documents/7-Governance/7-3-Reporting)
    - [7-3-1-成熟度追跡 (Tracking-maturities)](document/documents/7-Governance/7-3-Reporting/7-3-1-Tracking-maturities.md)
    - [7-3-2-脆弱性一元管理ダッシュボード (Central-vulnerability-management-dashboard)](document/documents/7-Governance/7-3-Reporting/7-3-2-Central-vulnerability-management-dashboard.md)

### 旧版

* [00. OWASP DevSecOps ガイドラインの概要](document/document-old-structure/00-Intro.md)
* [00a. DevSecOps 入門](document/document-old-structure/00a-Overview.md)
* [00b. 脅威モデリング](document/document-old-structure/00b-Threat-modeling.md)
* [01. コミット前に](document/document-old-structure/01-Pre-commit.md)
* [01a. シークレットとクレデンシャルに注意](document/document-old-structure/01a-Secrets-Management.md)
* [01b. コードのリンティング](document/document-old-structure/01b-Linting-Code.md)
* [02. 脆弱性スキャン](document/document-old-structure/02-Vulnerability-Scanning.md)
* [02a. 静的スキャンはプロセスの重要な部分](document/document-old-structure/02a-Static-Application-Security-Testing.md)
* [02b. 動的アプリケーションセキュリティテスト (DAST)](document/document-old-structure/02b-Dynamic-Application-Security-Testing.md)
* [02c. インタラクティブアプリケーションセキュリティテスト](document/document-old-structure/02c-Interactive-Application-Security-Testing.md)
* [02d. ソフトウェアコンポーネント/コンポジション解析 (SCA)](document/document-old-structure/02d-Software-Composition-Analysis.md)
* [02e. インフラストラクチャ脆弱性スキャン](document/document-old-structure/02e-Infrastructure-Vulnerability-Scanning.md)
* [02f. コンテナ脆弱性スキャン](document/document-old-structure/02f-Container-Vulnerability-Scanning.md)
* [02g. プライバシー](document/document-old-structure/02g-Privacy.md)
* [02h. 脆弱性の一元管理](document/document-old-structure/02h-Vulnerability-Management.md)
* [03. コンプライアンス監査](document/document-old-structure/03-Compliance-Auditing.md)

## Author (日本語訳)

[Koki Takeyama](https://github.com/coky-t)
