### 静的スキャンはプロセスの重要な部分
<img align="right" width="360" height="200" src="/document/assets/images/Static scanning.png">
静的コード解析またはソースコード解析は一般的にコードレビュー (ホワイトボックステスト) の一部であり、プログラムを実行せずにコードを調べることにより行われるコンピュータプログラムデバッグ手法です。</br>
静的スキャンは以下のようなコーディングの問題を見つけるのに適した方法です。

+ 構文違反
+ セキュリティ脆弱性
+ プログラミングエラー
+ コーディング規約違反
+ 未定義の値

静的コード解析の詳細については [OWASP ページ](https://owasp.org/www-community/controls/Static_Code_Analysis) をご覧ください。
より良い結果を得るために、静的セキュリティスキャンとサードパーティコード (オープンソースライブラリ(依存関係)) スキャンを組み合わせることができます。
この部分をより適切でより完全にする (設定ミスを防止する) ために、ここでは IaC (Infrastructure as code) セキュリティスキャンを導入することもできます。たとえば Terraform, helm, Ansible のコードなどをチェックします。
したがって上記の行によると、このステップで可能なアクションは以下のようになります。
+ 静的コード解析 (通称 SAST)
+ オープンソースライブラリ (サードパーティ / 依存関係) スキャン (通称 SCA)
+ IaC セキュリティスキャン

---
### ツール
- #### 静的コード解析:
  + [SonarQube](https://www.sonarqube.org) - オープンソースのウェブベースのツールで 20 以上の言語に対応しており、多くのプラグインもあります
  + [Veracode](https://www.veracode.com/security/static-analysis-tool) - SaaS モデル上に構築された静的解析ツール。このツールは主にセキュリティの観点からコードを解析するために使用されます
  + [security code scan](https://github.com/security-code-scan/security-code-scan) - C＃ と VB.NET 向けの脆弱性パターン検出器です
  + [Brakeman](https://github.com/presidentbeef/brakeman) - Ruby on Rails アプリケーション向けの静的解析セキュリティ脆弱性スキャナです
  + [Enlightn](https://github.com/enlightn/enlightn) - Laravel PHP アプリケーション向けの静的解析脆弱性スキャナです
  + [Inquisition](https://github.com/rubygarage/inquisition) - Ruby および Ruby on Rails で構築されたウェブアプリケーションのテクニカル分析に便利なツールセットです。これですべての単体 gem をセットアップして構成する必要がなくなります。代わりに Inquisition gem を使用します。
  + [CodeSweep](https://hclsw.co/codesweepgithub) - GitHub 向けの静的解析ツールです。フリーに使えてプルリクエストでコードをスキャンできます。 20 以上の言語と IaC (docker, k8s) をサポートしています。 VS Code 版は [こちら]( https://hclsw.co/codesweep) にあります
  + [HCL AppScan on Cloud](https://cloud.appscan.com ) - サービスとして構築された SAST ツールです。このツールは従来の SAST, SCA, IaC スキャンを実行できます。

- #### IaC スキャン: 
  + [Checkov](https://github.com/bridgecrewio/checkov) - Bridgecrew の Checkov で Terraform, Cloudformation, Kubernetes, Serverless フレームワーク、およびその他の infrastructure-as-code-languages のビルド時のクラウド設定ミスを防止します
  + [ansible-lint](https://github.com/ansible-community/ansible-lint) - Ansible のベストプラクティスチェッカです
  + [puppet-lint](https://github.com/rodjek/puppet-lint) - Puppet マニフェストがスタイルガイドに準拠していることをチェックします
  + [tfsec](https://github.com/tfsec/tfsec) - Terraform コード向けのセキュリティスキャナです
  + [terrascan](https://github.com/accurics/terrascan) - クラウドネイティブインフラストラクチャをプロビジョニングする前に Infrastructure as Code 全体でコンプライアンスやセキュリティ違反を検出してリスクを軽減します
  + [tflint](https://github.com/terraform-linters/tflint) - プラグ可能な Terraform リンターです