---
title: "AI Training Platform for Visual Inspection"
titleJa: "外観検査AI 学習プラットフォーム"
description: "A cloud-based, data-centric training platform with human-in-the-loop workflows for reproducible and continuously improvable visual inspection AI"
image: "../../assets/ai-training-platform.webp"
skills:
  - Data-Centric AI
  - Human-in-the-Loop
  - ML Training Pipeline
  - AWS
  - Docker
  - Python
  - TypeScript
featured: true
featuredOrder: 1
role: "System architecture design, full-stack development, ML training pipeline integration"
startDate: "2021-06-01"
endDate: "2023-03-31"
---

## Overview

産業用の外観検査 AI を対象に、  
**学習・評価・再学習をクラウド上で安定的に回すための AI 学習プラットフォーム** のプロトタイプを設計・実装しました。

本プラットフォームでは、モデル改善を個別のチューニングに依存させるのではなく、  
**データとアノテーションを中心に、人の判断を組み込んだ Data-Centric / Human-in-the-Loop な改善プロセス** を成立させることを重視しています。

> ※ 本ページは技術設計・アーキテクチャに焦点を当てたケーススタディです。  
> 組織・製品・導入状況に関する詳細は意図的に省略しています。

---

## Background / Problem

外観検査 AI の開発では、モデル精度以前に **学習プロセスとデータ管理がボトルネック** になることが多くあります。

- データが継続的に増加し、品種や撮像条件が頻繁に変わる
- アノテーション品質や基準が揺れ、学習結果が安定しない
- データセットやモデルの更新履歴が追えず、改善の根拠が残らない
- 評価結果が散在し、「どのデータが効いたのか」が分からない

その結果、  
モデルやハイパーパラメータを調整し続ける **Model-Centric な試行錯誤** に陥り、  
**人の判断を活かしたデータ改善のループが回らない** 状態になりがちでした。

---

## Approach & Architecture

本プロジェクトでは、  
**Model-Centric な最適化から、Human-in-the-Loop を前提とした Data-Centric な改善ループへの転換** を設計の中心に据えました。

### Design Principles

- モデルより **データとアノテーションを改善対象の主軸** に置く
- 判断が必要な箇所には **人が介在できる余地を意図的に残す**
- データセット・モデル・実験条件を **すべてバージョン管理**
- PoC 止まりにせず、クラウドでの **継続運用を前提** に設計する
- 改善の意思決定を「感覚」ではなく **比較可能な履歴** に残す

---

## System Structure

#### Data & Annotation Layer

- 画像データ・アノテーション・撮像条件の一元管理
- データセット単位でのバージョン管理と差分追跡
- 学習・評価結果と紐づく形でのデータ履歴保持

#### Human-in-the-Loop / Active Learning

- 推論結果や不確実性に基づく **追加アノテーション候補のサジェスト**
- 誤検出・見逃しが発生しやすいデータを人が確認・判断
- 人のフィードバックを次の学習データに反映する改善ループ
- アノテーション工数を抑えつつ、学習効果を最大化する設計

#### Frontend

- データセット・アノテーション状況の可視化
- 学習進捗・評価指標の確認
- 実験・モデル・データバージョンの一覧管理と比較
- 人の判断履歴を確認できる UI

#### Backend API

- データ・アノテーション・実験メタ情報の管理
- 非同期タスク制御による長時間ジョブの安定実行
- 認証・権限・データアクセス制御

#### ML Training Pipeline

- 前処理 → 学習 → 評価を一貫した設定で実行
- データセット・モデル・パラメータを含めた再現可能な実験単位
- 学習結果を **次のデータ選別・アノテーション判断** に接続

#### Cloud Infrastructure

- クラウド上での学習ジョブ実行とリソース管理
- 失敗時のリトライや同時実行数制御を含めた安定運用設計
- データ・モデル・メタ情報の永続化

---

## Role

- プラットフォーム全体のアーキテクチャ設計
- Data / Annotation / Model を横断した責務分離の設計
- Frontend / Backend / ML パイプラインの実装
- **Human-in-the-Loop を前提としたデータ改善ループの設計と検証**
- プロトタイプ段階から **安定的に稼働する状態** までの構築

---

## Result / Impact

- データとアノテーションを中心とした改善サイクルを確立
- 人の判断を組み込むことで、モデル変更に依存しない改善が可能に
- 実験条件・データ・モデルの関係が整理され、再現性が向上
- **Human-in-the-Loop な Data-Centric 学習基盤** として成立

---

## Lessons / Insights

- 外観検査 AI では、モデルより **データ設計と人の判断が性能を支配する**
- アノテーションは「量」ではなく **どのデータに人が介入するか** が重要
- 能動学習はアルゴリズムではなく **Human-in-the-Loop な運用設計の問題**
- 学習基盤は「自動化」より **改善が回り続ける構造** が価値になる

---

## Tech Stack

- Frontend: Web UI (Vue.js + TypeScript)
- Backend: Web API / Asynchronous Job Control (Flask)
- ML: Training & Evaluation Pipeline (Python, TensorFlow)
- Data Management: Dataset / Annotation / Versioning
- Learning Strategy: Human-in-the-Loop / Active Learning

## Infrastructure (Implementation Example)

- Cloud: AWS
- Containerization: Docker
- Compute & Job Orchestration: AWS ECS (long-running training jobs)
- Storage: Amazon S3 (image data, model artifacts)
- Database: Amazon RDS (PostgreSQL for metadata management)
- Queuing: Amazon SQS (asynchronous task queue)
- Infrastructure as Code: AWS CDK