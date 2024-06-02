## コミット前に

コミット前 (pre-commit) のフェーズは重要です。中心となる (Git) リポジトリに送信される前にセキュリティの問題を防ぐことができるためです。

コードにシークレットがないこと、およびコードが特定の (Linter ルールによる) ガイドラインに準拠していることを確認することが、より質の高いコードにつながります。

以下では、次のようなさまざまなタイプのコミット前 (pre-commit) アクションについて説明します。
1. シークレットの管理
2. コードのリンティング


以下の画像は pre-commit が何を意味し、なぜそれを考慮しなければならないかをよりよく理解するためのものです。

![Pre Commit](/document/assets/images/pre-commit.png)

## ツール:

+ [Pre-Commit](https://pre-commit.com/) - 多言語の pre-commit フックを管理および維持するためのフレームワークです。


### 参考情報

+ [Wikipedia - Lint (software)](https://en.wikipedia.org/wiki/Lint_(software))
