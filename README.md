# 🎙️ Security Voice Code Access — Audio Recognition System

<p align="center">
  <img src="https://img.shields.io/badge/Python-100%25-3776AB?style=for-the-badge&logo=python&logoColor=white" />
  <img src="https://img.shields.io/badge/PyQt5-GUI-41CD52?style=for-the-badge&logo=qt&logoColor=white" />
  <img src="https://img.shields.io/badge/scikit--learn-ML-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white" />
  <img src="https://img.shields.io/badge/librosa-Audio%20Processing-8A2BE2?style=for-the-badge" />
  <img src="https://img.shields.io/badge/RandomForest-Classifier-009688?style=for-the-badge" />
</p>

> A Python desktop application that authenticates users via voice using audio feature extraction (MFCC, ZCR, spectral features) and a trained Random Forest classifier — built as a Digital Signal Processing assignment at Cairo University, Faculty of Engineering.

---

## 📸 Screenshots

> _Add screenshots of the PyQt5 interface here._
>
> Suggested layout:
> | Main Interface | Voice Recording | Authentication Result |
> |---|---|---|
> | `screenshots/main_ui.png` | `screenshots/recording.png` | `screenshots/result.png` |

---

## 📋 Table of Contents

- [Overview](#-overview)
- [How It Works](#-how-it-works)
- [Features](#-features)
- [Tech Stack](#-tech-stack)
- [Audio Features Extracted](#-audio-features-extracted)
- [Getting Started](#-getting-started)
- [Project Structure](#-project-structure)
- [Model Performance](#-model-performance)
- [Academic Context](#-academic-context)

---

## 🔍 Overview

This application implements a **speaker verification system** — a form of biometric authentication that uses a person's voice as a password. The system records an audio sample, extracts discriminative signal features using `librosa`, and classifies the speaker using a pre-trained `RandomForestClassifier` from `scikit-learn`.

The desktop GUI is built with **PyQt5**, providing a clean interface for recording, enrolling users, and triggering access control decisions.

---

## ⚙️ How It Works

```
┌──────────────┐    ┌───────────────────┐    ┌─────────────────────┐
│  Microphone   │───▶│  Audio Preprocessing│───▶│  Feature Extraction │
│  Input (WAV)  │    │  (librosa)          │    │  MFCC · ZCR · RMS   │
└──────────────┘    └───────────────────┘    └──────────┬──────────┘
                                                         │
                                             ┌───────────▼───────────┐
                                             │  RandomForestClassifier│
                                             │  (scikit-learn)        │
                                             └───────────┬───────────┘
                                                         │
                                             ┌───────────▼───────────┐
                                             │  Access Granted / Denied│
                                             │  (PyQt5 GUI Response)  │
                                             └───────────────────────┘
```

---

## ✨ Features

- 🎤 **Real-time voice recording** via PyQt5 interface
- 📊 **Audio feature extraction** using librosa (MFCC, ZCR, spectral centroid, RMS energy)
- 🌲 **Random Forest classifier** for speaker identity verification
- 🔐 **Access control logic** — grant or deny based on voice match confidence
- 🖥️ **Desktop GUI** with PyQt5 — no browser required
- 🧩 **Modular architecture** — audio processing and ML are decoupled into separate classes

---

## 🛠 Tech Stack

| Component | Technology |
|---|---|
| **Language** | Python 3.x |
| **GUI Framework** | PyQt5 |
| **Audio Processing** | librosa |
| **Machine Learning** | scikit-learn (RandomForestClassifier) |
| **Numerical Computing** | NumPy |
| **Audio I/O** | sounddevice / scipy.io.wavfile |

---

## 🎵 Audio Features Extracted

The classifier relies on the following signal features, extracted per audio clip:

| Feature | Description |
|---|---|
| **MFCC** (Mel-Frequency Cepstral Coefficients) | Captures the spectral envelope of the voice — most discriminative feature for speaker ID |
| **ZCR** (Zero Crossing Rate) | Measures signal noisiness and frequency characteristics |
| **RMS Energy** | Represents the loudness/power of the audio signal |
| **Spectral Centroid** | The "center of mass" of the frequency spectrum |
| **Spectral Rolloff** | Frequency below which 85% of signal energy is concentrated |

---

## 🚀 Getting Started

### Prerequisites

```bash
Python 3.8+
pip
```

### Clone the Repository

```bash
git clone https://github.com/mahmoudnasr-gif/DSP-Task5-Security-Voice-code-Access.git
cd DSP-Task5-Security-Voice-code-Access
```

### Install Dependencies

```bash
pip install pyqt5 librosa scikit-learn numpy sounddevice scipy
```

### Run the Application

```bash
python main.py
```

---

## 📁 Project Structure

```
DSP-Task5-Security-Voice-code-Access/
├── main.py           # Application entry point — launches PyQt5 window
├── Task5Ui.py        # PyQt5 UI layout and event handlers
├── class_audio.py    # Audio recording, feature extraction (librosa)
└── trials.py         # Experimental scripts used during development
```

### Key modules

- **`class_audio.py`** — Core ML logic. Handles microphone input, librosa feature extraction, and RandomForest inference.
- **`Task5Ui.py`** — UI layer. Defines the PyQt5 window, buttons, and result display.
- **`main.py`** — Entry point that wires UI and audio classes together.

---

## 📈 Model Performance

> _Fill in your actual results after running the classifier._

| Metric | Value |
|---|---|
| **Classifier** | RandomForestClassifier (scikit-learn) |
| **Training samples** | _(add your dataset size)_ |
| **Accuracy** | _(add your measured accuracy %)_ |
| **False Accept Rate** | _(add FAR if measured)_ |
| **False Reject Rate** | _(add FRR if measured)_ |

---

## 🎓 Academic Context

This project was developed as **DSP Task 5** for the Digital Signal Processing course at Cairo University's Faculty of Engineering (Biomedical & Healthcare Data Engineering, 2024).

The task goal was to implement a biometric voice authentication system using real DSP concepts — audio sampling, feature extraction in the frequency domain, and supervised ML classification.

> *Original team repository: [bassel-hammad/DSP-Task5-Security-Voice-code-Access](https://github.com/bassel-hammad/DSP-Task5-Security-Voice-code-Access)*

---

## 🔮 Future Improvements

- [ ] Replace RandomForest with a deep learning model (CNN on spectrograms)
- [ ] Add speaker enrollment UI (record training samples in-app)
- [ ] Export and reload trained model (joblib/pickle persistence)
- [ ] Add waveform visualization inside the PyQt5 interface
- [ ] Evaluate on a larger, noisier dataset

---

<p align="center">
  <i>Built with Python · PyQt5 · librosa · scikit-learn</i>
</p>
