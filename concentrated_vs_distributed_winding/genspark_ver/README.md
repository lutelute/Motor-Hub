# 🔧 Brushless Motor Simulator

**ブラシレスモータ シミュレータ - コイルの巻き方がモータ特性に及ぼす影響を体感**

An interactive web-based simulator for visualizing and understanding how coil winding methods affect brushless motor characteristics. Created as an example by [Genspark AI](https://www.genspark.ai/).

![Brushless Motor Simulator](https://img.shields.io/badge/Type-Educational%20Tool-blue) ![License](https://img.shields.io/badge/License-MIT-green) ![HTML5](https://img.shields.io/badge/HTML5-Canvas-orange)

---

## 📖 Overview

This simulator recreates the learning experience from the "Building While Learning Brushless Motors" workshop (つくりながら学ぶブラシレスモータ), allowing users to interactively explore how different coil winding configurations impact motor performance without physical prototyping.

### Key Features

- **🎨 Real-time Motor Visualization**: 3D circular motor structure with rotating rotor
- **📐 2D Winding Diagrams**: Expanded views showing concentrated and distributed winding patterns
- **⚙️ Interactive Parameters**: Adjust coil turns, density, slot count, pole count, and speed
- **📊 Performance Metrics**: Live calculations of torque, efficiency, torque ripple, and copper loss
- **📈 Characteristic Charts**: Torque-speed curves and torque ripple waveforms
- **🔄 Comparative Analysis**: Side-by-side comparison of concentrated vs. distributed winding

---

## 🚀 Quick Start

### Online Demo

Simply open the `brushless_motor_simulator.html` file in any modern web browser. No installation or server required!

```bash
# Clone the repository
git clone https://github.com/yourusername/brushless-motor-simulator.git

# Open in browser
cd brushless-motor-simulator
open brushless_motor_simulator.html
```

Or download and double-click the HTML file to run locally.

---

## 🎮 How to Use

### 1. **Select Winding Type**
- **Concentrated Winding (集中巻)**: Each tooth has an independent coil
- **Distributed Winding (分布巻)**: Coils span multiple teeth

### 2. **Adjust Parameters**
- **Coil Turns** (50-200): Number of wire turns per coil
- **Coil Density** (50-100%): Slot fill factor
- **Slot Count** (9-18): Number of stator teeth
- **Pole Count** (4-12): Number of rotor magnet poles
- **Rotation Speed** (0-3000 rpm): Motor operating speed

### 3. **Run Simulation**
Click the ▶️ **Run Simulation** button to see the motor rotate and observe real-time characteristic changes.

### 4. **Analyze Results**
- Monitor estimated torque, efficiency, torque ripple, and copper loss
- Study torque-speed characteristic curves
- Examine torque ripple waveforms
- Compare performance metrics in the comparison table

---

## 📊 Educational Value

### Understanding Concentrated Winding
✅ **Advantages:**
- Higher efficiency (90-93%)
- Lower copper loss
- Easier manufacturing
- Shorter coil end turns

❌ **Disadvantages:**
- Higher torque ripple (8-12%)
- Moderate torque density
- More harmonic content

### Understanding Distributed Winding
✅ **Advantages:**
- Lower torque ripple (3-5%)
- Higher torque density
- Smoother magnetomotive force (MMF) distribution
- Better for precision applications

❌ **Disadvantages:**
- Lower efficiency (85-88%)
- More complex manufacturing
- Longer coil end turns
- Higher copper consumption

### Key Learning Concepts
- **Slot/Pole Ratio**: Optimal ratios (1.2-1.8) minimize torque ripple
- **Winding Factor**: How coil distribution affects torque production
- **Harmonic Analysis**: Concentrated winding introduces more spatial harmonics
- **Copper Loss vs. Iron Loss**: Trade-offs in motor design
- **MMF Distribution**: How winding patterns create magnetic fields

---

## 🛠️ Technical Details

### Technologies Used
- **HTML5 Canvas**: For all graphics rendering
- **Vanilla JavaScript**: No external dependencies
- **CSS3**: Modern responsive styling
- **Mathematical Models**: Based on brushless DC motor theory

### Motor Model Parameters
- **Type**: 3-phase permanent magnet brushless DC motor
- **Configuration**: Inner rotor type (インナーロータ型)
- **Base Specifications**: 100W, 12V (inspired by workshop motors)
- **Phases**: 3-phase (U, V, W)
- **Control**: Assumes ideal sinusoidal drive

### Calculation Algorithms

The simulator implements simplified models for:

1. **Torque Calculation**
   - Based on coil turns, current density, and air gap flux
   - Speed-dependent torque characteristics
   - Winding type multipliers

2. **Efficiency Estimation**
   - Copper loss from winding resistance
   - Iron loss approximation
   - Mechanical loss modeling

3. **Torque Ripple Analysis**
   - Fundamental component from pole interactions
   - Harmonic components (concentrated winding has 3rd, 5th harmonics)
   - Slot/pole ratio effects

4. **Copper Loss**
   - Proportional to turns squared
   - Inversely proportional to slot fill factor

---

## 📚 Background & Inspiration

This simulator is inspired by the **"つくりながら学ぶブラシレスモータ"** (Building While Learning Brushless Motors) educational workshop series by [PWEL (Japan Power Electronics Association)](https://pwel.jp/). The workshop allows participants to hand-wind coils and assemble actual 100W brushless motors, experiencing firsthand how winding methods affect motor performance.

### Related Resources
- [PWEL Workshop Information](https://pwel.jp/seminars/296)
- [Nidec Motor Basics - Brushless DC Motors](https://www.nidec.com/jp/technology/motor/basic/00019/)
- [CQ Publishing - Motor Coil Winding Techniques](https://www.youtube.com/watch?v=klKtd9L4i0s)

---

## 🎓 Use Cases

### For Students
- Learn brushless motor fundamentals without expensive equipment
- Visualize abstract electromagnetic concepts
- Experiment with different design parameters safely

### For Engineers
- Quick prototyping of winding configurations
- Teaching tool for training sessions
- Design trade-off exploration

### For Educators
- Interactive demonstration for lectures
- Hands-on learning supplement
- Distance learning resource

---

## 🖼️ Screenshots

### Main Interface
The simulator features a clean, intuitive interface with:
- Left panel: Parameter controls and winding type selection
- Right panel: 3D motor visualization and performance metrics
- Bottom section: 2D winding diagrams and characteristic charts

### 2D Winding Diagrams
- **Concentrated Winding Pattern**: Shows individual coils on each tooth
- **Distributed Winding Pattern**: Illustrates coils spanning multiple slots
- **Current Configuration**: Real-time visualization of selected parameters

### Performance Charts
- **Torque-Speed Curve**: Characteristic motor performance envelope
- **Torque Ripple Waveform**: Periodic variation in output torque

---

## 🔬 Future Enhancements

Potential additions for future versions:

- [ ] Magnetic flux density visualization
- [ ] Back-EMF waveform analysis
- [ ] Finite element analysis integration
- [ ] Export data to CSV/JSON
- [ ] Temperature rise estimation
- [ ] Cost analysis based on copper usage
- [ ] Multi-language support expansion
- [ ] Mobile-optimized interface
- [ ] Sound simulation (cogging torque noise)
- [ ] 3D WebGL motor model

---

## 🤝 Contributing

Contributions are welcome! This is an educational tool, and improvements that enhance learning are especially appreciated.

### How to Contribute
1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

### Contribution Ideas
- Improve calculation accuracy
- Add more winding patterns (lap winding, wave winding)
- Enhance visualization quality
- Translate to other languages
- Add more educational tooltips
- Create tutorial videos

---

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

```
MIT License

Copyright (c) 2024 Genspark AI

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

---

## 👏 Acknowledgments

- **PWEL (一般社団法人 日本パワーエレクトロニクス協会)**: For the inspiring workshop concept
- **Motor manufacturers**: For technical documentation and educational resources
- **Open source community**: For web technologies that make this possible
- **Genspark AI**: For creating this educational example

---

## 📞 Contact & Support

- **Created by**: [Genspark AI](https://www.genspark.ai/)
- **Issues**: Please report bugs or suggestions via GitHub Issues
- **Discussions**: Use GitHub Discussions for questions and ideas

---

## 🌟 Show Your Support

If you find this simulator useful for learning or teaching, please consider:
- ⭐ Starring this repository
- 🔄 Sharing with students and colleagues
- 💬 Providing feedback for improvements
- 🤝 Contributing enhancements

---

## 🔗 Related Projects

- [Motor Control Simulator](https://github.com/topics/motor-control)
- [Electric Machine Design Tools](https://github.com/topics/electric-machines)
- [Educational Electronics Simulators](https://github.com/topics/electronics-education)

---

## 📖 Further Reading

### Motor Design Theory
- "Brushless Permanent Magnet Motor Design" by Duane Hanselman
- "Design of Rotating Electrical Machines" by Juha Pyrhönen
- IEEE Papers on concentrated vs. distributed windings

### Online Resources
- [Motor Design Learning Platform - JMAG](https://www.jmag-international.com/jp/motor_design_develop/)
- [ROHM Semiconductor - Motor Basics](https://techweb.rohm.co.jp/product/motor/motor-library/)
- [All About Circuits - Motor Control](https://www.allaboutcircuits.com/technical-articles/)

---

**Built with ❤️ by Genspark AI - Empowering Education Through Interactive Simulation**

*Last Updated: November 2024*
