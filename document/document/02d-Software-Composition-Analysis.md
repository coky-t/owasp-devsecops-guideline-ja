### ソフトウェアコンポーネント/コンポジション解析 (SCA)

コンポーネント解析はコードベースのサードパーティおよびオープンソースコンポーネントを管理するためのアプリケーションセキュリティを自動化するプロセスです。 SCA はコードベース内の潜在的に脆弱なコンポーネントを見つけて **サプライチェーン攻撃** などの高いセキュリティリスクを防止するだけでなく、各コンポーネントに関するライセンスも提供します。これを行うことで、組織はコードベースライブラリのセキュリティリスクを軽減することに役立ち、現在のソフトウェア開発ライフサイクルの中で早期に必要とされています。

> コンポーネント解析の詳細については [OWASP ページ](https://owasp.org/www-community/Component_Analysis) をご覧ください

SAST や DAST などのセキュリティテストの前にコンポーネント解析を早期に実施して、脆弱なライブラリがライブ環境 (本番環境) にプッシュされるのを防ぎます。ライブラリの継続的な監視を実装し、サプライチェーン攻撃のリスクを迅速に軽減します。

---
### ツール
- #### オープンソース:
  + [OWASP Dependency-check](https://owasp.org/www-project-dependency-check) - プロジェクトの依存関係に含まれる一般に公開されている脆弱性の検出を試みるソフトウェアコンポジション解析 (SCA) ツールで、 Java, .NET, JavaScript, Ruby をサポートしています
  + [RetireJS](https://github.com/RetireJS/retire.js) - JavaScript に特化した依存関係チェッカです
  + [Safety](https://github.com/pyupio/safety) - 既知のセキュリティ脆弱性に対する Python 依存関係チェッカです
  + [bundler-audit](https://github.com/rubysec/bundler-audit) - Bundler 向けのパッチレベル検証 (Ruby サードパーティライブラリバージョンの監査) です

- #### 商用:
  + [Hakiri](https://hakiri.io/) - Ruby や Rails ベースの GitHub プロジェクト向けに静的コード解析を使用して依存関係チェックを提供する商用ツールです
  + [HCL AppScan on Cloud](https://cloud.appscan.com) - SAST, SCA, IaC を同時に実行できるサービスとして構築された SAST ツールです
  + [Snyk](https://snyk.io/) - SaaS ソリューションとして SCA ツールを提供します
  + [WhiteSource](https://www.whitesourcesoftware.com/) - WhiteSource はソフトウェア内のすべてのオープンソースコンポーネントを依存関係を含めて識別します。ソフトウェア開発ライフサイクルを通して脆弱性からユーザーを保護し、ライセンスポリシーを適用します。
  + [Synopsys BlackDuck](https://www.blackducksoftware.com/) - Black Duck の自動化されたポリシー管理ではオープンソースの使用、セキュリティリスク、およびライセンスコンプライアンスに関するポリシーを前もって定義し、ソフトウェア開発ライフサイクル (SDLC) を通して実施を自動化できます。


### 参考情報

+ [SCA - OWASP](https://owasp.org/www-community/Component_Analysis)