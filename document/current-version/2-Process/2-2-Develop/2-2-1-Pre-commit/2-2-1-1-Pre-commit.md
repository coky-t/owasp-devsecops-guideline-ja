## プレコミット (Pre-commit)

コミット前 (pre-commit) のフェーズは重要です。中心となる (Git) リポジトリに送信される前にセキュリティの問題を防ぐことができるためです。

コードにシークレットがないこと、およびコードが特定の (Linter ルールによる) ガイドラインに準拠していることを確認することが、より質の高いコードにつながります。

以下では、次のようなさまざまなタイプのコミット前 (pre-commit) アクションについて説明します。
1. シークレットの管理
2. コードのリンティング

**Pre-commit** is a git feature that can be leveraged as part of the **shift-left security** approach where the developers are empowered to view the issues in the source code earlier in the SDLC process. When the developer runs a git-commit command to commit the code into their local repository, **pre-commit hook** check can be integrated with a security scanning tool executed to look for code quality issues, hard-coded secrets, insecure code, vulnerable dependencies/opensource libraries, etc..

It is to be noted that pre-commit hooks are at the developer's local repository level and not the remote repository commonly used by all the developers working on the same project/application. In such cases when it's required to prevent security issues before they are submitted to a remote/central (Git) repository **pre-push hook** or **git-push** checks can be configured. Refer: https://git-scm.com/docs/git-push

Another alternative approach to scan the source code for security issues (such as hardcoded-secrets, insecure code and vulnerable dependencies/opensource libraries) is the use of **SAST/SCA IDE plugins**. This works together with the IDEs used by developers while they write the code. Whereas, git-commit and git-push actions are used after the code is written by the developer. It is necessary to discern these distinct use-cases in order to implement the proper security controls at various levels based on the requirement.

以下の画像は pre-commit が何を意味し、なぜそれを考慮しなければならないかをよりよく理解するためのものです。

![Pre Commit](../assets/images/pre-commit.png)

## ツール:

+ [Pre-Commit](https://pre-commit.com/) - 多言語の pre-commit フックを管理および維持するためのフレームワークです。


### 参考情報

+ [Wikipedia - Lint (software)](https://en.wikipedia.org/wiki/Lint_(software))
