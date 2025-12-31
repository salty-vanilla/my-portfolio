# Design Rules & Implementation Guidelines

**適用対象**: すべてのコンポーネント・ページ実装

このポートフォリオサイトは**ミニマリスト × モノクロ × 研究者向け**のデザインを採用しています。

---

## デザイン原則

### 1. カラーパレット

**ほぼモノクロのみ使用**

```css
/* 許可される色 */
- グレー階調のみ（white, gray-50～900, black）
- 背景: white, gray-50, gray-100
- テキスト: gray-900, gray-700, gray-600
- ボーダー: gray-200, gray-300

/* アクセント色（最小限のみ） */
- リンクhover: gray-900 or underline
- アクション: 必要であればgray-800～900
```

**参考サイト**: [Nagi](https://nagi-6tu.pages.dev/)

### 2. 余白とレイアウト

```css
/* セクション間の余白 */
- セクション間: py-16 md:py-24 lg:py-32
- コンテナ: max-w-4xl lg:max-w-5xl
- 要素間: space-y-8 md:space-y-12

/* 統一ルール */
- 余白は広めに取る
- 呼吸するスペースを確保
- 情報密度を下げる
```

### 3. タイポグラフィ

```css
/* 見出し */
- H1: text-4xl md:text-5xl lg:text-6xl, font-bold
- H2: text-3xl md:text-4xl, font-bold
- H3: text-2xl md:text-3xl, font-semibold

/* 本文 */
- 通常: text-base md:text-lg
- 小: text-sm md:text-base
- 行間: leading-relaxed

/* フォントウェイト */
- 見出し: font-bold or font-semibold
- 本文: font-normal
- 補足: font-light（控えめに）
```

### 4. 影と枠線

```css
/* 影 - 極小またはなし */
- カード: shadow-sm or shadow-none
- hover: shadow-md（最大でもこの程度）

/* 枠線 - 薄いグレー */
- border: border-gray-200 or border-gray-300
- rounded: rounded-lg or rounded-xl
```

---

## コンポーネント実装ルール

### Hero セクション

```astro
<!-- 構造 -->
<section class="py-24 md:py-32">
  <h1>Computer Science Researcher & Software Engineer</h1>
  <p>Computer Vision / Industrial Anomaly Detection / Web & Cloud Systems</p>
  <p>研究成果を、Webとクラウド基盤で運用可能なプロダクトに落とし込みます。</p>
  
  <!-- CTA -->
  <div>
    <a href="/projects">View Projects</a> <!-- Primary -->
    <a href="/cv">View CV</a> <!-- Secondary -->
  </div>
  
  <!-- Links -->
  <div>
    <a href="/research">Research & Publications</a>
    <a href="https://...">Paper Archive</a>
  </div>
</section>
```

**スタイリング**:
- 中央揃え
- テキストは大きく、余白たっぷり
- CTAボタンは控えめ（border + hover effect）

### カード（Projects / Research）

```astro
<!-- Problem / Approach / Impact 構造 -->
<article class="border border-gray-200 rounded-lg p-6 space-y-4">
  <h3 class="text-2xl font-semibold">プロジェクト名</h3>
  
  <div>
    <h4 class="text-sm font-semibold text-gray-600">Problem</h4>
    <p class="text-gray-700">解決する問題</p>
  </div>
  
  <div>
    <h4 class="text-sm font-semibold text-gray-600">Approach</h4>
    <p class="text-gray-700">アプローチ</p>
  </div>
  
  <div>
    <h4 class="text-sm font-semibold text-gray-600">Impact</h4>
    <p class="text-gray-700">成果・影響</p>
  </div>
</article>
```

**ルール**:
- 技術スタックのバッジは**使わない**
- 構造は統一（Problem / Approach / Impact）
- 装飾は最小限

### Skills セクション

```astro
<!-- カテゴリごとにグルーピング -->
<section>
  <h2>Skills</h2>
  
  <div class="space-y-8">
    <div>
      <h3>Research & Academic</h3>
      <ul class="space-y-2">
        <li>Computer Vision</li>
        <li>Anomaly Detection</li>
      </ul>
    </div>
    
    <div>
      <h3>Software Engineering</h3>
      <ul>...</ul>
    </div>
    
    <div>
      <h3>Web & Cloud</h3>
      <ul>...</ul>
    </div>
  </div>
</section>
```

**ルール**:
- カテゴリは明確に分ける
- リスト形式でシンプルに
- 装飾バッジ不要

---

## 避けるべきこと

❌ **カラフルな配色**（blue-500, green-600など）
❌ **派手なグラデーション**
❌ **大きな影**（shadow-lg, shadow-2xl）
❌ **アニメーション過多**
❌ **技術スタックのバッジ羅列**
❌ **daisyUIのテーマ色**（primary, secondary, accentなど）

---

## daisyUI の使い方

### 許可される使用

```html
<!-- レイアウトユーティリティのみ -->
<div class="container">
<div class="prose">
```

### 避けるべき使用

```html
<!-- ❌ カラフルなコンポーネント -->
<button class="btn btn-primary">
<div class="alert alert-success">
<div class="badge badge-accent">
```

---

## 実装チェックリスト

コンポーネント作成時に確認：

- [ ] 色はグレー階調のみ
- [ ] 余白は広めに確保
- [ ] 影は極小（shadow-sm）またはなし
- [ ] 枠線は薄いグレー（border-gray-200/300）
- [ ] アクセント色は使用していない
- [ ] 技術スタックバッジは使用していない
- [ ] 情報は引き算されている
- [ ] テンプレ感がない

---

## 参考実装

### モノクロリンク

```astro
<a 
  href="/projects" 
  class="text-gray-900 hover:underline hover:text-gray-700 transition-colors"
>
  View Projects
</a>
```

### ミニマルボタン

```astro
<a 
  href="/cv" 
  class="border border-gray-300 px-6 py-2 rounded-lg hover:border-gray-900 hover:bg-gray-50 transition-all"
>
  View CV
</a>
```

### グリッドレイアウト

```astro
<div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
  <!-- カード要素 -->
</div>
```

---

## まとめ

- **ミニマル**: 情報を減らし、余白を増やす
- **モノクロ**: グレー階調のみ
- **落ち着いた**: 派手な装飾・色は使わない
- **研究者向け**: 内容で勝負、UIは脇役

**目的**: 研究・実装・運用を横断できる人間であることを短時間で理解させる
