---
title: "Digital Twin: Motion Log Collection & Replay System"
titleJa: "デジタルツインのための動作ログ収集・再現基盤"
description: "A microservice-based system for collecting, transforming, and replaying PLC motion logs to enable reproducible digital twin workflows"
image: "../../assets/digital-twin-motion-log.webp"
skills:
  - Industrial Data Platform
  - Digital Twin
  - Event-driven Architecture
  - Rust
featured: false
featuredOrder: 0
role: "System architecture design, microservice development, data pipeline implementation"
startDate: "2024-09-01"
endDate: "2024-12-31"
---

## Overview

PLC を含む実設備の動作状態を収集し、  
**後から同じ挙動を再現できること** を目的とした  
デジタルツイン向けの **動作ログ収集・再現基盤** を設計・実装しました。

本システムでは、  
単なるログ保存ではなく **「時間軸を含めた状態変化を再生可能な形で保持する」** ことを重視しています。

---

## Background / Problem

デジタルツインや設備シミュレーションにおいては、

- 実機が「今どう動いているか」
- 過去に「どのような状態遷移を辿ったか」
- 特定条件下で「なぜその挙動になったか」

を **後から再現できること** が重要になります。

しかし現場では、

- PLC データがそのままでは再利用しづらい
- ログ形式が用途ごとに異なり、再現性がない
- 実機とシミュレーション環境の間にデータの断絶がある

といった課題があり、  
**「データはあるが、再現できない」** 状態になりがちでした。

---

## Design Goals

本システムでは、以下を設計ゴールとしました。

- PLC の状態変化を **時系列イベントとして取得**
- 処理・保存・配信を **用途非依存な中間表現** に変換
- 後段（OPC サーバ / デジタルツイン側）が  
  **任意の形式で再生できる** 構造を作る
- 長時間・高頻度のデータでも **安定して処理できる**

---

## Architecture Overview

本システムは **Rust によるマイクロサービス構成** で実装しています。

### Data Flow

1. **UI / PLC Interface**

   - PLC から設備状態を抽出
   - 状態変化をイベントとして取得

2. **Message Queue (Redis)**

   - 状態イベントをキューに書き込み
   - コンポーネント間を疎結合に分離

3. **Log Processing Services**

   - MQ からイベントを読み出し
   - 任意の形式に変換
     - CSV
     - JSON
     - MongoDB への永続化

4. **Data Export / OPC Integration**

   - MongoDB に保存されたログを元に
   - OPC サーバへデータを送信

5. **Digital Twin / Replay**
   - OPC サーバ上でデータを受信
   - クライアント側で動作再現を実施

---

## Key Design Decisions

### Event-driven Architecture

- 状態を「現在値」ではなく **イベント列** として扱う
- 後から
  - 再生
  - 巻き戻し
  - 条件抽出  
    が可能な構造にした

### Intermediate Representation

- PLC 固有フォーマットをそのまま使わない
- 収集 → 変換 → 配信 を分離し、
  **用途非依存な中間表現** を設計

### Microservices with Rust

- 高頻度・長時間稼働を前提としたため
  - 低オーバーヘッド
  - 安定性
    を重視
- 各サービスを責務単位で分離し、  
  将来的な拡張や差し替えを容易にした

---

## Role

- システム全体のアーキテクチャ設計
- Rust によるマイクロサービスの設計・実装
- PLC データのイベント化と中間表現設計
- MQ を用いた非同期データパイプライン構築
- OPC サーバとのデータ連携設計・実装

---

## Result / Impact

- PLC の動作状態を **再現可能なログ** として取得・保存できるようになった
- データ収集・変換・再生の責務が分離され、
  - 再利用性
  - 拡張性
    が向上
- デジタルツイン側は、
  **実機と同じ状態遷移を再生できる入力** を取得可能になった

---

## Lessons / Insights

- デジタルツインにおいて重要なのは、可視化やUI以前に  
  **後から同じ挙動を再現できるデータ設計** であることを学んだ

- 当時の要件は「動作ログの収集と再生」に限定されていたため、  
  設計意図の説明は最小限に留めつつ、  
  **将来的な活用にも耐えうる再現性と疎結合性を満たす構造** を選択した

- PLC データは単なる現在値として扱うのではなく、  
  **時間軸を持つイベント列として保持することで、  
  再生・検証・シミュレーションへの展開が可能になる**

- ログは保存するだけでは価値がなく、  
  **後段システムが用途に応じて解釈・変換できる中間表現** として設計する必要がある

- 現場データ基盤では、  
  安定性・疎結合・時間軸を最初から設計に含めることで、  
  要件変更や用途拡張に対して壊れにくいシステムになる

---

## Tech Stack (Abstracted)

- Language: Rust
- Architecture: Event-driven Microservices
- Messaging: Message Queue (Redis)
- Storage: Time-series / Document-oriented Storage (MongoDB)
- Integration: OPC-based Data Exchange
- Domain: Digital Twin / Industrial Data Platform
