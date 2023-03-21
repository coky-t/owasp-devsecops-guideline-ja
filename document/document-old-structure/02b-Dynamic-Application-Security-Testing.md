### 動的アプリケーションセキュリティテスト (DAST)

DAST は "ブラックボックス" テスト技法であり、悪性ペイロードを注入して SQL インジェクションやクロスサイトスクリプティング (XSS) などの攻撃を可能にする潜在的な欠陥を特定することにより、実行中のアプリケーションのセキュリティ脆弱性や弱点を見つけることができます。 DAST ツールは以下のようなものの検出に特に役立ちます。
- 入出力バリデーション
- 認証の問題
- サーバー設定ミス

DAST ツールはアプリケーションをビルドするソースコードやフレームワークを必要とせずに、クライアント側とサーバー側の広範囲なスキャンを実行できます。設定には専門知識が必要ですが、スキャンは一般的に一度設定すればユーザーの操作は最小限で済み、夜間スキャンの一部として実行することができます。より重要な DAST ツールとして以下のものがあります。
- 動的セキュリティスキャナ
- ファザー
- 攻撃プロキシ

---
### ツール
- #### オープンソース:
  + [ZED Attack Proxy](https://www.zaproxy.org) - これは OWASP が提供するセキュリティテストを実行するためのオープンソースツールです

- #### 商用:
  + [Acunetix](https://www.acunetix.com) - HTML5, JavaScript, シングルページアプリケーション (SPA) などのすべてのウェブアプリケーションを正確にスキャンおよび監査する自動ウェブセキュリティテストスキャナです
  + [Netsparker](https://www.netsparker.com) - 基盤となるアーキテクチャやプラットフォームに関係なく、あらゆるタイプの最新のウェブアプリケーションの脆弱性を特定できます
  + [InsightAppSec (AppSpider)](https://www.rapid7.com/products/insightappsec) - 最新のウェブのアプリケーションセキュリティテストです
  + [Veracode Dynamic Analysis](https://www.veracode.com/products/dynamic-analysis-dast) - Veracode Dynamic Analysis は悪用可能な脆弱性に関して企業が大規模にウェブアプリケーションをスキャンするのに役立ちます
  + [Burp Suite](http://www.portswigger.net/) はウェブアプリケーションのセキュリティテストを実行するための統合プラットフォームです。さまざまなツールがシームレスに連携して、アプリケーションの攻撃対象領域の初期マッピングと分析から、セキュリティ脆弱性の発見とエクスプロイトに至るまで、テストプロセス全体をサポートします。
  + [HCL AppScan on Cloud](https://cloud.appscan.com) - サービスとして構築された DAST ツールです。パブリックアプリケーションとプライベートでホストされているアプリケーションの両方をスキャンできます。最新のウェブアプリケーションを調査およびテストし、手動で記録された手順を活用して複雑なログインシナリオを処理できます。
  + [Nuclei](https://github.com/projectdiscovery/nuclei) - シンプルな YAML ベースの DSL に基づく高速でカスタマイズ可能な脆弱性スキャナです。

---
### 参考情報

+ [OWASP - Vulnerability Scanning Tools](https://owasp.org/www-community/Vulnerability_Scanning_Tools)
+ [RAPID7 - Dynamic Application Security Testing](https://www.rapid7.com/fundamentals/dast/)
