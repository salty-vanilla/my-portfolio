# 開発方針

## プロジェクト概要

**転職向けポートフォリオ：ソフトウェアエンジニア × コンピュータサイエンス研究者**

研究（論文・publication）と実装（プロジェクト・Web/Cloud）を同格で見せることを目的とした、ミニマルで落ち着いたポートフォリオサイト。

---

## 核心思想

**研究・実装・運用を横断できる人間であることを、短時間で理解させる**

- UIは主役ではない
- 情報は引き算する
- Bloomfolio = 安定した土台
- Minimalistic = 思想・設計ルール

---

## 技術スタック

- **Astro（SSG）** - メインフレームワーク
- **Tailwind CSS** - スタイリング
- **daisyUI（控えめ）** - UI補助
- **JSON/Markdown** - コンテンツ管理

---

## デザイン原則

### トーン
- **ミニマル / 明るめ / 落ち着いた**
- 研究者・CSバックグラウンドに合う

### カラーテーマ
- **ほぼモノクロ**
- 参考：[Nagi](https://nagi-6tu.pages.dev/)
- アクセント色は必須ではない（使うならリンクhover程度）

### ルール
- 色数：グレー階調のみ
- 余白：セクション間は広め・統一
- 影：極小 or なし
- 枠線：薄いグレー
- 見出しは大きく、本文は落ち着かせる

---

## サイト構成

### トップページ `/`
1. **Hero** - 自己紹介・立ち位置
2. **Highlights** - Research / Software / Cloud
3. **Featured Projects** - 3件のみ
4. **Research** - 自分のpublication
5. **Skills** - 技術スタック
6. **Writing** - Zenn記事へのリンク
7. **Links** - 外部リンク集

### その他のページ
- `/projects` - プロジェクト一覧
- `/research` - 研究・論文一覧
- `/cv` - 履歴書（PDF + Web版）
- `/about` - About
- `/links` - リンク集

---

## Hero セクション

### コンセプト
**研究 × ソフトウェア × Web × クラウド**

### 表示内容
- タイトル：**Computer Science Researcher & Software Engineer**
- サブタイトル：**Computer Vision / Industrial Anomaly Detection / Web & Cloud Systems**
- 説明：研究成果を、Webとクラウド基盤で**運用可能なプロダクト**に落とし込みます。

### CTA
- Primary：Projects
- Secondary：CV
- Link：Research / Publications
- Link：Paper Archive（別サイト）

---

## コンテンツ表示ルール

### Projects
技術スタック羅列は**しない**。必ず以下の構造：

- **Problem** - 何の問題を解決するのか
- **Approach** - どうアプローチしたか
- **Impact** - どんな影響・成果があったか

### Research / Publications
- 掲載するのは**自分の研究のみ**
- 年・会議/誌・リンク（PDF / arXiv / Code）
- Projectsと同じカードデザインで統一

### 他論文・サーベイ
- **このサイトには置かない**
- 別サイト（論文アーカイブ）で運用
- ポートフォリオからリンクのみ

---

## 外部コンテンツ戦略

| コンテンツ | 掲載場所 | 説明 |
|----------|---------|-----|
| 技術ブログ | [Zenn](https://zenn.dev/) | ポートフォリオ側はリンク集約 |
| 他論文まとめ | 論文アーカイブサイト | サーベイ・Deep Dive |
| 自分の研究 | このポートフォリオ | Research セクション |

---

## 開発の進め方

1. **既存Bloomfolioをベース**として採用
2. **Minimalisticの設計思想**（余白・階層・引き算）を取り入れる
3. モノクロ・ミニマルなデザインに刷新
4. コンテンツ構造を整理（Problem/Approach/Impact）
5. 不要な装飾・色・情報を削除

---

## デプロイ

- GitHub Pages または Vercel
- 静的サイト生成（SSG）で運用
