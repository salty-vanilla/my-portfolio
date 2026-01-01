---
title: "AI Training Platform for Visual Inspection"
titleJa: "検査AI学習プラットフォーム"
description: "Full-stack platform integrating frontend, backend, and ML training pipeline for visual inspection AI"
image: "../../assets/ai-training-platform.webp"
startDate: "2022-06-01"
endDate: "2023-05-31"
skills: ["Vue", "Flask", "TensorFlow", "AWS", "Docker", "PostgreSQL", "Redis"]
featured: true
featuredOrder: 2
role: "System architecture, full-stack development, ML pipeline integration"
impact: "Enabled non-engineers to train inspection models, reduced training time from days to hours"
---

## Project Overview

検査AI学習アプリケーションの開発。Frontend（Vue）、Backend（Flask）、学習エンジン（TensorFlow）、AWSを統合した設計・実装を担当しました。

## Your Role

- **System Architecture**: フルスタックシステムの設計
- **Frontend Development**: Vue.jsによるUI/UX実装
- **Backend Development**: Flask APIサーバーの構築
- **ML Pipeline**: TensorFlow学習パイプラインの統合
- **Cloud Infrastructure**: AWS上のシステム構築

## Technical Architecture

### Frontend (Vue.js)
- **Data Annotation UI**: 画像アノテーションツール
- **Training Dashboard**: 学習進捗・メトリクス可視化
- **Model Management**: モデルバージョン管理UI
- **Real-time Updates**: WebSocketによるリアルタイム通知

### Backend (Flask)
- **RESTful API**: データ管理・学習制御API
- **Task Queue**: Celeryによる非同期タスク処理
- **Authentication**: JWT-based認証システム
- **Data Pipeline**: 画像前処理・データ拡張

### ML Engine (TensorFlow)
- **Transfer Learning**: 事前学習モデルの活用
- **Hyperparameter Tuning**: 自動ハイパーパラメータ調整
- **Model Evaluation**: 自動評価・検証パイプライン
- **Model Export**: 推論用モデルの最適化

### AWS Infrastructure
- **EC2**: アプリケーションサーバー
- **S3**: 画像・モデルストレージ
- **RDS**: PostgreSQLデータベース
- **ElastiCache**: Redisキャッシュ
- **CloudWatch**: ログ・モニタリング

## Key Features

1. **No-Code Training**: エンジニアでない現場担当者でも学習可能
2. **Rapid Iteration**: データアップロードから学習完了まで数時間
3. **Version Control**: モデルバージョン管理とロールバック
4. **A/B Testing**: 複数モデルの性能比較
5. **Deployment Ready**: 学習済みモデルの自動最適化

## Impact & Results

- **学習時間**: 数日 → 数時間に短縮
- **ユーザビリティ**: 非エンジニアでも学習可能
- **モデル精度**: 継続的な改善サイクルの確立
- **開発速度**: 新規検査項目の立ち上げ期間を大幅短縮

## Technologies Used

- **Frontend**: Vue 3, Vuex, Vue Router, Axios, Chart.js
- **Backend**: Flask, SQLAlchemy, Celery, Redis
- **ML**: TensorFlow, Keras, NumPy, OpenCV
- **Infrastructure**: AWS (EC2, S3, RDS, ElastiCache), Docker, Nginx
- **CI/CD**: GitHub Actions, Docker Compose
