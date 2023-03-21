# OWASP DevSecOps ガイドライン
OWASP DevSecOps ガイドラインはどのようにしてセキュアなパイプラインを実装するかを説明し、ベストプラクティスを使用し、この事象に使用できるツールを紹介します。また、このプロジェクトは開発プロセスにおいてシフトレフトのセキュリティ文化を促進することに役立てようとしています。
このプロジェクトは開発パイプライン、つまり DevOps パイプラインを持つあらゆる規模の企業に役立ちます。
このプロジェクトでは、セキュアな DevOps パイプラインの展望を描き、カスタマイズされた要件に基づいてそれを改善していきます。

理想とする目標は **"(設計やアプリケーションの脆弱性による) セキュリティ問題をできるだけ早く検出すること"** です。

## 最初のステップ
DevSecOps とは DevOps にセキュリティを取り込むことです。しかし CI/CD のペースに追いつくためにはソフトウェア作成やテストの初期段階でセキュリティを注入する必要があります。

![DevSecOps cycle](/assets/images/DevSecOps-cycle.png)

[OWASP プロアクティブコントロール](https://owasp.org/www-project-proactive-controls/) にはすべての開発者がアプリケーションをコーディングする際に実装しなければならないセキュリティコントロールのトップ 10 をリストしています。このセットは DevSecOps サイクルでコードを設計、記述、またはテストしなければならないときの出発点と考えてください。

また [OWASP ソフトウエアセキュリティ保証成熟度モデル (Software Assurance Maturity Model, SAMM)](https://owaspsamm.org/model/) にしたがって、成熟度に応じたセキュリティ要件 (およびその他) に対して考慮すべきことを確立することができます。

## パイプラインに追加するもの
![DevSecOps pipeline](/assets/images/DevSecOps-pipeline.png)
最初に、基本的なパイプラインに以下のステップを実装することを検討します。
* 潜在的なクレデンシャルの漏洩を発見するために git リポジトリをスキャンする
* SCA (ソフトウェアコンポジション解析)
* SAST (静的アプリケーションセキュリティテスト)
* IaC スキャン (Terraform, HelmChart コードをスキャンして設定ミスを発見する)
* IAST (インタラクティブアプリケーションセキュリティテスト)
* API セキュリティ
* DAST (動的アプリケーションセキュリティテスト)
* CNAPP (クラウドネイティブアプリケーション保護)
* インフラストラクチャスキャン
* 他のツールからの継続的なスキャン
* コンプライアンスチェック

ソフトウェア開発ライフサイクル (SDLC) やソフトウェアアーキテクチャにしたがってパイプラインのステップをカスタマイズし、始めていれば段階的に自動化を追加することができます。
たとえば SAST/DAST からセキュリティコントロールが組み込まれた通常のテストスイートに切り替えたり、既知の脆弱な依存関係をチェックする監査スクリプトを追加することができます。

CI/CD は SecOps にとって有利であり、セキュリティ対策やコントロールのための特権的なエントリポイントとなります。
ただし、CI/CD ツールを使用して自動化を行う場合にはツール自体が攻撃対象領域を拡大することがよくあることに注意します。そのため、ソフトウェアのビルド、デプロイメント、および自動化にセキュリティコントロールを配置します。

---
## 目次:

- [0-概論 (Intro)](documents/0-Intro)
  - [0-1-序文 (Intro)](documents/0-Intro/0-1-Intro.md)
  - [0-2-概要 (Overview)](documents/0-Intro/0-2-Overview.md)
- [1-導入 (Init)](documents/1-Init)
  - [1-1-チーム形成 (Shape-the-team)](documents/1-Init/1-1-Shape-the-team)
    - [1-1-1-セキュリティ担当者 (Security-champions)](documents/1-Init/1-1-Shape-the-team/1-1-1-Security-champions.md)
  - [1-2-トレーニング (Training)](documents/1-Init/1-2-Training)
    - [1-2-1-セキュアコーディング (Secure-coding)](documents/1-Init/1-2-Training/1-2-1-Secure-coding.md)
    - [1-2-2-セキュリティ CI/CD (Security-CICD)](documents/1-Init/1-2-Training/1-2-1-Security-CICD.md)
- [2-コミット前 (Pre-commit)](documents/2-Pre-commit)
  - [2-1-プレコミット (Pre-commit)](documents/2-Pre-commit/2-1-Pre-commit.md)
  - [2-2-脅威モデリング (Threat-modeling)](documents/2-Pre-commit/2-2-Threat-modeling.md)
  - [2-3-リポジトリ堅牢化 (Repository-hardening)](documents/2-Pre-commit/2-3-Repository-hardening.md)
  - [2-4-シークレット管理 (Secrets-Management)](documents/2-Pre-commit/2-4-Secrets-Management.md)
  - [2-5-コードのリンティング (Linting-code)](documents/2-Pre-commit/2-5-Linting-code.md)
- [3-コミット CI (Commit-CI)](documents/3-Commit-CI)
  - [3-2-インタラクティブアプリケーションセキュリティテスト (Interactive-Application-Security-Testing)](documents/3-Commit-CI/3-2-Interactive-Application-Security-Testing.md)
  - [3-1-静的解析 (Static-analysis)](documents/3-Commit-CI/3-1-Static-analysis)
    - [3-1-1-静的アプリケーションセキュリティテスト (Static-Application-Security-Testing)](documents/3-Commit-CI/3-1-Static-analysis/3-1-1-Static-Application-Security-Testing.md)
    - [3-1-2-ソフトウェアコンポジション解析 (Software-Composition-Analysis)](documents/3-Commit-CI/3-1-Static-analysis/3-1-2-Software-Composition-Analysis.md)
    - [3-1-3-コンテナセキュリティ (Container-Security)](documents/3-Commit-CI/3-1-Static-analysis/3-1-3-Container-Security)
      - [3-1-3-1-コンテナスキャン (Container-scanning)](documents/3-Commit-CI/3-1-Static-analysis/3-1-3-Container-Security/3-1-3-1-Container-scanning.md)
      - [3-1-3-2-コンテナ堅牢化 (Container-hardening)](documents/3-Commit-CI/3-1-Static-analysis/3-1-3-Container-Security/3-1-3-2-Container-hardening.md)
    - [3-1-4-Infastructure as Code (Infastructure-as-code)](documents/3-Commit-CI/3-1-Static-analysis/3-1-4-Infastructure-as-code.md)
- [4-継続的デリバリ CD (Continuous-delivery-CD)](documents/4-Continuous-delivery-CD)
  - [4-1-動的アプリケーションセキュリティテスト (Dynamic-Application-Security-Testing)](documents/4-Continuous-delivery-CD/4-1-Dynamic-Application-Security-Testing.md)
  - [4-2-モバイルアプリケーションセキュリティテスト (Mobile-Application-Security-Test)](documents/4-Continuous-delivery-CD/4-2-Mobile-Application-Security-Test.md)
  - [4-3-API セキュリティ (API-Security)](documents/4-Continuous-delivery-CD/4-3-API-Security.md)
  - [4-4-設定ミスのチェック (Miss-Configuration-Check)](documents/4-Continuous-delivery-CD/4-4-Miss-Configuration-Check.md)
- [5-デプロイ CD 稼働開始 (Deploy-CD-Golive)](documents/5-Deploy-CD-Golive)
  - [5-1-鍵と証明書の管理 (Key-and-certificate-management)](documents/5-Deploy-CD-Golive/5-1-Key-and-certificate-management.md)
  - [5-2-クラウドネイティブアプリケーション保護プラットフォーム (Cloud-Native-Application-Protection-Platform)](documents/5-Deploy-CD-Golive/5-2-Cloud-Native-Application-Protection-Platform.md)
- [6-運用 (Operation)](documents/6-Operation)
  - [6-1-稼働時テスト|継続的テスト (Runtime|Continuous-test)](documents/6-Operation/6-1-Runtime|Continuous-test)
    - [6-1-1-インフラスキャン (Infra-scanning)](documents/6-Operation/6-1-Runtime|Continuous-test/6-1-1-Infra-scanning)
      - [6-1-1-1-クラウドリソース (Could-resources)](documents/6-Operation/6-1-Runtime|Continuous-test/6-1-1-Infra-scanning/6-1-1-1-Could-resources.md)
      - [6-1-1-2-K8S リソース (K8S-resources)](documents/6-Operation/6-1-Runtime|Continuous-test/6-1-1-Infra-scanning/6-1-1-2-K8S-resources.md)
    - [6-1-2-イメージスキャン (Image-scanning)](documents/6-Operation/6-1-Runtime|Continuous-test/6-1-2-Image-scanning.md)  
  - [6-2-侵害と攻撃のシミュレーション (Breach-and-attack-simulation)](documents/6-Operation/6-2-Breach-and-attack-simulation.md)
  - [6-3-ログ記録と監視 (Logging-and-Monitoring)](documents/6-Operation/6-3-Logging-and-Monitoring.md)
  - [6-4-ペンテスト (Pentest)](documents/6-Operation/6-4-Pentest.md)
  - [6-5-脆弱性開示ポリシーとバグバウンティ (VDP|Bug-bounty)](documents/6-Operation/6-5-VDP|Bug-bounty.md)
- [7-ガバナンス (Governance)](documents/7-Governance)
  - [7-1-コンプライアンス監査 (Compliance-Auditing)](documents/7-Governance/7-1-Compliance-Auditing)
    - [7-1-1-コンプライアンス監査 (Compliance-Auditing)](documents/7-Governance/7-1-Compliance-Auditing/7-1-1-Compliance-Auditing.md)
    - [7-1-2-Policy as Code (Policy-as-code)](documents/7-Governance/7-1-Compliance-Auditing/7-1-2-Policy-as-code.md)
    - [7-1-3-セキュリティベンチマーク (Security-benchmarking)](documents/7-Governance/7-1-Compliance-Auditing/7-1-3-Security-benchmarking.md)
  - [7-2-データ保護 (Data-protection)](documents/7-Governance/7-2-Data-protection.md)
  - [7-3-レポーティング (Reporting)](documents/7-Governance/7-3-Reporting)
    - [7-3-1-成熟度追跡 (Tracking-maturities)](documents/7-Governance/7-3-Reporting/7-3-1-Tracking-maturities.md)
    - [7-3-2-脆弱性一元管理ダッシュボード (Central-vulnerability-management-dashboard)](documents/7-Governance/7-3-Reporting/7-3-2-Central-vulnerability-management-dashboard.md)



---
OWASP ウェブサイトのプロジェクトページは [こちら](https://owasp.org/www-project-devsecops-guideline/) です
