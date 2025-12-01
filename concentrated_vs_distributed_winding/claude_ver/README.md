# 🔧 Brushless Motor Winding Simulator

**ブラシレスモータ コイル巻き方シミュレーター**

An interactive web-based simulator to visualize and understand how different winding patterns affect brushless motor characteristics.

コイルの巻き方がモータ特性に及ぼす影響を体感できるインタラクティブシミュレーター

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![HTML5](https://img.shields.io/badge/HTML5-E34F26?logo=html5&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/HTML)
[![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?logo=javascript&logoColor=black)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
[![Canvas API](https://img.shields.io/badge/Canvas-API-orange)](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API)

## 🎯 Features / 機能

### Real-time Visualization / リアルタイム可視化

- **Motor Cross-section View** - Animated rotating motor with visible stator slots and rotor magnets
  - モータ断面図 - 回転アニメーション付き
- **2D Winding Pattern Diagram** - Expanded view showing coil placement in each slot
  - 巻線パターン展開図 - 各スロットのコイル配置を2D展開
- **Torque Waveform** - Real-time torque ripple visualization
  - トルク波形 - トルクリップルをリアルタイム表示
- **Back-EMF Waveform** - Three-phase back-EMF with harmonic content
  - 逆起電力波形 - 3相の逆起電力と高調波成分
- **MMF Distribution** - Magnetomotive force distribution comparison
  - 起磁力分布 - 理想正弦波との比較

### Adjustable Parameters / 調整可能パラメータ

| Parameter | Range | Description |
|-----------|-------|-------------|
| Winding Type | Concentrated / Distributed | 巻き方タイプ |
| Slot Count | 9 / 12 / 15 / 18 | スロット数 |
| Pole Count | 8 / 10 / 12 / 14 | 極数 |
| Speed | 100 - 3000 rpm | 回転速度 |
| Load Torque | 0 - 100% | 負荷トルク |

### Key Metrics / 主要指標

- **Average Torque** (Nm) - 平均トルク
- **Torque Ripple** (%) - トルクリップル
- **Back-EMF THD** (%) - 逆起電力の全高調波歪率
- **Winding Factor** - 巻線係数

## 🚀 Quick Start / クイックスタート

### Online Demo / オンラインデモ

Simply open `brushless_motor_sim.html` in a modern web browser. No installation required!

`brushless_motor_sim.html`をモダンブラウザで開くだけ。インストール不要！

```bash
# Clone the repository
git clone https://github.com/yourusername/brushless-motor-simulator.git

# Open in browser
cd brushless-motor-simulator
open brushless_motor_sim.html
```

### Browser Compatibility / ブラウザ互換性

- ✅ Chrome 90+
- ✅ Firefox 88+
- ✅ Safari 14+
- ✅ Edge 90+

## 📚 Understanding Winding Types / 巻き方の理解

### Concentrated Winding / 集中巻き

```
Slot:  [U] [V] [W] [U] [V] [W] ...
       ⊙  ⊙  ⊙  ⊙  ⊙  ⊙
       ⊗  ⊗  ⊗  ⊗  ⊗  ⊗
```

**Advantages / 利点:**
- ✅ Simple winding process - 巻線が簡単
- ✅ Short end turns → Lower copper loss - 端末長が短く銅損減少
- ✅ High slot fill factor - スロット充填率が高い
- ✅ Lower manufacturing cost - 製造コスト低

**Disadvantages / 欠点:**
- ⚠️ Large torque ripple (15-25%) - トルクリップルが大きい
- ⚠️ High harmonic content - 高調波成分が多い
- ⚠️ Higher acoustic noise - 騒音が大きい

**Best for / 適用例:**
- Small motors - 小型モータ
- Cost-sensitive applications - コスト重視
- High torque density - 高トルク密度

### Distributed Winding / 分布巻き

```
Slot:  [UVW] [VWU] [WUV] [UVW] ...
       Layer structure with multiple phases per slot
```

**Advantages / 利点:**
- ✅ Low torque ripple (5-10%) - トルクリップルが小さい
- ✅ Near-sinusoidal back-EMF - 正弦波に近い逆起電力
- ✅ Low harmonic content - 高調波が少ない
- ✅ Higher efficiency - 効率が高い
- ✅ Quieter operation - 静粛性

**Disadvantages / 欠点:**
- ⚠️ Complex winding process - 巻線が複雑
- ⚠️ Higher manufacturing cost - 製造コスト高
- ⚠️ Longer end turns - 端末長が長い

**Best for / 適用例:**
- High-performance motors - 高性能モータ
- Low-noise applications (EVs, drones) - 静粛性重視（EV、ドローン）
- High-efficiency requirements - 高効率要求

## 🎓 Educational Use / 教育利用

This simulator is designed as a learning tool for:
このシミュレーターは以下の学習ツールとして設計:

- **Electrical Engineering Students** - Understanding motor design principles
  - 電気工学の学生 - モータ設計原理の理解
- **Motor Engineers** - Comparing design trade-offs
  - モータエンジニア - 設計トレードオフの比較
- **Hobbyists** - Exploring motor technology
  - ホビイスト - モータ技術の探求

### Key Learning Points / 重要な学習ポイント

1. **Torque Ripple Impact** - How winding pattern affects smoothness
   - トルクリップルの影響 - 巻き方が滑らかさに与える影響

2. **Harmonic Content** - Relationship between winding and back-EMF quality
   - 高調波成分 - 巻き方と逆起電力品質の関係

3. **Winding Factor** - Efficiency of coil placement
   - 巻線係数 - コイル配置の効率

4. **MMF Distribution** - Spatial distribution of magnetic field
   - 起磁力分布 - 磁界の空間分布

## 🔬 Technical Details / 技術詳細

### Implementation / 実装

- **Frontend Only** - Pure HTML5/JavaScript/Canvas - フロントエンドのみ
- **No Dependencies** - Works offline - 依存関係なし、オフライン動作
- **Real-time Calculation** - Physics-based simulation - リアルタイム計算

### Key Formulas / 主要な計算式

**Torque Ripple / トルクリップル:**
```
Torque_Ripple (%) = (T_max - T_min) / T_avg × 100
```

**Winding Factor / 巻線係数:**
```
k_w = k_d × k_p
where k_d: distribution factor, k_p: pitch factor
```

**Back-EMF THD / 逆起電力THD:**
```
THD (%) = √(Σ V_n²) / V_1 × 100
where V_n: n-th harmonic voltage
```

## 📖 Usage Tips / 使い方のコツ

1. **Start with Concentrated Winding** at 50% load
   - まず集中巻きで負荷50%から始める

2. **Switch to Distributed Winding** and observe:
   - 分布巻きに切り替えて観察:
   - Smoother torque waveform - より滑らかなトルク波形
   - Lower ripple percentage - リップル率の低下
   - More sinusoidal back-EMF - より正弦波的な逆起電力

3. **Experiment with Slot/Pole Combinations:**
   - スロット/極数の組み合わせ実験:
   - 12 slot / 10 pole → Good balance (5/6)
   - 9 slot / 8 pole → Higher cogging (4/3)
   - 18 slot / 14 pole → Best performance but complex (9/7)

4. **Adjust Speed** to see back-EMF scaling
   - 速度調整で逆起電力のスケーリングを確認

## 🤝 Contributing / 貢献

This project was created by Claude (Anthropic) as an educational demonstration. Contributions are welcome!

このプロジェクトは教育デモンストレーションとしてClaude (Anthropic)によって作成されました。貢献歓迎！

### Potential Enhancements / 今後の拡張案

- [ ] Add cogging torque visualization
- [ ] Implement PWM control simulation
- [ ] 3D motor visualization using Three.js
- [ ] Current waveform and torque relationship
- [ ] Thermal analysis
- [ ] Efficiency map generation
- [ ] Vector control visualization
- [ ] Parameter optimization suggestions
- [ ] Export data as CSV
- [ ] Multi-language support

## 📄 License / ライセンス

MIT License - Feel free to use for educational and commercial purposes.

MITライセンス - 教育・商用利用自由

## 🙏 Acknowledgments / 謝辞

Created as an example of AI-assisted engineering education tools.

AI支援エンジニアリング教育ツールの例として作成されました。

Special thanks to the open-source community for web technologies that make interactive learning possible.

インタラクティブ学習を可能にするWeb技術のオープンソースコミュニティに感謝します。

## 📬 Contact / 連絡先

For questions or suggestions about this simulator:

このシミュレーターに関する質問や提案:

- Open an issue on GitHub
- Email: your.email@example.com

## 🔗 References / 参考文献

- Brushless Permanent Magnet Motor Design - Dr. Duane Hanselman
- Electric Motor Drives - R. Krishnan
- Design of Rotating Electrical Machines - Juha Pyrhönen

---

**Made with Claude** 🤖 | **Educational Tool** 📚 | **Open Source** 💙

*Note: This is a simplified educational simulator. For actual motor design, consult professional engineering software and conduct physical testing.*

*注: これは教育用の簡易シミュレーターです。実際のモータ設計には専門的なエンジニアリングソフトウェアと物理試験が必要です。*
