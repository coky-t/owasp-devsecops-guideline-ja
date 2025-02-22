# シークレットとクレデンシャルに注意


*機密情報がリポジトリにプッシュされないようにするにはどのようにすればよいでしょうか？*

これは [OWASP Top Ten issues](https://owasp.org/www-project-top-ten/2017/A3_2017-Sensitive_Data_Exposure) の一つであり、
いくつかのバグバウンティの記事がこの種の問題に関連しています。たとえばハードコードされたクレデンシャルが誤ってプッシュされたなどです。

コミットやリポジトリをスキャンして、パスワード、秘密鍵、社外秘などの機密情報を検出する必要があります。
図のようなプロセスに従います。
<br/>

理想的なアプローチは機密データがリポジトリにヒットする前に露出を検出して防止することです。
なぜならそれらは履歴に表示されるからです。コードホスティングプラットフォームの場合、シークレットはウェブ上に残り、
リポジトリから削除した後でも検索できます。

補完的なアプローチとしてはリポジトリをスキャンして機密情報を探し、それを削除することです。
クレデンシャルが漏洩した場合、それはすでに危険な状態であり、無効にすべきであることに注意してください。

## 複数の場所でシークレットを検出する

- **既存のシークレットを検出する** リポジトリ内の既存のシークレットを検索します。
- **プレコミットフックを使用する** シークレットがコードベースに入ることを防ぐため。
- **パイプラインでシークレットを検出する**

## なぜシークレットを検出するのか？

+ シークレットがハードコードされていないこと。
+ シークレットが暗号化解除されていないこと。
+ シークレットがソースコードに保存されていないこと。
+ コード履歴に不注意によるシークレットが含まれていないこと。

## シークレットをいつどこで検出するか？
![Pre Commit](../../../assets/images/pre-commit.png)


そうですね、最適な場所は **pre-commit** の場所です。これによりシークレットが実際にコードベースに入る前にインターセプトされ、開発者やコミットした人がメッセージを受け取ることができます。**SAST IDE プラグイン** を使用すると、開発者がセキュリティ構成ミスで安全でないコードを書くとすぐに IDE の警告が見つかるような問題を修正しようとしている際に便利です。もう一つの場所はビルドサーバーまたは **build** プロセスです。ビルドサーバーは既にコミットされているソースコードを取得して、ソースコードを解析します。新しいシークレットが含まれていたり、既知のシークレットが含まれていた場合にそのシークレットが実際に妥当性確認や監査されます。

---
ここではリポジトリを自動的にスキャンして機密情報を探すのに役立つツールを紹介します。
スキャンはパイプラインに直接実装でき、再現性と効率性に優れています。

## ツール:
- **オープンソース**:
  + [gittyleaks](https://github.com/kootenpv/gittyleaks) - git リポジトリの機密情報を検索します
  + [git-secrets](https://github.com/awslabs/git-secrets) - シークレットとクレデンシャルを git リポジトリにコミットできないようにします
  + [Repo-supervisor](https://github.com/auth0/repo-supervisor) - コードのセキュリティ設定ミスをスキャンし、パスワードとシークレットを検索します
  + [truffleHog](https://github.com/dxa4481/truffleHog) - git リポジトリから高エントロピー文字列とシークレットを検索し、コミット履歴を深く掘り下げます
  + [Git Hound](https://github.com/ezekg/git-hound) - 機密データのコミットを防止する git プラグインです
  + [Github Secret Scanning](https://docs.github.com/en/code-security/secret-scanning) - GitHub に組み込まれたシークレット検出用の機能です。

- **プロプライエタリソフトウェア**:
  + [GitGuardian](https://gitguardian.com) - ソースコードからシークレットを締め出します
  + [Spectralops](https://spectralops.io) - 開発者ファーストのクラウドセキュリティです
  + [TruffleSecurity](https://trufflesecurity.com) - シークレットを解き明かします
  + [GitHub Advanced Security](https://docs.github.com/en/code-security/secret-scanning/about-secret-scanning) - GitHub はリポジトリをスキャンして既知の種類のシークレットを検出し、誤ってコミットされたシークレットの不正使用を防ぎます
  + [BluBracket](https://blubracket.com) - コード内のシークレットとクレデンシャルを防ぎます
  + [Nightfall](https://nightfall.ai) - クラウド上のシークレットと鍵を見つけて保護します
