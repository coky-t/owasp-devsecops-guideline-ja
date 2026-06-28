# ソフトウェアコンポーネント/コンポジション解析 (SCA)

ソフトウェアコンポーネント解析はコードベースのサードパーティおよびオープンソースコンポーネントを管理するためのアプリケーションセキュリティを自動化するプロセスです。 SCA はコードベース内の潜在的に脆弱なコンポーネントを見つけて **サプライチェーン攻撃** などの高いセキュリティリスクを防止するだけでなく、各コンポーネントに対するライセンスも提供します。これを行うことで、組織はコードベースライブラリのセキュリティリスクを軽減することに役立ち、現在のソフトウェア開発ライフサイクルの中で早期に必要とされています。

> コンポーネント解析の詳細については [OWASP ページ](https://owasp.org/www-community/Component_Analysis) をご覧ください

SAST, DAST, IAST などのセキュリティテストの前にコンポーネント解析を早期に実施して、脆弱なライブラリがライブ環境 (本番環境) にプッシュされるのを防ぎます。ライブラリの継続的な監視を実装し、サプライチェーン攻撃のリスクを迅速に軽減します。

## ライセンスコンプライアンスチェック

<!-- TBD -->

## サプライチェーン攻撃

サプライチェーン攻撃はサプライヤー、ベンダー、ソフトウェアコンポーネントの相互接続ネットワークの脆弱性を悪用して、標的のシステムに侵入して侵害するものであり、多くの場合、広範なセキュリティ侵害やデータ窃取につながります。SCA ツールはすべての種類のサプライチェーン攻撃を直接検出できるわけではありませんが、それに関連する特定のリスクを軽減するのに役立ちます。ここでは SCA を使用してさまざまな種類のサプライチェーン攻撃にどのように対処できるかを示します。

- **依存関係の混乱 (Dependency Confusion)**
  攻撃者は悪意のあるパッケージやライブラリを、正規のものとよく似た名前でパブリックまたはプライベートのリポジトリにアップロードします。開発者はこれらの悪意のある依存関係を安全であると思い込んで、知らずにインストールしてしまい、セキュリティ侵害につながります。例: [PyTorch が休日を介した悪意のある依存関係チェーン侵害を公表](https://www.bleepingcomputer.com/news/security/pytorch-discloses-malicious-dependency-chain-compromise-over-holidays/#google_vignette)。
  SCA ツールは開発者が既知の脆弱性を持つ依存関係や、プロジェクトの設定ファイルで宣言していない依存関係を使用しているインスタンスを検出できます。悪意のあるパッケージを直接検出することはできませんが、予期しない依存関係や潜在的に危険な依存関係の存在を開発者に警告できます。

- **侵害されたビルド環境 (Compromised Build Environments)**
  ハッカーはビルド環境または CI/CD パイプラインに侵入してビルドプロセスを改竄し、コンパイルまたはパッケージ化の段階で悪意のあるコードを注入したり正規のコードを改変します。詳しくはこちらをご覧ください: [CI/CD パイプラインを侵害した 10 の実例](https://research.nccgroup.com/2022/01/13/10-real-world-stories-of-how-weve-compromised-ci-cd-pipelines/)。
  SCA ツールはビルドプロセスで使用されるソフトウェアパッケージやコンポーネントの構成を解析できます。既知の脆弱性や予期しない変更がないかこれらのコンポーネントをスキャンして、ビルドプロセスの中で悪意のあるコードが注入されたかどうかを特定するのに役立ちます。

- **ソフトウェアサプライチェーンハイジャック (Software Supply Chain Hijacking)**
  攻撃者はソフトウェアアップデートサーバー、ダウンロードミラー、パッケージマネージャーなど、ソフトウェアパッケージやアップデートの配布チャネルを侵害します。正規のソフトウェアを悪意のあるバージョンに置き換え、ユーザーや組織が無意識のうちにインストールしてしまいます。[SolarWinds ハックの説明](https://www.techtarget.com/whatis/feature/SolarWinds-hack-explained-Everything-you-need-to-know)。
  SCA ツールはソフトウェアパッケージと依存関係の完全性の変化を監視できます。正規のパッケージが悪意のあるバージョンに置き換えられた場合、SCA ツールはその不一致を検出して開発者やセキュリティチームに警告できます。

- **偽造コンポーネント (Counterfeit Components)**
  悪意のある攻撃者は正規の者に似せた偽造ハードウェアやソフトウェアのコンポーネントを作成します。これらの偽造コンポーネントには隠された脆弱性やバックドアが含まれている可能性があり、それらが統合されたシステムのセキュリティを脅かします。Stuxnet ワームはこのカテゴリに分類されます。 [Stuxnet について詳しくはこちらをご覧ください](https://www.wired.com/2014/11/countdown-to-zero-day-stuxnet/)。
  SCA ツールは偽造コンポーネントを直接検出できないかもしれませんが、信頼できて検証済みのコンポーネントのみがソフトウェア開発プロセスで使用されていることを確認するのに役立ちます。コンポーネントの出所とセキュリティステータスを可視化することで、SCA ツールはソフトウェアアプリケーションに偽造コンポーネントを組み込んでしまうリスクを軽減するのに役立ちます。

- **サードパーティの侵害 (Third-Party Compromise)**
  ハッカーはソフトウェアサプライチェーンに関わるサードパーティベンダーやサプライヤーを侵害し、機密情報やシステムへのアクセスを獲得して、顧客やパートナーに対してサプライチェーン攻撃を仕掛けることができます。
  SCA ツールはサードパーティやサプライヤーが提供するコンポーネントのセキュリティを解析して、そのセキュリティ態勢を評価できます。サードパーティコンポーネントの脆弱性や予期せぬ変更を監視します。
  SCA ツールはサードパーティベンダーが侵害されたかどうかを特定し、組織に潜在的なリスクを警告するのに役立ちます。[Accellion File Transfer Appliance の悪用](https://www.cisa.gov/news-events/cybersecurity-advisories/aa21-055a)

## SBOM

<!-- TBD -->

---

## ツール[^1]

### オープンソース

- [bundler-audit](https://github.com/rubysec/bundler-audit) - Bundler 向けのパッチレベル検証 (Ruby サードパーティライブラリバージョンの監査) です
- [OWASP CycloneDX](https://cyclonedx.org/) - 多くの [互換ジェネレータ](https://cyclonedx.org/tool-center/) と SPDX ライセンス ID および表現をサポートする SBOM 標準フォーマットです。
- [OWASP dep-scan](https://owasp.org/www-project-dep-scan/) - 複数の言語とコンテナのリポジトリに対する既知の脆弱性に基づく監査ツールです。SBOM および CSAF ドキュメントを生成します。
- [OWASP Dependency-check](https://owasp.org/www-project-dependency-check) - プロジェクトの依存関係に含まれる一般に公開されている脆弱性の検出を試みるソフトウェアコンポジション解析 (SCA) ツールで、 Java, .NET, JavaScript, Ruby をサポートしています
- [OWASP Dependency-Track](https://owasp.org/www-project-dependency-track/) -   Dependency-Track は組織がソフトウェアサプライチェーンのリスクを特定して低減できるようにするインテリジェントなコンポーネント解析プラットフォームです。これはソフトウェア部品表 (Software Bill of Materials, SBOM) の機能を活用するというユニークで非常に有益なアプローチをとっています。
- [RetireJS](https://github.com/RetireJS/retire.js) - JavaScript に特化した依存関係チェッカです
- [Safety](https://github.com/pyupio/safety) - 既知のセキュリティ脆弱性に対する Python 依存関係チェッカです

### 商用

- [Hakiri](https://hakiri.io/) - Ruby や Rails ベースの GitHub プロジェクト向けに静的コード解析を使用して依存関係チェックを提供する商用ツールです
- [HCL AppScan on Cloud](https://cloud.appscan.com) - SAST, SCA, IaC を同時に実行できるサービスとして構築された SAST ツールです
- [Snyk](https://snyk.io/) - SaaS ソリューションとして SCA ツールを提供します
- [Synopsys BlackDuck](https://www.blackducksoftware.com/) - Black Duck の自動化されたポリシー管理ではオープンソースの使用、セキュリティリスク、およびライセンスコンプライアンスに関するポリシーを前もって定義し、ソフトウェア開発ライフサイクル (SDLC) を通して実施を自動化できます。
- [WhiteSource](https://www.whitesourcesoftware.com/) - WhiteSource はソフトウェア内のすべてのオープンソースコンポーネントを依存関係を含めて識別します。ソフトウェア開発ライフサイクルを通して脆弱性からユーザーを保護し、ライセンスポリシーを適用します。

---

### リンク

- [SCA - OWASP](https://owasp.org/www-community/Component_Analysis)
- [SBOM - OWASP](https://owasp.org/www-community/Component_Analysis#software-bill-of-materials-sbom)

[^1]: アルファベット順にリストされています。
