# 📚 モーター学習教材プロジェクト - 開発ガイド

## 🎯 プロジェクト概要

このプロジェクトは、Git subtreeを使用した分散型教材開発システムです。各教材は独立したGitHubリポジトリとして管理され、必要に応じて統合・分離できる柔軟な構造を採用しています。

## 📁 プロジェクト構造

### 🏗️ 現在の構成

```
GitHub/EducationalProjects/Motor/
├── Motor-Hub/                    # 教材ポータルサイト
│   ├── README.md                 # プロジェクト全体説明
│   └── EDUCATIONAL_PROJECT_GUIDE.md  # この開発ガイド
├── Motor-WindingComparison/      # 巻線方式比較シミュレーター
│   ├── index.html               # メインシミュレーター
│   ├── claude_ver/              # Claude作成版
│   └── genspark_ver/            # Genspark作成版
└── Motor-InrushCurrent/         # 突入電流解析シミュレーター
    ├── index.html               # メインシミュレーター
    └── jsx/                     # React JSXソース
```

### 🌐 公開URL構成

```
https://lutelute.github.io/Motor-Hub/                    # メインポータル
https://lutelute.github.io/Motor-WindingComparison/      # 巻線比較教材
https://lutelute.github.io/Motor-InrushCurrent/          # 突入電流教材
```

### 📦 GitHubリポジトリ構成

1. **Motor-Hub** - 教材ポータル・統合管理用
2. **Motor-WindingComparison** - 巻線方式比較教材
3. **Motor-InrushCurrent** - 突入電流解析教材

## 🔄 開発ワークフロー

### Phase 1: 独立開発段階
各教材は独立したリポジトリで開発・テスト・改善を行います。

### Phase 2: 統合検討段階  
共通コンポーネントや相互連携が必要になった時点で統合を検討します。

### Phase 3: subtree統合
必要に応じてsubtreeを使用して教材を統合・分離します。

## 📋 教材要件・標準

### 🎨 技術スタック標準

#### フロントエンド
- **HTML5/CSS3**: レスポンシブデザイン
- **JavaScript/React**: インタラクティブUI
- **Canvas/SVG**: グラフィックス・可視化
- **CDN使用**: 外部ライブラリはCDN経由で読み込み

#### 可視化ライブラリ
- **Recharts**: データ可視化（推奨）
- **D3.js**: 高度なカスタムグラフィックス
- **Three.js**: 3D可視化（必要に応じて）

#### スタイリング
- **Tailwind CSS**: ユーティリティファーストCSS（推奨）
- **カスタムCSS**: 独自スタイル

### 📝 ファイル構成標準

各教材リポジトリは以下の構成を推奨：

```
Motor-[教材名]/
├── README.md                    # 教材説明・使用方法
├── index.html                   # メインシミュレーター
├── src/                         # ソースコード（開発用）
│   ├── components/              # Reactコンポーネント
│   ├── utils/                   # ユーティリティ関数
│   └── data/                    # データファイル
├── docs/                        # ドキュメント
│   ├── theory.md                # 理論説明
│   ├── usage.md                 # 使用方法
│   └── development.md           # 開発ガイド
├── assets/                      # 静的ファイル
│   ├── images/                  # 画像ファイル
│   └── icons/                   # アイコン
└── examples/                    # 使用例・サンプル
    ├── basic_example.html       # 基本例
    └── advanced_example.html    # 応用例
```

### 🎯 教材品質基準

#### 機能要件
- [x] **レスポンシブデザイン**: モバイル・タブレット対応
- [x] **インタラクティブ性**: リアルタイムパラメータ調整
- [x] **視覚化**: グラフ・図表による分かりやすい表示
- [x] **教育効果**: 理論と実践の橋渡し

#### 技術要件  
- [x] **GitHub Pages互換**: 静的サイトとして動作
- [x] **パフォーマンス**: 高速ロード・滑らかな動作
- [x] **アクセシビリティ**: 誰でも使える設計
- [x] **ブラウザ対応**: Chrome, Firefox, Safari, Edge

#### ドキュメント要件
- [x] **README.md**: 教材概要・使用方法
- [x] **理論説明**: 物理・数学的背景
- [x] **開発ドキュメント**: コード説明・拡張方法

## 🚀 新教材追加手順

### Step 1: 企画・設計

1. **教材テーマ決定**
   - 学習目標の明確化
   - 対象読者の設定
   - 既存教材との差別化

2. **技術設計**
   - 使用ライブラリの選定
   - UI/UXデザイン
   - データ構造設計

### Step 2: 独立開発

```bash
# 1. 新しいGitHubリポジトリ作成
gh repo create Motor-[教材名] --public --description "[教材説明]"

# 2. ローカル開発環境準備
mkdir Motor-[教材名]
cd Motor-[教材名]
git init
git remote add origin https://github.com/lutelute/Motor-[教材名].git

# 3. 初期ファイル構成作成
mkdir {src,docs,assets,examples}
touch README.md index.html

# 4. 開発・テスト
# ...コーディング...

# 5. 初期コミット・プッシュ
git add .
git commit -m "Initial commit: [教材名] simulator"
git push -u origin main

# 6. GitHub Pages有効化
gh api repos/lutelute/Motor-[教材名]/pages -X POST \
  --field 'source[branch]=main' --field 'source[path]=/'
```

