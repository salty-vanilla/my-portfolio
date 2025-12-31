# Content Structure Guidelines

**適用対象**: `src/content/`配下のすべてのMarkdown/MDXファイル

---

## 共通ルール

### Frontmatter必須項目

すべてのコンテンツには以下を含める：

```yaml
---
title: "タイトル"
description: "説明文（1-2行）"
date: 2024-01-15
draft: false
---
```

---

## Projects（`src/content/projects/`）

### 必須構造

**Problem / Approach / Impact** の3セクション構成

```markdown
---
title: "プロジェクト名"
description: "1行の説明"
date: 2024-01-15
url: "https://..."
github: "https://github.com/..."
draft: false
---

## Problem

何の問題を解決するのか。
背景・課題を明確に記述。

## Approach

どのようにアプローチしたか。
技術的な選択理由や実装の工夫。

## Impact

どんな成果・影響があったか。
定量的な結果や、解決した課題の評価。
```

### 禁止事項

❌ 技術スタックのバッジ羅列
❌ "Technologies Used" セクション
❌ スクリーンショットの大量配置

### 推奨

✅ 問題→解決→成果の流れを明確に
✅ 具体的な数値や事例
✅ 簡潔な文章（各セクション2-4パラグラフ）

### 例

```markdown
---
title: "Screencial - Screenshot Management Tool"
description: "Automatic screenshot organization and search system"
date: 2024-01-15
url: "https://screencial.com"
github: "https://github.com/example/screencial"
draft: false
---

## Problem

開発中に大量のスクリーンショットが蓄積され、必要な画像を見つけるのに時間がかかる。手動での整理は非効率。

## Approach

自動分類システムを構築。OCRで文字抽出、画像認識でカテゴリ推定。検索インデックスを作成し、フルテキスト検索を実装。

## Impact

整理時間を90%削減。500枚以上のスクリーンショットから目的の画像を3秒以内に発見可能に。
```

---

## Research（`src/content/research/`）

### 必須構造

**自分の研究・論文のみ**掲載

```markdown
---
title: "論文タイトル（英語）"
description: "研究の概要（1-2行）"
date: 2024-01-15
venue: "会議名 or ジャーナル名"
authors: ["Author 1", "Author 2", "Your Name"]
pdf: "https://..."
arxiv: "https://arxiv.org/abs/..."
code: "https://github.com/..."
draft: false
---

## Problem

研究が解決する問題。

## Approach

提案手法・アプローチ。

## Impact

研究成果・貢献。
```

### Frontmatter追加項目

```yaml
venue: "CVPR 2024"  # 会議名
authors: ["John Doe", "Jane Smith"]
pdf: "https://..."
arxiv: "https://..."
code: "https://..."
```

### 禁止事項

❌ 他人の論文まとめ
❌ サーベイ記事
❌ 分野全体の解説

→ これらは**別サイト（論文アーカイブ）**で運用

---

## Work（`src/content/work/`）

### 職歴情報

```markdown
---
title: "会社名"
role: "役職・ポジション"
startDate: 2022-04-01
endDate: 2024-03-31  # 現職の場合はnullまたは空
location: "Tokyo, Japan"
draft: false
---

担当業務や成果を簡潔に記述。
```

---

## Education（`src/content/education/`）

### 学歴情報

```markdown
---
title: "大学名"
degree: "Bachelor of Science in Computer Science"
startDate: 2018-04-01
endDate: 2022-03-31
location: "Tokyo, Japan"
draft: false
---

専攻や研究内容を記述。
```

---

## Hackathons（`src/content/hackathons/`）

### ハッカソン参加記録

```markdown
---
title: "ハッカソン名"
date: 2024-01-15
award: "最優秀賞"  # 受賞がある場合
url: "https://..."
draft: false
---

成果物や学びを記述。
```

---

## About（`src/content/about/`）

### 自己紹介

```markdown
---
title: "About Me"
draft: false
---

簡潔な自己紹介文。

- 研究バックグラウンド
- ソフトウェアエンジニアリング経験
- 興味分野
```

---

## ファイル命名規則

```
# Projects
code-tips-platform.md
mary-ui-laravel-starter-kit.md

# Research
anomaly-detection-cvpr-2024.md
industrial-inspection-icpr-2023.md

# Work
company-1.md
company-2.md

# Education
university-1.md
university-2.md
```

**ルール**:
- ケバブケース（小文字 + ハイフン）
- 説明的な名前
- 短く明確に

---

## Markdown記法ルール

### 見出し

```markdown
## レベル2見出し（セクション）
### レベル3見出し（サブセクション）
```

レベル1（`#`）は使わない（titleがH1）

### リンク

```markdown
[リンクテキスト](https://example.com)
```

### 画像

```markdown
![代替テキスト](/images/projects/example.png)
```

画像は`public/images/`に配置

### コードブロック

````markdown
```python
def hello():
    print("Hello, World!")
```
````

---

## コンテンツ作成チェックリスト

### Projects
- [ ] Problem / Approach / Impact の構造
- [ ] 技術スタックバッジなし
- [ ] 具体的な成果を記述
- [ ] URLやGitHubリンクを含む

### Research
- [ ] 自分の研究のみ
- [ ] venue, authors, pdf, arxivなど記載
- [ ] Problem / Approach / Impact の構造
- [ ] 他人の論文は含まない

### その他
- [ ] Frontmatterが正しい
- [ ] draft: false（公開する場合）
- [ ] 簡潔で明確な文章
- [ ] 画像パスが正しい

---

## まとめ

- **Projects / Research**: Problem / Approach / Impact 構造で統一
- **技術スタック羅列**: 禁止
- **自分の成果**: のみ記載（他人の論文・サーベイは別サイト）
- **簡潔**: 情報を引き算し、本質を伝える
