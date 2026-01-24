# AVVA-curation

🎯 **AVVA: Audio-Video Vector Alignment** - LLM-based curation for data-efficient multimodal foundation models

[![Paper](https://img.shields.io/badge/Paper-EUSIPCO%202025-blue)](https://eurasip.org/Proceedings/Eusipco/Eusipco2025/pdfs/0000286.pdf)
[![IEEE](https://img.shields.io/badge/IEEE-Xplore-00629B)](https://ieeexplore.ieee.org/abstract/document/11226207)
[![Website](https://img.shields.io/badge/Project-Website-green)](https://avva-curation.github.io/AVVA-curation/)
[![License](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

> **Quality Over Quantity? LLM-Based Curation for a Data-Efficient Audio-Video Foundation Model**  
> [Ali Vosoughi](https://alivosoughi.com)¹*, [Dimitra Emmanouilidou](https://www.microsoft.com/en-us/research/people/diemmano/)², [Hannes Gamper](https://www.microsoft.com/en-us/research/people/hagamper/)²  
> ¹University of Rochester, ²Microsoft Research  
> *Work completed during internship at Microsoft Research  
> **EUSIPCO 2025** | European Signal Processing Conference

---

## 📋 Quick Links

- 🌐 **[Project Website](https://avva-curation.github.io/AVVA-curation/)** - Interactive demo and visualizations
- 📄 **[Paper (EUSIPCO)](https://eurasip.org/Proceedings/Eusipco/Eusipco2025/pdfs/0000286.pdf)** - Official proceedings
- 📄 **[Paper (IEEE Xplore)](https://ieeexplore.ieee.org/abstract/document/11226207)** - IEEE digital library
- 💻 **[Code](https://github.com/AVVA-curation/AVVA-curation)** - This repository

---

## 🎯 Overview

**AVVA** (Audio-Video Vector Alignment) addresses the challenge of integrating audio and visual data for training multimodal foundational models by leveraging **Large Language Models (LLMs) for intelligent data curation**.

### Key Achievements

- ✨ **4.45× improvement** in video-to-audio retrieval on AudioCaps (6.23% vs 1.40% DenseAV)
- ✨ **3.52× improvement** on VALOR and **4.29× improvement** on VGGSound for V2A retrieval
- 🚀 **Only 192 hours** of curated training data vs DenseAV's 5,800+ hours
- 🎯 **30× data efficiency** - Quality trades for quantity
- 📊 Evaluated on **AudioCaps, VALOR, and VGGSound** datasets

---

## 🏗️ Architecture

AVVA implements a **dual-encoder structure** with:

1. **Audio Encoder**: Whisper (speech-based foundation model)
2. **Video Encoder**: DINOv2 (vision foundation model)  
3. **Multimodal Reasoning Engine (MRE)**: LLM-based data curation with 5 alignment metrics:
   - ⏱️ Temporal Alignment
   - 🌍 Spatial Coherence
   - 🎯 Contextual Relevance
   - 🔗 Physical Causality
   - 👁️ Sound Source Visibility

The framework enables **direct audio-video alignment without textual mediation** during training, using contrastive learning on carefully curated AV pairs.

---

## 📊 Results

### Video-to-Audio Retrieval (Top-1 Accuracy)

| Dataset | AVVA (192h) | DenseAV Baseline | Improvement |
|---------|-------------|------------------|-------------|
| AudioCaps | **6.23%** | 1.40% | **4.45×** |
| VALOR | **7.75%** | 2.20% | **3.52×** |
| VGGSound | **6.86%** | 1.60% | **4.29×** |

### Audio-to-Video Retrieval (Top-1 Accuracy)

| Dataset | AVVA (192h) | DenseAV Baseline | Improvement |
|---------|-------------|------------------|-------------|
| AudioCaps | **6.57%** | 10.20% | - |
| VALOR | **6.69%** | 7.80% | - |
| VGGSound | **6.71%** | 6.80% | - |

AVVA achieves these results using **only 192 hours** of LLM-curated training data compared to DenseAV's 5,800+ hours, demonstrating that intelligent data curation enables **significant performance improvements** in video-to-audio retrieval with **30× better data efficiency**.

---

## 🚀 Getting Started

### Installation

```bash
# Clone the repository
git clone https://github.com/AVVA-curation/AVVA-curation.git
cd AVVA-curation

# Install dependencies
pip install -r requirements.txt
```

### Quick Start

```python
from avva import AVVAModel, DataCurator

# Initialize the multimodal reasoning engine
curator = DataCurator(
    audio_model="whisper-large",
    video_model="dinov2-large",
    llm_model="mistral-7b"
)

# Score audio-video alignment
scores = curator.score_alignment(
    audio_path="path/to/audio.wav",
    video_path="path/to/video.mp4"
)

# Train AVVA model on curated data
model = AVVAModel()
model.train(curated_data_path="data/curated_192h")
```

---

## 📁 Repository Structure

```
AVVA-curation/
├── avva/                  # Core AVVA implementation
│   ├── models/           # Audio/video encoders
│   ├── curation/         # LLM-based data curation
│   └── training/         # Contrastive learning
├── configs/              # Configuration files
├── scripts/              # Training and evaluation scripts
├── data/                 # Data processing utilities
├── notebooks/            # Demo notebooks
└── docs/                 # Documentation
```

---

## 📖 Citation

If you use AVVA in your research, please cite:

```bibtex
@inproceedings{vosoughi2025quality,
  title={Quality Over Quantity? LLM-Based Curation for a Data-Efficient Audio-Video Foundation Model},
  author={Vosoughi, Ali and Emmanouilidou, Dimitra and Gamper, Hannes},
  booktitle={2025 33rd European Signal Processing Conference (EUSIPCO)},
  year={2025},
  organization={IEEE},
  url={https://eurasip.org/Proceedings/Eusipco/Eusipco2025/pdfs/0000286.pdf}
}
```

**APA Format:**
```
Vosoughi, A., Emmanouilidou, D., & Gamper, H. (2025). Quality Over Quantity? 
LLM-Based Curation for a Data-Efficient Audio-Video Foundation Model. 
In 2025 33rd European Signal Processing Conference (EUSIPCO). IEEE.
```

**IEEE Format:**
```
A. Vosoughi, D. Emmanouilidou, and H. Gamper, "Quality Over Quantity? LLM-Based 
Curation for a Data-Efficient Audio-Video Foundation Model," in 2025 33rd European 
Signal Processing Conference (EUSIPCO), 2025.
```

---

## 🔬 Key Features

### 1. **LLM-Based Data Curation**
- Five-dimensional alignment scoring
- Automated quality assessment
- Intelligent data selection

### 2. **Efficient Training**
- Contrastive learning on AV pairs
- Direct audio-video alignment
- No textual mediation required

### 3. **Foundation Model Integration**
- Whisper for audio understanding
- DINOv2 for visual analysis
- Mistral LLM for reasoning

### 4. **Comprehensive Evaluation**
- AudioCaps, VALOR, VGGSound benchmarks
- Video-to-audio and audio-to-video retrieval
- Top-k accuracy metrics

---

## 📚 Resources

- **[Project Website](https://avva-curation.github.io/AVVA-curation/)** - Interactive visualizations and demos
- **[Paper (EUSIPCO)](https://eurasip.org/Proceedings/Eusipco/Eusipco2025/pdfs/0000286.pdf)** - Full technical details
- **[Paper (IEEE)](https://ieeexplore.ieee.org/abstract/document/11226207)** - IEEE Xplore version
- **[University of Rochester](https://www.rochester.edu)** - Academic affiliation
- **[Microsoft Research](https://www.microsoft.com/en-us/research/)** - Research collaboration

---

## 🤝 Contributing

We welcome contributions! Please see [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 🙏 Acknowledgments

- University of Rochester, Department of Computer Science
- Microsoft Research, Audio and Acoustics Research Group
- EUSIPCO 2025 reviewers and conference organizers

---

## 📧 Contact

- **Ali Vosoughi** - [ali.vosoughi@rochester.edu](mailto:ali.vosoughi@rochester.edu) - [Website](https://alivosoughi.com)
- **Project Website** - [https://avva-curation.github.io/AVVA-curation/](https://avva-curation.github.io/AVVA-curation/)

---

<p align="center">
  <strong>AVVA: Quality Over Quantity for Multimodal Foundation Models</strong><br>
  EUSIPCO 2025 | University of Rochester | Microsoft Research
</p>
