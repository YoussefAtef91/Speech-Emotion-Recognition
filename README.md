# 🎙️ Speech Emotion Recognition (RAVDESS)

This project focuses on classifying emotions from speech using deep learning. Leveraging the **RAVDESS** dataset and the **Librosa** library for feature engineering and augmentation, we trained an **LSTM** model using TensorFlow to recognize a speaker's emotion from audio. The model is deployed via a **LitServe API** using **Lightning AI**.

---

## 📁 Dataset

**Dataset:** [Ryerson Audio-Visual Database of Emotional Speech and Song (RAVDESS)](https://zenodo.org/record/1188976)

* 1440 audio files (.wav, 16-bit, 48kHz)
* 24 actors (12 male, 12 female)
* 8 emotions:
  `neutral`, `calm`, `happy`, `sad`, `angry`, `fearful`, `disgust`, `surprised`
* Two sentences spoken at two intensity levels (normal, strong)

> 📦 Total Files: `60 recordings x 24 actors = 1440 samples`

---

## 🛠️ Project Pipeline

### 🔉 1. **Feature Engineering**

* **Library:** [`librosa`](https://librosa.org/)
* Extracted features:

  * MFCCs (Mel-frequency cepstral coefficients)
  * Chroma features
  * Spectral contrast
  * Tonnetz

### 🔁 2. **Data Augmentation**

* Pitch shifting
* Time-stretching
* Noise injection

### 🧠 3. **Modeling**

* **Architecture:** LSTM (Long Short-Term Memory)
* **Framework:** TensorFlow / Keras
* Loss: Categorical Cross-Entropy
* Optimizer: Adam


---

## 📊 Results

* Model Precision (macro): 72%
* Model Recall (macro): 73% 

---

## 📂 Project Structure

```
├── data/                 # Preprocessed & augmented audio
├── models/               # Saved model weights
├── notebooks/            # EDA & evaluation notebooks
├── src/deplyment         # LitServe API code
├── README.md             # Project documentation
└── pyproject.toml        # Python dependencies
```

---

## 📚 References

* Livingstone, S. R., & Russo, F. A. (2018). The Ryerson Audio-Visual Database of Emotional Speech and Song (RAVDESS): A dynamic, multimodal set of facial and vocal expressions in North American English. *PLOS ONE*.
* [RAVDESS Dataset on Zenodo](https://zenodo.org/record/1188976)
* [Kaggle Version](https://www.kaggle.com/datasets/uwrfkaggler/ravdess-emotional-speech-audio)