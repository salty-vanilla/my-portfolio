---
title: "Automated Visual Inspection System Deployment"
titleJa: "自動外観検査設備の実導入"
description: "Deployment of multiple automated visual inspection systems combining AI-based visual judgment and rule-based image processing under real-world constraints"
image: "../../assets/automated-visual-inspection.webp"
skills: ["Industrial Vision", "AI Inspection", "Image Processing", "System Integration", "Human-in-the-Loop"]
featured: true
featuredOrder: 2
role: "System design, on-site deployment, inspection logic integration"
startDate: "2019-08-01"
endDate: "2022-05-31"
---

## Overview

AI と画像処理を組み合わせた **自動外観検査設備の実導入** に携わりました。  
約 3 年間で **3 つの検査設備** を立ち上げ、いずれも実運用環境で稼働するシステムとして導入しています。

各設備では、

- **AI による官能検査（外観・状態の判断）**
- **画像処理による寸法検査（幾何・数値条件）**

を役割分担させ、  
**現場要件に耐える検査ロジック** を構成しました。

---

## Background / Problem

製造現場における検査工程では、以下のような制約が常に存在します。

- タクトタイム・安定稼働が最優先される
- 誤検出・見逃しの影響が工程全体に波及する
- 官能的な判断（人の目）が必要な項目が残る
- 寸法や位置など、数値で定義できる項目も混在する

AI 単体で全てを解決しようとすると、

- 説明性・再現性が不足する
- 現場での調整やトラブル対応が難しい
- 導入後の改善が属人化する

という問題が顕在化しやすく、  
**AI と従来の画像処理をどう組み合わせるか** が重要な設計課題でした。

---

## Approach & System Design

本プロジェクトでは、  
**「AIに任せる部分」と「ルールで定義すべき部分」を明確に分離** する方針を採用しました。

### Role Separation

- **AI Inspection**
  - 外観のばらつきや官能評価が必要な項目を担当
  - 完全な決定ではなく「判定支援」として設計
- **Image Processing**
  - 寸法・位置・形状など、数値条件で定義可能な検査を担当
  - 再現性と説明性を重視

この分離により、

- AI の不確実性を限定的な範囲に閉じ込める
- 現場での調整・保守を容易にする
- 全体としての検査信頼性を確保する

というバランスを実現しました。

---

## Deployment Characteristics

3 つの検査設備は、それぞれ条件や制約が異なりましたが、  
共通して以下の点を重視しました。

- **安定稼働を最優先**
  - 精度よりも「止まらない」「挙動が予測できる」ことを重視
- **現場調整を前提とした設計**
  - 閾値・判定ロジックを調整可能な形で実装
- **Human-in-the-Loop**
  - AI 判定結果を人が確認・判断できる導線を残す
  - 誤判定時の原因追跡が可能な構成

---

## Role

- 検査要件整理（官能検査 / 寸法検査の切り分け）
- AI 検査ロジックと画像処理ロジックの統合設計
- 現場環境を考慮したシステム全体構成の設計
- 実設備への導入・立ち上げ・調整対応
- 導入後の改善点整理と次設備への横展開

---

## Result / Impact

- AI と画像処理を組み合わせた検査ロジックが、実運用環境で安定稼働
- 官能検査の自動化により、人の負荷を軽減
- 寸法検査は従来手法を活かし、説明性・再現性を維持
- 複数設備への展開を通じて、設計パターンを蓄積

---

## Lessons / Insights

- 現場導入では、AI 精度より **運用時の安定性と説明性** が重要
- 「AI で全部やる」より  
  **AI と画像処理の役割分担** が現実的
- 官能検査の自動化には、必ず **Human-in-the-Loop** が必要
- 現場で得た制約理解が、  
  後の **学習プラットフォーム設計の前提** になった

---

## Tech Stack (Abstracted)

- Inspection Logic: AI-based visual inspection + rule-based image processing
- Learning Strategy: Human-in-the-Loop
- System Integration: Industrial inspection system
- Deployment: On-site production environment
