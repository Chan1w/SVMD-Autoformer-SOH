# 🚀 SVMD-FAC-net  
## A Lightweight Multiscale Signal Learning Framework for Battery Degradation Trajectory Prediction

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)]()
[![PyTorch](https://img.shields.io/badge/PyTorch-2.0+-red.svg)]()
[![IEEE Sensors Journal](https://img.shields.io/badge/Published-IEEE%20Sensors%20Journal-005BAC.svg)]()
[![Status](https://img.shields.io/badge/Status-Active-success.svg)]()

---

## 🔬 Background & Motivation

Accurate degradation trajectory prediction is essential for:

- Battery health monitoring  
- Remaining useful life (RUL) estimation  
- Safety management of electric vehicles  

Battery degradation signals exhibit:

- Strong nonlinearity and nonstationarity  
- Multiscale temporal coupling  
- Periodic regeneration phenomena  

Existing deep learning methods (CNN, LSTM, Transformer) often:

1. Fail to explicitly separate multiscale components  
2. Over-parameterize temporal modeling  
3. Ignore intrinsic frequency characteristics  

To address these limitations, we propose a multiscale decomposition-based lightweight prediction framework.

---

## 🧠 Proposed Method: SVMD-FAC-net

The proposed framework integrates adaptive signal decomposition with efficient temporal modeling.

### 1️⃣ Successive Variational Mode Decomposition (SVMD)

The raw capacity sequence is adaptively decomposed into:

- **Intrinsic Mode Functions (IMFs)** – capturing high-frequency fluctuation components  
- **Residual (RES)** – representing low-frequency degradation trend  

SVMD automatically determines the number of modes, avoiding manual hyperparameter tuning and reducing mode mixing.


### 2️⃣ Frequency-Aware Auto-Correlation Module (FAC)

For IMF prediction, we design a lightweight Auto-Correlation Module that:

- Detects dominant periodic patterns via FFT  
- Aggregates similar temporal segments  
- Enhances periodic feature modeling  
- Reduces computational complexity compared to standard self-attention  


### 3️⃣ Lightweight Parallel Prediction Architecture

Separate networks are constructed for:

- IMF components (high-frequency modeling)  
- Residual component (trend modeling)  

Final degradation trajectory is reconstructed by summing predicted components.

The framework supports:

- Multi-step trajectory prediction  
- Robust generalization across datasets  
- Lightweight deployment with reduced inference latency  

---

## 💻 Environment

- torch==2.0.0+cu118
- numpy==1.22.4
- pandas==1.4.2
- matplotlib==3.6.0
- scikit-learn== 1.0.2

```
pip install -r requirements.txt
```

---

## 🏃 Training & Testing
```
python main.py
```

Hyperparameters (learning rate, window size, decomposition parameters) can be modified in configuration files or script arguments.

---

## 📌 Citation

If you find SVMD-FAC-net useful, please consider citing:

```bibtex
@article{shen2025svmd,
  title={A Lightweight Multiscale Signal Learning Framework for Predicting Battery Degradation Trajectory},
  author={Shen, Quanyong and Li, Jian and Nie, Jiahao and Bao, Zhengyi and Wang, Chenhan},
  journal={IEEE Sensors Journal},
  year={2025}
}
