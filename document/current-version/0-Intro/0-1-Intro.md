# 序文

OWASP DevSecOps Guideline は、ベストプラクティスと、厳選されたベンダー中立なツール群を使用して、セキュアなソフトウェアデリバリパイプラインを構築して運用する方法を説明しています。その目的は、DevOps パイプラインを動かすあらゆる規模の組織がデリバリを遅くすることなくセキュリティコントロールを導入するように支援すること、開発ライフサイクル全体を通じて **シフトレフト** (そしてさらには **シフトエブリウェア**) のセキュリティ文化を促進することです。

このガイドラインの理想とする目標は以下のようにシンプルです。

> **設計上の欠陥であれアプリケーションの脆弱性であれ、セキュリティ上の問題を可能な限り早くかつ安く検出し、継続的に検出し続けること。**

DevSecOps とは DevOps *内に* セキュリティを組み込むことです。CI/CD のペースに追従するには、セキュリティは最後の関門とするのではなく、ソフトウェアの設計、記述、ビルド、テスト、運用内に早期に組み込み、本番環境でも継続的に検証していく必要があります。

## なぜ DevSecOps なのか — 遅れによるコスト

脆弱性が早期に発見されるほど、その修正を安価に抑えられます。IBM の Systems Science Institute の調査によると、設計段階で発見された欠陥の修正コストは、実装段階で発見されたものと比べておよそ 6 分の 1 になり、本番環境で発見されたものと比べておよそ 100 分の 1 になることを、一貫して示しています。これらの比率は厳密ではなく、欠陥の種類やシステムによって異なりますが、発見が遅れるほど費用が増大する、というのが業界全体にわたる方向性を示す事実です。

しかし、数字だけでは捕捉できないより深刻なコストがもうひとつあります。本番環境で脆弱性が *悪用される* と、修復コストを負担するだけでなく、侵害によるコスト、規制当局からの制裁、評判の低下、顧客への被害、経営陣の説明責任という負担もあります。2020 年の SolarWinds サプライチェーン攻撃、2021 年に数百万のシステムに影響を及ぼした Log4Shell 情報漏洩、2019 年の Capital One 侵害 (WAF/SSRF の設定ミスによる) はすべてが共通の脅威を共有しています。セキュリティがデリバリ全体を通して継続的に考慮されていないために、悪用経路が存在していたということです。

リリースの数週前のペネトレーションテストや、リクエストを受けてコードをレビューするセキュリティチームといった、従来のセキュリティは一日に幾度も出荷するチームには追従できません。DevSecOps は、自動化可能なものを自動化し、セキュリティに関するフィードバックを即座に得られるとともに、リスクに関する判断が適切なレベルでできるように共有されたオーナーシップを築くことで、これを解決します。

## どのようにこのガイドラインが構成されているか

このバージョンは DevSecOps の三つの主要な柱を中心に構成されています。

- **要員 (People)** — 安全なデリバリを可能にするチーム、役割、文化、トレーニング。
- **プロセス (Process)** — ソフトウェア開発ライフサイクルのあらゆる段階に編み込まれたセキュリティ活動。
- **ガバナンス (Governance)** — プログラムの説明責任と改善を維持する監視、コンプライアンス、測定、報告。

**プロセス (Process)** の下には、製品開発ライフサイクルは七つの段階に区分され、それぞれにセキュリティコントロールが割り当てられています。

- **設計 (Design)** — 脅威モデリング、セキュアバイデザイン、セキュリティ要件。
- **開発 (Develop)** — pre-commit フック、シークレット管理、リント実行、リポジトリ堅牢化、AI 支援型内部ループの保護。
- **ビルド (Build)** — SAST、SCA、コンテナセキュリティ、IaC スキャン、セキュリティゲート、ソフトウェアサプライチェーンセキュリティ (SBOM、署名/来歴、パイプラインセキュリティ)。
- **テスト (Test)** — IAST、DAST、モバイルアプリテスト、API セキュリティ、誤設定チェック。
- **リリース (Release)** — 最終承認、署名および証明済みアーティファクト。
- **デプロイ (Deploy)** — アドミッションコントロール、GitOps、プログレッシブデリバリ。
- **運用 (Operate)** — クラウドネイティブなランタイムセキュリティ、ログ記録と監視、ペンテスト、脆弱性管理、開示プログラム、Breach and Attack Simulation。

独自の SDLC やアーキテクチャに合わせてこれらの段階をカスタマイズでき、成熟度が高まるにつれて段階的に自動化を追加できます。

## What DevSecOps is NOT

Understanding the common misconceptions is as important as knowing the definition:

