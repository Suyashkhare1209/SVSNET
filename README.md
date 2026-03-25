# 🧠 SVSNet: Scalable Vision for Stress Detection using Multimodal Physiological Signals

![Status](https://img.shields.io/badge/Manuscript-Minor%20Revision-brightgreen)

![Journal](https://img.shields.io/badge/Journal-Biomedical%20Signal%20Processing%20and%20Control-blue)

![Indexing](https://img.shields.io/badge/Index-SCI%20%7C%20Q1-orange)

---

## 📌 Overview

SVSNet is a deep learning framework for **subject-independent stress detection** using multimodal physiological signals, including **EEG, EDA, BVP, and temperature (TEMP)**.

The model is designed to overcome the **generalization bottleneck** in physiological computing by learning robust representations that transfer across individuals **without per-user calibration**.

---

## 🚀 Key Contributions

* 🔬 **Knowledge-Transitive Architecture**  
  Learns generalized stress representations and adapts to unseen subjects via transfer learning.

* 🧠 **Multimodal Deep Fusion**  
  Integrates signals from:
  - Central Nervous System (**EEG**)  
  - Peripheral Nervous System (**EDA, BVP, TEMP**)  

* ⏱ **Temporal Modeling with BiLSTM**  
  Captures both short-term and long-term physiological dynamics.

* 🎯 **Attention-Based Fusion Mechanism**  
  Dynamically weights modality contributions for each sample.

* 🧹 **Rigorous Preprocessing Pipeline**
  - Bandpass filtering  
  - Wavelet denoising  
  - Detrending  
  - Normalization  

---

## 🏗️ Architecture

SVSNet follows a **dual-branch architecture**:

### 🔹 EEG Branch
* CNN layers → spectral-spatial feature extraction  
* BiLSTM → temporal modeling  

### 🔹 Peripheral Signal Branch (EDA, BVP, TEMP)
* CNN → signal-specific features  
* BiLSTM → temporal dependencies  

### 🔹 Fusion Layer
* Attention-based multimodal fusion  

### 🔹 Classifier
* Fully connected layers for stress classification  

---

## 📊 Performance

### 🔸 Binary Classification (Low vs High Stress)
* **Accuracy:** 90.31%  
* **Precision:** 90.28%  
* **Recall:** 90.22%  
* **F1-score:** 90.25%  
* **AUC:** 96.64%  

### 🔸 Multiclass Classification
* **Accuracy:** 76.28%  

---

## 📈 Comparison with Baselines

| Model Type            | Accuracy |
|---------------------|---------|
| Random Forest        | 57.00%  |
| XGBoost              | 59.02%  |
| EEG-only CNN         | ~66%    |
| Transformer (TST)    | 72.32%  |
| Informer             | 75.86%  |
| **SVSNet (Proposed)**| **90.31%** |

👉 SVSNet significantly outperforms:
* Traditional ML models  
* Unimodal deep learning  
* Transformer-based architectures  

---

## ⚡ Why SVSNet Works Better

* Captures **local + global temporal patterns** (CNN + BiLSTM)  
* Learns **modality-specific representations**  
* Uses **attention to suppress noisy signals**  
* Strong preprocessing ensures **clean physiological inputs**  

---

## 🧪 Results Visualization

The repository includes:

* Accuracy curves  
* F1-score curves  
* Confusion matrices  
* ROC curves  
* Classification reports  


## ⚙️ How to Run
1. Clone the repo
git clone https://github.com/Suyashkhare1209/SVSNET.git
and cd SVSNET
2. Install dependencies
pip install torch numpy matplotlib scikit-learn
3. Run notebook

Open:

main.ipynb
##  📁 Dataset

The dataset consists of:

EEG (4 channels, 256 Hz)
EDA
BVP
Temperature

Each sample represents a 10-second physiological window.

⚡ Computational Efficiency
~0.105 Million parameters
Inference latency: ~0.155 ms per sample

6400 samples/sec throughput

👉 Suitable for real-time wearable deployment

## ⚠️ Limitations
Dataset size: 24 subjects
Generalization to larger populations needs further validation
Chronic vs acute stress differentiation not explored
🔮 Future Work
Cross-modal self-attention mechanisms
Larger and more diverse datasets
Real-world vs lab environment analysis
Temporal stress dynamics modeling

## 📌 Conclusion

SVSNet demonstrates that high-accuracy stress detection is possible without subject-specific calibration, making it a strong candidate for real-world wearable health monitoring systems.
