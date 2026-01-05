---
title: "Drawing Analysis–Based Estimation RPA System"
titleJa: "図面解析による見積積算RPAシステム"
description: "RPA system using drawing analysis AI for automated cost estimation, from internal tool to external product"
image: "../../assets/drawing-analysis-rpa.webp"
startDate: "2023-06-01"
skills: ["React", "NestJS", "ONNX Runtime", "AWS", "TypeScript", "PostgreSQL", "Docker", "Python"]
featured: true
featuredOrder: 3
role: "Full-stack development, AI inference engine implementation, product expansion"
impact: "Automated 80% of estimation tasks, expanded from internal use to external product offering"
---

## Project Overview

図面解析AIを用いた見積積算RPAシステム。社内向け業務自動化ツールから社外向けプロダクト展開まで、フルスタック開発と推論エンジン実装を担当しました。

## Your Role

- **Full-stack Development**: React + NestJSによるアプリケーション開発
- **AI Inference Engine**: ONNX Runtimeによる推論エンジン実装
- **Product Development**: 社内ツールから外販プロダクトへの拡張
- **AWS Infrastructure**: スケーラブルなクラウド基盤の構築

## Technical Architecture

### Frontend (React + TypeScript)
- **Drawing Viewer**: PDF/CAD図面ビューワー
- **Annotation Tool**: AI検出結果の確認・修正UI
- **Estimation Dashboard**: 積算結果の可視化・編集
- **Workflow Management**: 承認フロー・タスク管理

### Backend (NestJS + TypeScript)
- **API Gateway**: RESTful API・GraphQL
- **Business Logic**: 見積計算ロジック・ワークフロー制御
- **Authentication**: Role-based access control
- **Integration**: 既存システムとの連携API

### AI Inference Engine (ONNX Runtime)
- **Drawing Analysis**: 図面からの情報抽出
- **Object Detection**: 部品・寸法の自動検出
- **OCR Pipeline**: 文字認識・データ構造化
- **Batch Processing**: 大量図面の並列処理

### AWS Infrastructure
- **ECS**: コンテナオーケストレーション
- **S3**: 図面ファイルストレージ
- **RDS**: PostgreSQLデータベース
- **Lambda**: サーバーレス処理
- **SQS**: 非同期タスクキュー
- **CloudFront**: CDN配信

## Project Evolution

### Phase 1: Internal Tool
- 社内見積業務の自動化
- 特定フォーマット図面への対応
- 基本的な積算ロジック

### Phase 2: Generalization
- 多様な図面フォーマットへの対応
- 推論精度の向上
- ユーザビリティ改善

### Phase 3: External Product
- マルチテナント対応
- カスタマイズ可能な積算ルール
- エンタープライズ機能追加
- SaaS化対応

## Key Features

1. **Automated Drawing Analysis**: AI自動解析による工数削減
2. **Flexible Rules Engine**: 業種・企業別の積算ルール設定
3. **Human-in-the-Loop**: AI結果の確認・修正ワークフロー
4. **Integration Ready**: 既存システムとのAPI連携
5. **Multi-tenant**: 複数企業の安全な運用

## Impact & Results

- **業務効率**: 見積作成時間を80%削減
- **精度向上**: 人的ミスの削減、見積精度の標準化
- **事業拡大**: 社内ツールから外販プロダクトへ
- **顧客価値**: 複数企業での導入実績

## Technologies Used

- **Frontend**: React 18, TypeScript, TanStack Query, Zustand, Tailwind CSS
- **Backend**: NestJS, TypeScript, TypeORM, PostgreSQL
- **AI/ML**: ONNX Runtime, Python, OpenCV, Tesseract OCR
- **Infrastructure**: AWS (ECS, S3, RDS, Lambda, SQS), Docker, Terraform
- **CI/CD**: GitHub Actions, AWS CodePipeline