- **DevSecOps is not "security team in the pipeline"** — adding security engineers to approve every PR does not scale. The goal is to give developers the tools, training, and context to make security decisions themselves, with the security team acting as an enabler and escalation path, not a gatekeeper.
- **DevSecOps is not tool procurement** — buying a SAST, SCA, and DAST tool without a triage process, clear ownership, and remediation SLAs creates alert fatigue and false confidence. Tools are enablers; process and culture are the program.
- **DevSecOps is not a one-time project** — there is no "done." The threat landscape, your architecture, your dependencies, and your regulatory obligations all change continuously. DevSecOps is a continuous practice, not a migration.
- **DevSecOps is not compliance** — passing an audit is a floor, not a ceiling. Compliance frameworks describe minimum bars against known risks; a real-world adversary does not follow the framework. Design for adversaries, not just auditors.
- **DevSecOps is not just CI/CD** — the pipeline is important, but threat modeling happens at design, culture happens in teams, runtime security happens in production, and vulnerability disclosure happens at the boundary with the outside world. The pipeline is one layer of a much broader system.

## A note on the pipeline itself

CI/CD is a powerful entry point for security automation, but the build and automation tooling is also part of your attack surface. Compromised pipelines, leaked tokens, and poisoned dependencies are now among the most damaging attack vectors — the SolarWinds, Codecov, and XZ Utils incidents all illustrate how the build and supply chain can be abused to reach production at scale. This guideline therefore treats **securing the pipeline** as a first-class concern alongside securing the application.

## How to use this guideline

Different audiences will find different entry points most useful:

**If you are a developer or engineer:**
Start with the [Develop](../2-Process/2-2-Develop) stage, specifically pre-commit hooks and secrets management — the controls you can implement in your own workflow today. Then read the [Build](../2-Process/2-3-Build) stage for what your CI pipeline should enforce. Use the [Threat Modeling](../2-Process/2-1-Design/2-1-1-Threat-modeling.md) page when you are designing a new feature or service.

**If you are a security engineer or AppSec lead:**
Start with the [Overview](0-2-Overview.md) for a full pipeline view, then use the [Frameworks and Standards](0-3-Frameworks-and-Standards.md) page to map this guideline to your regulatory or maturity framework requirements. Use the [Governance](../3-Governance) section to build a reporting and measurement program.

**If you are an engineering manager or CISO:**
Start with the [Maturity levels](#maturity-levels--where-to-start) table below and the [Tracking Maturities](../3-Governance/3-3-Reporting/3-3-1-Tracking-maturities.md) page. The [People](../1-People) section covers the organizational structures (security champions, roles) that make the program sustainable.

## Common anti-patterns to avoid

- **Security as a gate at the end** — running a pentest or DAST scan as the sole security activity before release does not scale, finds issues too late, and creates a bottleneck. Gates are necessary but not sufficient.
- **Tool sprawl without process** — buying or deploying many scanners without a clear triage, ownership, and remediation process generates noise and alert fatigue that causes teams to ignore findings entirely.
- **Centralized security ownership** — a small security team that "owns" security and must review everything becomes a bottleneck and a single point of failure. Shared ownership, supported by tooling and champions, is the goal.
- **Treating compliance as security** — passing an audit is not the same as being secure. Compliance is a floor, not a ceiling; design for real-world adversaries, not just checkbox controls.
- **Ignoring developer experience** — security tooling that is slow, noisy, or hard to use gets disabled or routed around. Developer experience is a security concern.

## Maturity levels — where to start

| Stage | What to focus on |
|---|---|
| Starting out | Secrets scanning in CI, SCA for known CVEs, basic branch protection, OWASP Top 10 awareness training |
| Developing | SAST in pull requests, IaC scanning, security gates on high/critical findings, security champions program |
| Maturing | Container hardening, SBOM generation, threat modeling, DAST, vulnerability management SLAs |
| Advanced | Supply-chain signing and provenance (SLSA), ASPM, BAS, runtime detection-as-code, AI/ML security |

## Where to start

- [OWASP Proactive Controls](https://owasp.org/www-project-proactive-controls/) lists the top security controls every developer should implement while coding.
- [OWASP Software Assurance Maturity Model (SAMM)](https://owaspsamm.org/model/) helps you decide what to prioritize according to your maturity level.
- The [Frameworks and Standards](0-3-Frameworks-and-Standards.md) page maps how SSDF, SAMM, DSOMM, and SLSA fit together with this guideline.
- The [Overview](0-2-Overview.md) page lists a recommended progression of controls to introduce into a pipeline.

If you need earlier editions, see the [old-versions](../../old-versions/) directory.
