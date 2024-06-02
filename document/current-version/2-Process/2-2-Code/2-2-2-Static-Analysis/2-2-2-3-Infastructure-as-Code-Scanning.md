### Infrastructure as Code スキャン
IaC スキャンとはインフラストラクチャのセットアップと管理に使われるコードをチェックすることを意味します。このコードは、Terraform や Ansible などのツールで記述され、サーバー、ネットワーク、インフラストラクチャのその他の部分をどのように作成するかを定義します。IaC スキャンの目的はインフラストラクチャをデプロイする前の早期にセキュリティの問題や間違いを発見することです。こうすることで、チームは最初からインフラストラクチャがセキュリティルールや会社のポリシーに従っていることを確認できます。このようなチェックはコードが実際のシステムで使用される前に、開発プロセスの一環として行われます。

開発チームが Terraform を使用して AWS のクラウドリソースのプロビジョニングを自動化するシナリオを考えてみましょう。簡略化した例を以下に示します。
```terraform 
# Terraform script to create an S3 bucket

provider "aws" {
  region = "us-east-1"
}

resource "aws_s3_bucket" "example_bucket" {
  bucket = "example-bucket"
  acl    = "public-read"
}
```
この例では、Terraform スクリプトは "example-bucket" という名前の S3 バケットをパブリック読み取りアクセス (acl = "public-read") で作成します。

IaC スキャンプロセスにおいて、パケットへのパブリックアクセスが許可されているため、スキャンツールはこの設定を検出して、セキュリティリスクとしてフラグを立てるかもしれません。これは、バケットに保存されている機密データを認可されていないユーザーに公開してしまう可能性があります。

IaC スキャンで見つかった結果により、開発チームが Terraform スクリプトを修正して、バケットがパブリックにアクセスできないようにするかもしれません。

次のパートでは、アプリケーションの開発とデプロイメントのさまざまなフェーズでさまざまなタイプの IaC スキャンに対処するのに役立つツールのリストを紹介します。

---
### ツール
- #### Infrastructure as Code スキャンツール: 
  + [Checkov](https://github.com/bridgecrewio/checkov) - Terraform, Cloudformation, Kubernetes, Serverless フレームワーク, その他の Infrastructure as Code 言語の構築時に Bridgecrew の Checkov でクラウドの設定ミスを防ぎます。
  + [ansible-lint](https://github.com/ansible-community/ansible-lint) - Ansible 向けのベストプラクティスチェッカーです。
  + [puppet-lint](https://github.com/rodjek/puppet-lint) - Puppet マニフェストがスタイルガイドに準拠していることをチェックします。
  + [tfsec](https://github.com/tfsec/tfsec) - Terraform コード向けのセキュリティスキャナです。
  + [terrascan](https://github.com/accurics/terrascan) - Infrastructure as Code のコンプライアンスとセキュリティ違反を検出して、クラウドネイティブインフラストラクチャをプロビジョニングする前にリスクを軽減します。
  + [tflint](https://github.com/terraform-linters/tflint) - プラグ可能な Terraform リンターです。
  + [Trivy](https://github.com/aquasecurity/trivy) - Docker, Kubernetes, Terraform, CloudFormation の設定問題を検出するためのビルトインポリシーを提供します。また、Conftest のように Rego で独自のポリシーを記述して JSON, YAML などをスキャンできます。
  + [KICS](https://github.com/Checkmarx/kics) - Find security vulnerabilities, compliance issues, and infrastructure misconfigurations early in the development cycle of your infrastructure-as-code with KICS by Checkmarx.
