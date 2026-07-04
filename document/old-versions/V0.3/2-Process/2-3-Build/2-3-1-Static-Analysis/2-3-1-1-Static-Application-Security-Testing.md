# 静的スキャンはプロセスの重要な部分

![Static scanning diagram showing analysis process](../../../assets/images/Static%20scanning.png)

静的コード解析またはソースコード解析は一般的にコードレビュー (ホワイトボックステスト) の一部であり、プログラムを実行せずにコードを調べることにより行われるコンピュータプログラムデバッグ手法です。

静的スキャンは以下のようなコーディングの問題を見つけるのに適した方法です。

- 構文違反
- セキュリティ脆弱性
- プログラミングエラー
- コーディング規約違反
- 未定義の値

静的コード解析の詳細については [OWASP ページ](https://owasp.org/www-community/controls/Static_Code_Analysis) をご覧ください。
より良い結果を得るために、静的セキュリティスキャンとサードパーティコード (オープンソースライブラリ(依存関係)) スキャンを組み合わせることができます。
この部分をより適切でより完全にする (設定ミスを防止する) ために、 IaC (Infrastructure as code) セキュリティスキャンを導入することもできます。たとえば Terraform, helm, Ansible のコードなどをチェックします。
したがって上記の行によると、このステップで可能なアクションは以下のようになります。

- 静的コード解析 (通称 SAST)
- オープンソースライブラリ (サードパーティ / 依存関係) スキャン (通称 SCA)
- IaC セキュリティスキャン

---

## ツール[^1]

### オープンソース

- [Brakeman](https://github.com/presidentbeef/brakeman) - Ruby on Rails アプリケーション向けの静的解析セキュリティ脆弱性スキャナです
- [CodeQL](https://github.com/github/codeql) - 業界をリードするセマンティックコード解析エンジン CodeQL により、コードベース全体の脆弱性を発見します。
- [CodeSec by Contrast Security](https://www.contrastsecurity.com/developer) - 開発者および CI/CD パイプラインで使用するために設計された高速で高品質なフリーの SAST ツールです。
- [SonarQube](https://www.sonarqube.org) - オープンソースのウェブベースのツールで 20 以上の言語に対応しており、多くのプラグインもあります

### 商用

- [Checkmarx SAST](https://checkmarx.com) - 静的解析セキュリティ脆弱性スキャナです
- [CodeSweep](https://hclsw.co/codesweepgithub) - GitHub 向けの静的解析ツールです。フリーに使えてプルリクエストでコードをスキャンできます。 20 以上の言語と IaC (docker, k8s) をサポートしています。 [CodeSweep VS Code 拡張をダウンロード](https://hclsw.co/codesweep)
- [Enlightn](https://github.com/enlightn/enlightn) - Laravel PHP アプリケーション向けの静的解析脆弱性スキャナです
- [Fortify](https://www.microfocus.com/en-us/cyberres/application-security/static-code-analyzer)- 静的解析セキュリティ脆弱性スキャナです
- [HCL AppScan on Cloud](https://cloud.appscan.com ) - サービスとして構築された SAST ツールです。このツールは従来の SAST, SCA, IaC スキャンを実行できます。
- [Inquisition](https://github.com/rubygarage/inquisition) - Ruby および Ruby on Rails で構築されたウェブアプリケーションのテクニカル分析に便利なツールセットです。これですべての単体 gem をセットアップして構成する必要がなくなります。代わりに Inquisition gem を使用します。
- [PT Application Inspector](https://www.ptsecurity.com/ww-en/products/ai/) - 高品質な解析と脆弱性を自動的に確認する便利なツールを提供する唯一のソースコードアナライザです - レポートにより作業を大幅にスピードアップし、セキュリティ専門家と開発者との間のチームワークを簡素化します
- [security code scan](https://github.com/security-code-scan/security-code-scan) - C＃ と VB.NET 向けの脆弱性パターン検出器です
- [Semgrep](https://semgrep.dev) - 多くの言語に対応した軽量な静的解析です。ソースコードのようなパターンでバグと思われるものを見つけます。
- [Veracode](https://www.veracode.com/security/static-analysis-tool) - SaaS モデル上に構築された静的解析ツールです。このツールは主にセキュリティの観点からコードを解析するために使用されます

---

### リンク

[^1]: アルファベット順にリストされています。
