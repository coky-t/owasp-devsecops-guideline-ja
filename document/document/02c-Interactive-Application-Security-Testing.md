## インタラクティブアプリケーションセキュリティテスト

**IAST (インタラクティブアプリケーションセキュリティテスト)** は自動テスト、人間のテスト担当者、またはアプリケーション機能と "相互連携する" アクティビティによりアプリが実行されている間にアプリケーションをテストするアプリケーションセキュリティテスト手法です。

IAST ツールの中核となるのはアプリケーションコードに含まれるソフトウェアライブラリであるセンサーモジュールです。これらのセンサーモジュールはインタラクティブテストが実行されている間、アプリケーションの動作を追跡します。脆弱性が検出された場合、アラートが送信されます。

このプロセスとフィードバックは統合開発環境 (IDE)、継続的インテグレーション (CI) 環境、品質保証、あるいは実稼働時にリアルタイムで行われます。センサーは以下のものにアクセスできます。
+ コード全体
+ データフローと制御フロー
+ システム構成データ
+ ウェブコンポーネント
+ バックエンド接続データ

このような脆弱性の例としては API キーを平文でハードコードする、ユーザー入力をサニタイズしない、 SSL 暗号化なしで接続を使用するなどがあります。

---

### IAST vs SAST

**静的アプリケーションセキュリティテスト** 手法は SDLC の早い段階に非ランタイム環境でソースコードを調べます。セキュリティリスクを示す疑わしいコードパターンを探します。 SAST は簡単にデプロイできますが、他のセキュリティ対策の存在を考慮せず、実行時の視点が欠けているため、誤検出が多くなります。 SAST ツールは一般的にコンパイルフェーズの一環として IDE 内部で実行され、スキャンプロセスが終了するまでに時間がかかるため遅延が生じます。実稼働ランタイム環境に適用できるため、 IAST は SAST よりも柔軟性が高くなります (SAST はソースコードに直接アクセスする必要があります) 。

### IAST vs DAST

**動的アプリケーションセキュリティテスト** 手法はアプリケーションに対してリクエストを実行してセキュリティ問題を見つけるブラックボックススキャナのように機能します。 DAST はアプリケーションを外側から見て、一連のテストに対するサーバーの (本文とヘッダを含む) 応答を見ることによりリスクの存在を判断しますが、 DAST はアプリの内部動作を可視化できません。さらに、 DAST が本当に役立つためには、ペネトレーションテスト担当者などの経験豊富なアプリセキュリティチームにより操作される必要があるため、 DAST テストは自動化が困難です。 Forrester の見積もりでは DAST スキャンの所要時間はおよそ 5 から 7 日ですが、 IAST でのテストはリアルタイム (ゼロ分) オペレーションです。

---

### ツール

+ [Contrast Community Edition (CE)](https://www.contrastsecurity.com/contrast-community-edition)
+ [Checkmarx Interactive Application Security Testing(CxIAST)](https://www.checkmarx.com/products/interactive-application-security-testing/)
+ [Seeker Interactive Application Security Testing](https://www.synopsys.com/software-integrity/security-testing/interactive-application-security-testing.html)
+ [HCL AppScan on Cloud](https://cloud.appscan.com)

---
### 参考情報

+ [Veracode - IAST](https://www.veracode.com/security/interactive-application-security-testing-iast)
+ [OWASP - Free for Open Source Application Security Tools](https://owasp.org/www-community/Free_for_Open_Source_Application_Security_Tools)
+ [Hdivsecurity - IAST](https://hdivsecurity.com/bornsecure/what-is-iast-interactive-application-security-testing/)
+ [Contrastsecurity - IAST](https://www.contrastsecurity.com/knowledge-hub/glossary/interactive-application-security-testing)
+ [Synk - IAST](https://snyk.io/learn/iast-interactive-application-security-testing/)
+ [Acunetix - IAST](https://www.acunetix.com/blog/web-security-zone/what-is-iast-interactive-application-security-testing/)
+ [Contrast - Why the difference sast, dast, and iast mastters](https://www.contrastsecurity.com/security-influencers/why-the-difference-between-sast-dast-and-iast-matters)
+ [Esecurityplanet - Application security vendors](https://www.esecurityplanet.com/products/application-security-vendors/)