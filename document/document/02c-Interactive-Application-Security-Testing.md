## インタラクティブアプリケーションセキュリティテスト

**IAST (インタラクティブアプリケーションセキュリティテスト)** は自動テスト、人間のテスト担当者、もしくはコードの機能とのその他の「相互連携」によって実行しながらアプリケーション、API、機能をテストするアプリケーションセキュリティテスト手法です。これはあらゆるソフトウェア開発ライフサイクル、特に DevOps と高い親和性を持っています。

IAST はアプリケーションをスキャンするのではなく、アプリケーションや API サーバーにインストールし、アプリケーションを継続的に解析し続けます。IAST はセキュリティに関連するアプリケーションの動作を直接観察できるセンサーをコードに組み込むことで機能します。IAST は APM ツールやプロファイラと同様の実績のある技法を使用していますが、セキュリティとスピードに対して高度に最適化されています。

IAST ではチームがコードをビルド、テスト、デプロイする方法を変更する必要はありません。IAST は通常の開発およびテストの中でリアルタイムにセキュリティテストを実行し、脆弱性を悪用することなく特定します。つまり、IAST を使用すれば、セキュリティの知識がなくても、誰でも高品質のセキュリティテストを実行できるのです。

IAST は開発サーバー、CI/CD パイプライン、品質保証サーバーに導入でき、また本番環境でも利用できます。サーバー、コンテナ、仮想マシン、クラウド、その他の環境など、コードが実行される場所であればどこでも IAST がインストールされます。IAST は複雑な API コードやデータに対する SAST や DAST の課題を克服しており、API セキュリティテストに非常に適しています。

IAST センサーは以下のものにアクセスできます。
+ コード全体
+ 完全な HTTP リクエストとレスポンス
+ データフローとコントロール
+ 設定データ
+ ライブラリやフレームワークとそれらの使用方法
+ バックエンド接続データ

この豊富なコンテキストにより、IAST は従来のアプリケーションセキュリティテストツールと比較して非常に正確であり、IAST は非常に詳細な詳細な調査結果を提供できるため、開発者は問題を理解して正しく修正できます。また IAST は以下のような非常に広範囲のアプリケーションセキュリティ脆弱性をカバーできます。
+ ハードコードされたシークレットや脆弱な暗号化アルゴリズムなどのコードに関する問題
+ インジェクションや SSRF などのデータフローに関する問題
+ クリックジャッキング、パラメータ汚染、ヘッダ欠落などの HTTP に関する問題
+ SSRF などのバックエンド接続に関する問題
+ 動詞の改竄 (Verb Tamparing) や脆弱な認証などの設定に関する問題
+ その他いろいろ


IAST の課題の一つは実行されたコードのみがテストされることです。しかし、単純なエンドツーエンドの「スモーク」テストや単純なクローラーを使用して、このカバレッジを生成することは簡単です。IAST は大規模な機能テストを必要とせず、基本的なエンドツーエンドの経路の実行だけを必要とします。IAST ツールの中にはアプリケーションから一連の経路を抽出して、経路カバレッジを 100% にするプロセスを簡素化するものがあります。


---

### IAST vs SAST

**静的アプリケーションセキュリティテスト** 手法は SDLC の早い段階に非ランタイム環境でソースコードを調べます。セキュリティリスクを示す疑わしいコードパターンを探します。 SAST は簡単に導入できますが、他のセキュリティ対策の存在を考慮せず、実行時の視点が欠けているため、多くの誤検出を報告します。 SAST ツールは一般的にビルドプロセスの中で実行され、スキャンプロセスが終了するまでに時間がかかるため遅延が生じます。本番運用中のランタイム環境に適用できるため、 IAST は SAST よりも柔軟性が高くなります (SAST はソースコードに直接アクセスする必要があります) 。

### IAST vs DAST

**動的アプリケーションセキュリティテスト** 手法はアプリケーションに対して悪意のある HTTP リクエストを送信し、HTTP レスポンスを評価してセキュリティ静寂性があるかどうかを判断するブラックボックススキャナのように機能します。 DAST はアプリケーションを外側から見て、一連のテストに対するサーバーの (ボディやヘッダを含む) レスポンスを見ることによりリスクの有無を判断しますが、 DAST はアプリの内部動作を可視化できません。さらに、 DAST が本当に役立つためには、ペネトレーションテスト担当者などの経験豊富なアプリケーションセキュリティチームにより操作される必要があるため、 DAST テストは自動化が困難です。 Forrester の見積もりでは DAST スキャンの所要時間はおよそ 5 から 7 日ですが、 IAST でのテストはリアルタイム (ゼロ分) オペレーションです。

---

### ツール

+ [Contrast Assess](https://www.contrastsecurity.com/contrast-assess) and [Contrast Community Edition](https://www.contrastsecurity.com/contrast-community-edition)
+ [Checkmarx Interactive Application Security Testing(CxIAST)](https://www.checkmarx.com/products/interactive-application-security-testing/)
+ [Seeker Interactive Application Security Testing](https://www.synopsys.com/software-integrity/security-testing/interactive-application-security-testing.html)
+ [HCL AppScan on Cloud](https://cloud.appscan.com)

---
### 参考情報

+ [OWASP - Free IAST Tools](https://owasp.org/www-community/Free_for_Open_Source_Application_Security_Tools#:~:text=open%20source%20projects.-,IAST%20Tools,-IAST%20tools%20are)
+ [Contrast Security - What is Interactive Application Security Testing?](https://www.contrastsecurity.com/knowledge-hub/glossary/interactive-application-security-testing)
+ [Veracode - IAST](https://www.veracode.com/security/interactive-application-security-testing-iast)
+ [Hdivsecurity - IAST](https://hdivsecurity.com/bornsecure/what-is-iast-interactive-application-security-testing/)
+ [Synk - IAST](https://snyk.io/learn/iast-interactive-application-security-testing/)
+ [Acunetix - IAST](https://www.acunetix.com/blog/web-security-zone/what-is-iast-interactive-application-security-testing/)
+ [Contrast Security - Why the difference sast, dast, and iast mastters](https://www.contrastsecurity.com/security-influencers/why-the-difference-between-sast-dast-and-iast-matters)
+ [Esecurityplanet - Application security vendors](https://www.esecurityplanet.com/products/application-security-vendors/)