### Step 3: Hub統合（オプション）

教材が完成し、ポータルサイトからリンクしたい場合：

```bash
# Motor-Hubリポジトリで実行
cd Motor-Hub/

# 新教材をsubtreeとして追加
git remote add [教材名]-origin https://github.com/lutelute/Motor-[教材名].git
git subtree add --prefix=[教材名] [教材名]-origin main --squash

# READMEやindex.htmlを更新して新教材へのリンクを追加
# ... 編集作業 ...

git add .
git commit -m "Add [教材名] integration"
git push hub-origin main
```

### Step 4: 将来の分離（必要に応じて）

```bash
# 統合された教材を再度独立させる場合
git subtree push --prefix=[教材名] [教材名]-origin main
git rm -r [教材名]/
git commit -m "Separate [教材名] - now independent repo"
```

## 🎓 教材開発ガイドライン

### 💡 教育設計原則

1. **段階的学習**: 基本→応用→発展の流れ
2. **視覚的理解**: 複雑な概念を図解で説明
3. **体験型学習**: パラメータ調整による探索的学習
4. **実践応用**: 実際の設計・解析への適用

### 🎨 UI/UXガイドライン

#### 配色ルール
```css
/* 推奨カラーパレット */
:root {
  --primary: #3B82F6;      /* メインブルー */
  --secondary: #1F2937;    /* ダークグレー */
  --accent: #F59E0B;       /* オレンジ */
  --success: #22C55E;      /* グリーン */
  --warning: #EF4444;      /* レッド */
  --background: #111827;   /* ダークバックグラウンド */
  --text: #D1D5DB;         /* ライトグレーテキスト */
}
```

#### レイアウト原則
- **3カラムレイアウト**: パラメータ | 可視化 | 結果
- **レスポンシブ**: モバイルでは縦積み
- **アクセシビリティ**: 十分なコントラスト・フォントサイズ

### 📊 可視化ベストプラクティス

1. **リアルタイム更新**: パラメータ変更の即座反映
2. **複数視点**: 時間軸・周波数軸・空間軸での表示
3. **比較機能**: Before/After, 複数ケースの重ね合わせ
4. **エクスポート**: 結果のPNG/CSV出力機能

### 🧪 テスト・検証

#### 機能テスト
- [ ] 全ブラウザでの動作確認
- [ ] モバイル端末での操作性
- [ ] パフォーマンス測定（ロード時間・応答性）

#### 教育効果検証
- [ ] 学習目標の達成確認
- [ ] ユーザビリティテスト
- [ ] 専門家レビュー

## 🤖 Claude向け理解ポイント

### 🔍 プロジェクト理解のために

このプロジェクトを引き継ぐ際は、以下を最初に確認してください：

1. **現在の構造把握**
```bash
# リモートリポジトリ一覧
git remote -v

# 現在のブランチ・コミット状況  
git status
git log --oneline -10

# subtreeの状態確認
git log --grep="Subtree" --oneline
```

2. **各教材の状態確認**
```bash
# 各リポジトリのPages状況
gh api repos/lutelute/Motor-Hub/pages
gh api repos/lutelute/Motor-WindingComparison/pages  
gh api repos/lutelute/Motor-InrushCurrent/pages
```

3. **開発環境の確認**
```bash
# 必要ツールの確認
which gh git node npm

# プロジェクト依存関係
ls package*.json requirements*.txt 2>/dev/null || echo "No dependency files"
```

### 🎯 作業パターン例

#### パターンA: 既存教材の改善
```bash
# 該当する独立リポジトリで直接作業
cd Motor-[教材名]/
# ... 修正作業 ...
git commit -m "Improve [feature]"
git push origin main
```

#### パターンB: 新教材の追加
```bash
# 新教材開発手順（上記Step 1-4に従う）
gh repo create Motor-[新教材名] --public
# ... 開発 ...
# 必要に応じてHub統合
```

#### パターンC: 教材統合・分離
```bash
# subtree操作（慎重に実行）
git subtree add/push/pull --prefix=[教材名] [remote] main
```

### ⚠️ 注意事項

1. **subtree操作は慎重に**: 履歴が複雑になる可能性
2. **Pages反映時間**: 変更が反映されるまで数分かかる場合あり
3. **CDN依存**: 外部ライブラリの可用性に注意
4. **ブラウザキャッシュ**: 開発時は強制リロード推奨

### 🔧 トラブルシューティング

#### よくある問題と解決法
```bash
# subtreeプッシュエラー
git subtree push --prefix=[path] [remote] main --squash

# Pages表示されない場合
gh api repos/lutelute/[repo]/pages/builds -X POST

# リモート競合の解決
git fetch [remote]
git subtree pull --prefix=[path] [remote] main --squash
```

---

**🎯 目標**: 各教材の独立性を保ちながら、プロジェクト全体として統一感のある学習体験を提供

**🚀 拡張性**: 新しい教材やコラボレーターが容易に参加できる構造

**📚 持続性**: 長期的な保守・改善が可能な設計