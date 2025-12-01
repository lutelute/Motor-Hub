# 集中巻きと分布巻きの比較

⚡ モーター巻線方式の教材プロジェクト

## 🚀 ライブデモ

**すぐに試す:** [インタラクティブシミュレーター](https://lutelute.github.io/concentrated_vs_distributed_winding/)

| シミュレーター | 特徴 | デモリンク |
|-------------|------|----------|
| 🤖 **Claude版** | 詳細な技術解析・教育機能特化 | [Demo](https://lutelute.github.io/concentrated_vs_distributed_winding/claude_ver/brushless_motor_sim.html) |
| ✨ **Genspark版** | 直感的UI・リアルタイム調整 | [Demo](https://lutelute.github.io/concentrated_vs_distributed_winding/genspark_ver/brushless_motor_simulator.html) |

## 概要

このプロジェクトは、モーターの集中巻き（Concentrated Winding）と分布巻き（Distributed Winding）の特性を比較・解析するための教材です。2つの異なるAI（Claude、Genspark）によって作成されたインタラクティブシミュレーターで学習できます。

## 巻線方式の特徴

### 集中巻き（Concentrated Winding）
- 各相の巻線が特定のスロットに集中
- 構造がシンプル
- 巻線抵抗が低い
- 高調波成分が多い

### 分布巻き（Distributed Winding）
- 各相の巻線が複数のスロットに分散
- 正弦波に近い磁束分布
- 高調波の低減効果
- 巻線抵抗が高い

## 📁 プロジェクト構成

```
concentrated_vs_distributed_winding/
├── index.html                    # メインランディングページ
├── claude_ver/                   # Claude作成シミュレーター
│   ├── brushless_motor_sim.html # 詳細解析版
│   ├── README.md                # 詳細ドキュメント
│   └── ...                      # GitHub テンプレート等
├── genspark_ver/                # Genspark作成シミュレーター  
│   ├── brushless_motor_simulator.html # 直感的UI版
│   └── README.md                # 使用ガイド
├── concentrated/                # 将来の拡張用
├── distributed/                 # 将来の拡張用
└── comparison/                  # 比較結果用
```

## 🎯 特徴比較

| 項目 | 集中巻き | 分布巻き |
|------|----------|----------|
| 🔧 **製造性** | ✅ 簡単 | ⚠️ 複雑 |
| 📊 **トルクリップル** | ⚠️ 大きい (15-25%) | ✅ 小さい (5-10%) |
| ⚡ **効率** | ✅ 高い | ⚠️ やや低い |
| 🌊 **高調波** | ⚠️ 多い | ✅ 少ない |
| 💰 **コスト** | ✅ 低い | ⚠️ 高い |
| 🎯 **適用例** | 小型・コスト重視 | 高性能・静粛性重視 |

## 🎓 学習効果

- **視覚的理解**: リアルタイムでパラメータ変更の影響を確認
- **定量的分析**: トルクリップル、THD、巻線係数の数値で比較
- **実践的知識**: 設計トレードオフの体感的理解
- **技術文献**: 各シミュレーターに詳細な技術解説付き

## 💻 使用方法

1. [ライブデモ](https://lutelute.github.io/concentrated_vs_distributed_winding/)にアクセス
2. Claude版またはGenspark版を選択
3. パラメータを調整して特性変化を観察
4. 両バージョンで比較学習

## 🔗 参考文献

- Brushless Permanent Magnet Motor Design - Dr. Duane Hanselman
- Electric Motor Drives - R. Krishnan  
- Design of Rotating Electrical Machines - Juha Pyrhönen
- PWEL ワークショップ「つくりながら学ぶブラシレスモータ」

## 🤝 貢献

教育改善のための貢献を歓迎します！詳細は各フォルダの`CONTRIBUTING.md`を参照してください。

---

**Made with AI** 🤖 | **Educational Purpose** 📚 | **Open Source** 💙