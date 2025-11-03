# Accounting App - 家計簿アプリ

[![iOS](https://img.shields.io/badge/iOS-14.0+-blue.svg)](https://www.apple.com/ios)
[![Swift](https://img.shields.io/badge/Swift-5.5+-orange.svg)](https://swift.org)
[![SwiftUI](https://img.shields.io/badge/SwiftUI-Supported-green.svg)](https://developer.apple.com/swiftui/)

家族で共有できる高機能な家計簿アプリです。CloudKit を使用したリアルタイム同期、レシート OCR、予算管理などの機能を備えています。

## ✨ 主な機能

### 💰 収支管理
- 日々の収入・支出を簡単に記録
- 費目ごとの分類（デフォルト13種類）
- 費目のカスタマイズ（追加・削除可能）
- 家族メンバーによる共同記録

### 👨‍👩‍👧‍👦 家族共有
- CloudKit を使用した安全なデータ共有
- 複数デバイス間での自動同期
- メンバー権限管理（オーナー・メンバー）
- メンバー招待・管理機能

### 📊 予算管理
- 費目ごと・全体の予算設定
- 暦年・会計年度・月次の複数期間対応
- リアルタイム予算進捗表示
- 予算超過時の通知

### 📈 分析・可視化
- 円グラフ・棒グラフ・折れ線グラフ
- 費目別・メンバー別の分析
- 支出トレンド表示
- 収入・支出の比較分析

### 📷 レシート OCR
- カメラでレシートを撮影
- AI による自動テキスト認識
- 金額・日付・店舗名の自動抽出
- 1タップで収支に登録

### 🔄 定期収支
- 給与・定期支出の自動記録
- 日次・週次・月次・年次対応
- スケジュール自動管理
- 設定日に自動で計上

### 🗑️ 削除リクエスト機能
- 他メンバーの収支削除をリクエスト
- 削除理由の記載が必須
- 作成者による承認・拒否
- 透明性のある削除処理

### 🎯 貯蓄目標
- 目標設定と進捗管理
- 期限設定機能
- 進捗率の可視化
- 複数目標の同時管理

### 🌐 多言語対応
- 日本語
- 英語
- 中国語（簡体字）

### 💳 広告・課金
- アプリ内課金（App内課金）
- プレミアム会員（広告非表示）
- 継続的なコンテンツ更新

## 🎯 システム要件

- **iOS**: 14.0以上
- **デバイス**: iPhone、iPad
- **Xcode**: 13.0以上
- **Swift**: 5.5以上

## 🛠️ テクノロジースタック

### フレームワーク・ライブラリ
- **SwiftUI** - UI フレームワーク
- **Core Data** - ローカルデータベース
- **CloudKit** - iCloud データ同期
- **Vision** - OCR テキスト認識
- **StoreKit 2** - App内課金
- **UserNotifications** - ローカル通知

### アーキテクチャ
- **MVVM** - Model-View-ViewModel パターン
- **Repository Pattern** - データアクセス抽象化
- **Dependency Injection** - 依存性注入

## 📁 プロジェクト構成

```
Accounting/
├── Models/                      # ドメインモデル
│   └── DomainModels.swift
├── Views/                       # SwiftUI ビュー
│   ├── DashboardView.swift
│   ├── TransactionListView.swift
│   ├── BudgetView.swift
│   ├── AnalyticsView.swift
│   ├── SavingsGoalView.swift
│   ├── SettingsView.swift
│   ├── DeleteRequestView.swift
│   ├── OnboardingView.swift
│   ├── CameraView.swift
│   └── ReceiptOCRResultView.swift
├── Services/                    # ビジネスロジック
│   ├── AuthenticationManager.swift
│   ├── FamilyGroupManager.swift
│   ├── CategoryService.swift
│   ├── TransactionService.swift
│   ├── BudgetService.swift
│   ├── RecurringTransactionService.swift
│   ├── DeleteRequestService.swift
│   ├── SavingsGoalService.swift
│   ├── NotificationService.swift
│   ├── OcrService.swift
│   ├── CloudKitManager.swift
│   └── StoreKitManager.swift
├── Utils/                       # ユーティリティ
│   ├── LocalizationManager.swift
│   ├── SecurityManager.swift
│   └── PerformanceOptimizer.swift
├── Navigation/                  # ナビゲーション
│   └── NavigationCoordinator.swift
├── Resources/                   # リソース
│   ├── Localizable.strings      # 日本語
│   ├── en.lproj/Localizable.strings     # 英語
│   └── zh.lproj/Localizable.strings     # 中国語
├── Accounting.xcdatamodeld/     # Core Data モデル
├── AccountingApp.swift          # エントリーポイント
├── ContentView.swift            # メイン画面
└── Persistence.swift            # Core Data スタック
```

## 🚀 セットアップ手順

### 1. プロジェクトのクローン
```bash
git clone https://github.com/MasayukiKumazawa/Accounting.git
cd Accounting
```

### 2. Xcode で開く
```bash
open Accounting.xcodeproj
```

### 3. 署名・ビルドセッティング
- Target を選択
- Signing & Capabilities タブを開く
- チーム選択とバンドルID設定
- CloudKit の entitlements を有効化

### 4. ビルド・実行
```bash
⌘ + B   # ビルド
⌘ + R   # 実行
```

## 🧪 テスト実行

### ユニットテスト
```bash
⌘ + U   # Xcode でテスト実行
```

### UIテスト
```bash
# Xcode で UITest ターゲットを選択して実行
⌘ + U
```

## 📋 主要なクラス・構造体

### Models
- `User` - ユーザー情報
- `Transaction` - 収支データ
- `Category` - 費目
- `Budget` - 予算
- `RecurringTransaction` - 定期収支
- `DeleteRequest` - 削除リクエスト
- `SavingsGoal` - 貯蓄目標
- `FamilyMember` - 家族メンバー

### Services
- `AuthenticationManager` - 認証・ユーザー管理
- `FamilyGroupManager` - 家族グループ管理
- `TransactionService` - 収支管理
- `CategoryService` - 費目管理
- `BudgetService` - 予算管理
- `RecurringTransactionService` - 定期収支管理
- `DeleteRequestService` - 削除リクエスト管理
- `SavingsGoalService` - 貯蓄目標管理
- `NotificationService` - 通知管理
- `OcrService` - OCR処理
- `CloudKitManager` - CloudKit 統合
- `StoreKitManager` - App内課金

## 🔐 セキュリティ機能

- **Keychain** - 認証情報の安全な保存
- **CloudKit 暗号化** - 送受信データの暗号化
- **データ保護** - デバイス内データの暗号化
- **エンドツーエンド暗号化** - 家族間通信の暗号化

## 📊 データ構造

### Core Data エンティティ
1. **User** - ユーザー情報
2. **FamilyMember** - 家族メンバー
3. **Category** - 費目
4. **Transaction** - 収支
5. **Budget** - 予算
6. **RecurringTransaction** - 定期収支
7. **DeleteRequest** - 削除リクエスト
8. **SavingsGoal** - 貯蓄目標

### リレーション
- User → FamilyMember (1:多)
- FamilyMember → Transaction (1:多)
- Category → Transaction (1:多)
- Category → Budget (1:多)

## 🎨 UI/UX

### 画面構成（7つのメインタブ）
1. **ダッシュボード** - 今月の収支サマリー、予算進捗
2. **収支** - 月別収支一覧、検索機能
3. **予算** - 予算設定・管理
4. **分析** - グラフ表示（複数種類）
5. **貯蓄** - 貯蓄目標管理
6. **リクエスト** - 削除リクエスト管理
7. **設定** - アプリ設定、メンバー管理

### デザイン言語
- Dark Mode 対応
- アクセシビリティ対応
- iPad 対応

## 📚 ドキュメント

| ドキュメント | 説明 |
|------------|------|
| [🆘 サポート](docs/SUPPORT.md) | よくある質問、トラブルシューティング、お問い合わせ方法 |
| [🔒 プライバシーポリシー](docs/PRIVACY_POLICY.md) | データ保護方針、個人情報の取扱について |
| [📋 App Store公開手順](docs/APP_STORE_RELEASE_GUIDE.md) | Apple App Store に公開するための完全な手順書 |
| [📝 API ドキュメント](docs/API_DOCUMENTATION.md) | 詳細な API ドキュメント |

## 🆘 サポート

ご質問やサポートが必要な場合は、以下からお気軽にお問い合わせください：

- 📖 **[サポートページ](docs/SUPPORT.md)** - FAQ・トラブルシューティング
- 🐛 **[GitHub Issues](https://github.com/MasayukiKumazawa/Accounting/issues)** - バグ報告・機能リクエスト
- 📧 **メール** - support@masayuki-app.com

## 🐛 バグ報告

バグ報告は [GitHub Issues](https://github.com/MasayukiKumazawa/Accounting/issues) から提出してください。

## 📄 ライセンス

MIT License - 詳細は [LICENSE](LICENSE) を参照してください。

## 👥 開発者

Masayuki Kumazawa

## 📧 お問い合わせ

質問や提案は、GitHub Issues または [email@example.com](mailto:email@example.com) までお願いします。

## 🙏 謝辞

- Apple のフレームワーク・ドキュメント
- SwiftUI コミュニティ
- ベータテスターの皆様

---

**最終更新**: 2025年11月1日
