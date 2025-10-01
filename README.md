# OWASP DevSecOps Guideline ja

This is the unofficial Japanese translation of the [OWASP DevSecOps Guideline](https://github.com/OWASP/DevSecOpsGuideline).

- Document Site - <https://coky-t.gitbook.io/owasp-devsecops-guideline-ja/>
- Document Repository - <https://github.com/coky-t/owasp-devsecops-guideline-ja>

### Originator

- Project Site - <https://owasp.org/www-project-devsecops-guideline/>
- Project Repository - <https://github.com/OWASP/www-project-devsecops-guideline>
- Document Repository - <https://github.com/OWASP/DevSecOpsGuideline>

## OWASP DevSecOps ガイドライン 日本語版

* [README](document/README.md)

### V0.3

- [0-概論 (Intro)](document/current-version/0-Intro)
  - [0-1-序文 (Intro)](document/current-version/0-Intro/0-1-Intro.md)
  - [0-2-概要 (Overview)](document/current-version/0-Intro/0-2-Overview.md)
- [1-要員 (People)](document/current-version/1-People)
  - [1-1-チーム形成 (Shape-the-team)](document/current-version/1-People/1-1-Shape-the-team)
    - [1-1-1-セキュリティチャンピオン (Security-champions)](document/current-version/1-People/1-1-Shape-the-team/1-1-1-Security-champions.md)
  - [1-2-トレーニング (Training)](document/current-version/1-People/1-2-Training)
    - [1-2-1-セキュアコーディング (Secure-coding)](document/current-version/1-People/1-2-Training/1-2-1-Secure-coding.md)
    - [1-2-2-セキュリティ CI/CD (Security-CICD)](document/current-version/1-People/1-2-Training/1-2-2-Security-CICD.md)
- [2-プロセス (Process)](document/current-version/2-Process)
  - [2-1-設計 (Design)](document/current-version/2-Process/2-1-Design)
    - [2-1-1-脅威モデリング (Threat-modeling)](document/current-version/2-Process/2-1-Design/2-1-1-Threat-modeling.md)
  - [2-2-開発 (Develop)](document/current-version/2-Process/2-2-Develop)
    - [2-2-1-コミット前 (Pre-commit)](document/current-version/2-Process/2-2-Develop/2-2-1-Pre-commit)
      - [2-2-1-1-プレコミット (Pre-commit)](document/current-version/2-Process/2-2-Develop/2-2-1-Pre-commit/2-2-1-1-Pre-commit.md)
      - [2-2-1-2-シークレット管理 (Secrets-Management)](document/current-version/2-Process/2-2-Develop/2-2-1-Pre-commit/2-2-1-2-Secrets-Management.md)
      - [2-2-1-3-コードのリンティング (Linting-code)](document/current-version/2-Process/2-2-Develop/2-2-1-Pre-commit/2-2-1-3-Linting-code.md)
      - [2-2-1-4-リポジトリ堅牢化 (Repository-Hardening)](document/current-version/2-Process/2-2-Develop/2-2-1-Pre-commit/2-2-1-4-Repository-Hardening.md)
  - [2-3-ビルド (Build)](document/current-version/2-Process/2-3-Build)
    - [2-3-5-セキュリティゲート (Security-Gates)](document/current-version/2-Process/2-3-Build/2-3-5-Security-Gates.md)
    - [2-3-1-静的解析 (Static-Analysis)](document/current-version/2-Process/2-3-Build/2-3-1-Static-Analysis)
      - [2-3-1-1-静的アプリケーションセキュリティテスト (Static-Application-Security-Testing)](document/current-version/2-Process/2-3-Build/2-3-1-Static-Analysis/2-3-1-1-Static-Application-Security-Testing.md)
    - [2-3-2-ソフトウェアコンポジション解析 (Software Composition Analysis)](document/current-version/2-Process/2-3-Build/2-3-2-Software%20Composition%20Analysis)
      - [2-3-2-1-ソフトウェアコンポジション解析 (Software-Composition-Analysis)](document/current-version/2-Process/2-3-Build/2-3-2-Software%20Composition%20Analysis/2-3-2-1-Software-Composition-Analysis.md)
    - [2-3-3-コンテナセキュリティ (Container-Security)](document/current-version/2-Process/2-3-Build/2-3-3-Container-Security)
      - [2-3-3-1-コンテナスキャン (Container-Scanning)](document/current-version/2-Process/2-3-Build/2-3-3-Container-Security/2-3-3-1-Container-Scanning.md)
      - [2-3-3-2-コンテナ堅牢化 (Container-Hardening)](document/current-version/2-Process/2-3-Build/2-3-3-Container-Security/2-3-3-2-Container-Hardening.md)
    - [2-3-4-Infastructure as Code セキュリティ (Infrastructure as Code Security)](document/current-version/2-Process/2-3-Build/2-3-4-Infrastructure%20as%20Code%20Security)
      - [2-3-1-3-Infastructure as Code スキャン (Infastructure-as-Code-Scanning)](document/current-version/2-Process/2-3-Build/2-3-4-Infrastructure%20as%20Code%20Security/2-3-1-3-Infastructure-as-Code-Scanning.md)
  - [2-4-テスト (Test)](document/current-version/2-Process/2-4-Test)
    - [2-4-1-インタラクティブアプリケーションセキュリティテスト (Interactive-Application-Security-Testing)](document/current-version/2-Process/2-4-Test/2-4-1-Interactive-Application-Security-Testing.md)
    - [2-4-2-動的アプリケーションセキュリティテスト (Dynamic-Application-Security-Testing)](document/current-version/2-Process/2-4-Test/2-4-2-Dynamic-Application-Security-Testing.md)
    - [2-4-3-モバイルアプリケーションセキュリティテスト (Mobile-Application-Security-Test)](document/current-version/2-Process/2-4-Test/2-4-3-Mobile-Application-Security-Test.md)
    - [2-4-4-API セキュリティ (API-Security)](document/current-version/2-Process/2-4-Test/2-4-4-API-Security.md)
    - [2-4-5-構成ミスチェック (Misconfiguration-Check)](document/current-version/2-Process/2-4-Test/2-4-5-Misconfiguration-Check.md)
  - [2-5-リリース (Release)](document/current-version/2-Process/2-5-Release)
    - [2-5-1-リリース (Release)](document/current-version/2-Process/2-5-Release/2-5-1-Release.md)
  - [2-6-デプロイ (Deploy)](document/current-version/2-Process/2-6-Deploy)
    - [2-6-1-デプロイ (Deploy)](document/current-version/2-Process/2-6-Deploy/2-6-1-Deploy.md)
  - [2-7-運用 (Operate)](document/current-version/2-Process/2-7-Operate)
    - [2-7-1-クラウドネイティブセキュリティ (Cloud-Native-Security)](document/current-version/2-Process/2-7-Operate/2-7-1-Cloud-Native-Security.md)
    - [2-7-2-ログ記録と監視 (Logging-and-Monitoring)](document/current-version/2-Process/2-7-Operate/2-7-2-Logging-and-Monitoring.md)
    - [2-7-3-ペンテスト (Pentest)](document/current-version/2-Process/2-7-Operate/2-7-3-Pentest.md)
    - [2-7-4-脆弱性管理 (Vulnerability-Management)](document/current-version/2-Process/2-7-Operate/2-7-4-Vulnerability-Management.md)
    - [2-7-6-侵害と攻撃のシミュレーション (Breach-and-attack-simulation)](document/current-version/2-Process/2-7-Operate/2-7-6-Breach-and-attack-simulation.md)
- [3-ガバナンス (Governance)](document/current-version/3-Governance)
  - [3-2-データ保護 (Data-protection)](document/current-version/3-Governance/3-2-Data-protection.md)
  - [3-1-コンプライアンス監査 (Compliance-Auditing)](document/current-version/3-Governance/3-1-Compliance-Auditing)
    - [3-1-1-コンプライアンス監査 (Compliance-Auditing)](document/current-version/3-Governance/3-1-Compliance-Auditing/3-1-1-Compliance-Auditing.md)
    - [3-1-2-Policy as Code (Policy-as-code)](document/current-version/3-Governance/3-1-Compliance-Auditing/3-1-2-Policy-as-code.md)
    - [3-1-3-セキュリティベンチマーク (Security-benchmarking)](document/current-version/3-Governance/3-1-Compliance-Auditing/3-1-3-Security-benchmarking.md)
  - [3-3-レポーティング (Reporting)](document/current-version/3-Governance/3-3-Reporting)
    - [3-3-1-成熟度追跡 (Tracking-maturities)](document/current-version/3-Governance/3-3-Reporting/3-3-1-Tracking-maturities.md)
    - [3-3-2-脆弱性一元管理ダッシュボード (Central-vulnerability-management-dashboard)](document/current-version/3-Governance/3-3-Reporting/3-3-2-Central-vulnerability-management-dashboard.md)

### V0.2

- [0-概論 (Intro)](document/old-versions/V0.2/0-Intro)
  - [0-1-序文 (Intro)](document/old-versions/V0.2/0-Intro/0-1-Intro.md)
  - [0-2-概要 (Overview)](document/old-versions/V0.2/0-Intro/0-2-Overview.md)
- [1-導入 (Init)](document/old-versions/V0.2/1-Init)
  - [1-1-チーム形成 (Shape-the-team)](document/old-versions/V0.2/1-Init/1-1-Shape-the-team)
    - [1-1-1-セキュリティ担当者 (Security-champions)](document/old-versions/V0.2/1-Init/1-1-Shape-the-team/1-1-1-Security-champions.md)
  - [1-2-トレーニング (Training)](document/old-versions/V0.2/1-Init/1-2-Training)
    - [1-2-1-セキュアコーディング (Secure-coding)](document/old-versions/V0.2/1-Init/1-2-Training/1-2-1-Secure-coding.md)
    - [1-2-2-セキュリティ CI/CD (Security-CICD)](document/old-versions/V0.2/1-Init/1-2-Training/1-2-1-Security-CICD.md)
- [2-コミット前 (Pre-commit)](document/old-versions/V0.2/2-Pre-commit)
  - [2-1-プレコミット (Pre-commit)](document/old-versions/V0.2/2-Pre-commit/2-1-Pre-commit.md)
  - [2-2-脅威モデリング (Threat-modeling)](document/old-versions/V0.2/2-Pre-commit/2-2-Threat-modeling.md)
  - [2-3-リポジトリ堅牢化 (Repository-hardening)](document/old-versions/V0.2/2-Pre-commit/2-3-Repository-hardening.md)
  - [2-4-シークレット管理 (Secrets-Management)](document/old-versions/V0.2/2-Pre-commit/2-4-Secrets-Management.md)
  - [2-5-コードのリンティング (Linting-code)](document/old-versions/V0.2/2-Pre-commit/2-5-Linting-code.md)
- [3-コミット CI (Commit-CI)](document/old-versions/V0.2/3-Commit-CI)
  - [3-2-インタラクティブアプリケーションセキュリティテスト (Interactive-Application-Security-Testing)](document/old-versions/V0.2/3-Commit-CI/3-2-Interactive-Application-Security-Testing.md)
  - [3-1-静的解析 (Static-analysis)](document/old-versions/V0.2/3-Commit-CI/3-1-Static-analysis)
    - [3-1-1-静的アプリケーションセキュリティテスト (Static-Application-Security-Testing)](document/old-versions/V0.2/3-Commit-CI/3-1-Static-analysis/3-1-1-Static-Application-Security-Testing.md)
    - [3-1-2-ソフトウェアコンポジション解析 (Software-Composition-Analysis)](document/old-versions/V0.2/3-Commit-CI/3-1-Static-analysis/3-1-2-Software-Composition-Analysis.md)
    - [3-1-3-コンテナセキュリティ (Container-Security)](document/old-versions/V0.2/3-Commit-CI/3-1-Static-analysis/3-1-3-Container-Security)
      - [3-1-3-1-コンテナスキャン (Container-scanning)](document/old-versions/V0.2/3-Commit-CI/3-1-Static-analysis/3-1-3-Container-Security/3-1-3-1-Container-scanning.md)
      - [3-1-3-2-コンテナ堅牢化 (Container-hardening)](document/old-versions/V0.2/3-Commit-CI/3-1-Static-analysis/3-1-3-Container-Security/3-1-3-2-Container-hardening.md)
    - [3-1-4-Infastructure as Code (Infastructure-as-code)](document/old-versions/V0.2/3-Commit-CI/3-1-Static-analysis/3-1-4-Infastructure-as-code.md)
- [4-継続的デリバリ CD (Continuous-delivery-CD)](document/old-versions/V0.2/4-Continuous-delivery-CD)
  - [4-1-動的アプリケーションセキュリティテスト (Dynamic-Application-Security-Testing)](document/old-versions/V0.2/4-Continuous-delivery-CD/4-1-Dynamic-Application-Security-Testing.md)
  - [4-2-モバイルアプリケーションセキュリティテスト (Mobile-Application-Security-Test)](document/old-versions/V0.2/4-Continuous-delivery-CD/4-2-Mobile-Application-Security-Test.md)
  - [4-3-API セキュリティ (API-Security)](document/old-versions/V0.2/4-Continuous-delivery-CD/4-3-API-Security.md)
  - [4-4-設定ミスのチェック (Miss-Configuration-Check)](document/old-versions/V0.2/4-Continuous-delivery-CD/4-4-Miss-Configuration-Check.md)
- [5-デプロイ CD 稼働開始 (Deploy-CD-Golive)](document/old-versions/V0.2/5-Deploy-CD-Golive)
  - [5-1-鍵と証明書の管理 (Key-and-certificate-management)](document/old-versions/V0.2/5-Deploy-CD-Golive/5-1-Key-and-certificate-management.md)
  - [5-2-クラウドネイティブアプリケーション保護プラットフォーム (Cloud-Native-Application-Protection-Platform)](document/old-versions/V0.2/5-Deploy-CD-Golive/5-2-Cloud-Native-Application-Protection-Platform.md)
- [6-運用 (Operation)](document/old-versions/V0.2/6-Operation)
  - [6-1-稼働時テスト|継続的テスト (Runtime|Continuous-test)](document/old-versions/V0.2/6-Operation/6-1-Runtime|Continuous-test)
    - [6-1-1-インフラスキャン (Infra-scanning)](document/old-versions/V0.2/6-Operation/6-1-Runtime|Continuous-test/6-1-1-Infra-scanning)
      - [6-1-1-1-クラウドリソース (Could-resources)](document/old-versions/V0.2/6-Operation/6-1-Runtime|Continuous-test/6-1-1-Infra-scanning/6-1-1-1-Could-resources.md)
      - [6-1-1-2-K8S リソース (K8S-resources)](document/old-versions/V0.2/6-Operation/6-1-Runtime|Continuous-test/6-1-1-Infra-scanning/6-1-1-2-K8S-resources.md)
    - [6-1-2-イメージスキャン (Image-scanning)](document/old-versions/V0.2/6-Operation/6-1-Runtime|Continuous-test/6-1-2-Image-scanning.md)  
  - [6-2-侵害と攻撃のシミュレーション (Breach-and-attack-simulation)](document/old-versions/V0.2/6-Operation/6-2-Breach-and-attack-simulation.md)
  - [6-3-ログ記録と監視 (Logging-and-Monitoring)](document/old-versions/V0.2/6-Operation/6-3-Logging-and-Monitoring.md)
  - [6-4-ペンテスト (Pentest)](document/old-versions/V0.2/6-Operation/6-4-Pentest.md)
  - [6-5-脆弱性開示ポリシーとバグバウンティ (VDP|Bug-bounty)](document/old-versions/V0.2/6-Operation/6-5-VDP_Bug-bounty.md)
- [7-ガバナンス (Governance)](document/old-versions/V0.2/7-Governance)
  - [7-1-コンプライアンス監査 (Compliance-Auditing)](document/old-versions/V0.2/7-Governance/7-1-Compliance-Auditing)
    - [7-1-1-コンプライアンス監査 (Compliance-Auditing)](document/old-versions/V0.2/7-Governance/7-1-Compliance-Auditing/7-1-1-Compliance-Auditing.md)
    - [7-1-2-Policy as Code (Policy-as-code)](document/old-versions/V0.2/7-Governance/7-1-Compliance-Auditing/7-1-2-Policy-as-code.md)
    - [7-1-3-セキュリティベンチマーク (Security-benchmarking)](document/old-versions/V0.2/7-Governance/7-1-Compliance-Auditing/7-1-3-Security-benchmarking.md)
  - [7-2-データ保護 (Data-protection)](document/old-versions/V0.2/7-Governance/7-2-Data-protection.md)
  - [7-3-レポーティング (Reporting)](document/old-versions/V0.2/7-Governance/7-3-Reporting)
    - [7-3-1-成熟度追跡 (Tracking-maturities)](document/old-versions/V0.2/7-Governance/7-3-Reporting/7-3-1-Tracking-maturities.md)
    - [7-3-2-脆弱性一元管理ダッシュボード (Central-vulnerability-management-dashboard)](document/old-versions/V0.2/7-Governance/7-3-Reporting/7-3-2-Central-vulnerability-management-dashboard.md)

### V0.1

* [00. OWASP DevSecOps ガイドラインの概要](document/old-versions/V0.1/00-Intro.md)
* [00a. DevSecOps 入門](document/old-versions/V0.1/00a-Overview.md)
* [00b. 脅威モデリング](document/old-versions/V0.1/00b-Threat-modeling.md)
* [01. コミット前に](document/old-versions/V0.1/01-Pre-commit.md)
* [01a. シークレットとクレデンシャルに注意](document/old-versions/V0.1/01a-Secrets-Management.md)
* [01b. コードのリンティング](document/old-versions/V0.1/01b-Linting-Code.md)
* [02. 脆弱性スキャン](document/old-versions/V0.1/02-Vulnerability-Scanning.md)
* [02a. 静的スキャンはプロセスの重要な部分](document/old-versions/V0.1/02a-Static-Application-Security-Testing.md)
* [02b. 動的アプリケーションセキュリティテスト (DAST)](document/old-versions/V0.1/02b-Dynamic-Application-Security-Testing.md)
* [02c. インタラクティブアプリケーションセキュリティテスト](document/old-versions/V0.1/02c-Interactive-Application-Security-Testing.md)
* [02d. ソフトウェアコンポーネント/コンポジション解析 (SCA)](document/old-versions/V0.1/02d-Software-Composition-Analysis.md)
* [02e. インフラストラクチャ脆弱性スキャン](document/old-versions/V0.1/02e-Infrastructure-Vulnerability-Scanning.md)
* [02f. コンテナ脆弱性スキャン](document/old-versions/V0.1/02f-Container-Vulnerability-Scanning.md)
* [02g. プライバシー](document/old-versions/V0.1/02g-Privacy.md)
* [02h. 脆弱性の一元管理](document/old-versions/V0.1/02h-Vulnerability-Management.md)
* [03. コンプライアンス監査](document/old-versions/V0.1/03-Compliance-Auditing.md)

## License

[Creative Commons Attribution-ShareAlike 4.0 International](https://creativecommons.org/licenses/by-sa/4.0/)

## Translator (Japanese)

[Koki Takeyama](https://github.com/coky-t)

- Document Site - <https://coky-t.gitbook.io/owasp-docs-ja/>
- Document Repository - <https://github.com/coky-t/owasp-docs-ja>
