# 🌿 AI Crop Disease Detection

An end-to-end **Deep Learning + Generative AI application** for detecting crop diseases and pests from leaf images. The system uses a fine-tuned **ResNet50 CNN** to classify **22 crop disease and healthy classes**, then integrates **Google Gemini 1.5 Flash** to generate disease explanations, treatment recommendations, and preventive measures — deployed as an interactive **Streamlit** web app.

---

## 📌 Project Overview

Early detection of crop diseases helps reduce crop losses and enables timely intervention. This project combines **Computer Vision** and **Generative AI** to analyze crop leaf images and deliver actionable agricultural insights.

**Supported crops:** 🌰 Cashew · 🌱 Cassava · 🌽 Maize · 🍅 Tomato

### Pipeline

```text
Leaf Image → Preprocessing → Fine-Tuned ResNet50 → Disease/Healthy Classification
           → Gemini 1.5 Flash → Explanation + Treatment + Prevention Guidance
```

---

## ✨ Features

- **Multi-class classification** — 22 disease, pest, and healthy classes across multiple crops
- **Transfer learning & fine-tuning** — pretrained CNN backbone adapted to crop disease data
- **Generative AI insights** via Gemini — disease description, symptoms, causes, treatment, prevention, and additional guidance
- **Robust data pipeline** — image validation, corrupted-image removal, TensorFlow decoding, augmentation, and train/val/test splitting (original dataset ~1.35 GB)
- **Automatic model retrieval** — downloads trained weights from external storage on first run, avoiding GitHub's file-size limits
- **Interactive Streamlit app** — upload an image and get prediction, AI explanation, and recommendations in one view

---

## 🧠 Model Development

**1. Data Cleaning** — TensorFlow-based decoding/validation pipeline to detect and remove corrupted or unreadable images from the ~1.35 GB dataset.

**2. Preprocessing** — validation, decoding, resizing, normalization, and augmentation (to improve generalization and reduce overfitting).

**3. Architecture Evaluation**

| Architecture | Role |
|---|---|
| ANN | Baseline |
| Custom CNN | Baseline computer vision model |
| VGG16 | Transfer learning |
| ResNet50 | Transfer learning + fine-tuning (**selected**) |
| EfficientNetB3 | Architecture evaluation |
| DenseNet121 | Architecture evaluation |

**4. Two-Stage Fine-Tuning**
- *Stage 1 — Transfer learning:* pretrained ResNet50 backbone frozen; new classification layers trained.
- *Stage 2 — Fine-tuning:* selected backbone layers unfrozen and trained at a lower learning rate.

**5. Regularization** — data augmentation, dropout, L2 regularization, controlled learning rate, transfer learning, fine-tuning.

---

## 📊 Model Performance

| Metric | Result |
|---|---|
| Test Accuracy | **85.62%** |
| Number of Classes | **22** |
| Dataset Size | **~1.35 GB** |
| Primary Model | **ResNet50** |

Accuracy was measured on an unseen test set.

> Accuracy alone doesn't fully capture multi-class performance. Planned evaluation additions: per-class precision, recall, F1-score, and a confusion matrix.

---

## 🛠️ Tech Stack

- **Language:** Python
- **Deep Learning:** TensorFlow, Keras, CNN, ResNet50, DenseNet121, VGG16, EfficientNetB3, Transfer Learning, Fine-Tuning, Data Augmentation, L2 Regularization, Dropout
- **Generative AI:** Google Gemini API (Gemini 1.5 Flash)
- **Image Processing:** Pillow (PIL), NumPy
- **Application:** Streamlit
- **Training:** Google Colab (GPU)

---

## 📁 Project Structure

```text
AI-Crop-Disease-Detection/
├── app.py
├── requirements.txt
├── README.md
├── model/
├── notebooks/
├── src/
└── assets/
```

---

## 🚀 Installation & Setup

**Prerequisites:** Python 3.9+, pip, Google Gemini API key

```bash
# 1. Clone the repository
git clone <YOUR_REPOSITORY_URL>
cd AI-Crop-Disease-Detection

# 2. Create a virtual environment
python3 -m venv venv
source venv/bin/activate      # Windows: venv\Scripts\activate

# 3. Install dependencies
pip install -r requirements.txt
```

**4. Configure Gemini API** — create a `.env` file in the project root:

```env
GEMINI_API_KEY=your_api_key_here
```

> Never commit API keys or other secrets to GitHub.

**5. Run the app**

```bash
streamlit run app.py
```

The app starts locally and prints a URL to open in your browser.

---

## 🖥️ Usage

1. Launch the Streamlit app.
2. Upload a crop leaf image.
3. The image is validated and preprocessed.
4. The fine-tuned ResNet50 model predicts the disease/health class.
5. The prediction is passed to Gemini.
6. Gemini generates an explanation and agricultural recommendations.
7. Results are displayed in the app.

---

## 🎯 What This Project Demonstrates

Data cleaning & preprocessing · Computer Vision · Deep Learning · Transfer Learning · Fine-Tuning · CNN architecture evaluation · Model regularization & evaluation · Generative AI integration · API integration · Model deployment · Streamlit development · Large model artifact management

This goes beyond a standard image-classification notebook by pairing a deep learning classifier with Generative AI and an interactive deployment layer.

---

## 🔮 Future Improvements

- **Disease localization** — integrate YOLOv8 to detect and localize infected regions, not just classify the whole leaf
- **Mobile deployment** — convert to TensorFlow Lite (TFLite) for offline Android/iOS inference
- **Multilingual support** — generate explanations and recommendations in regional languages
- **Advanced evaluation** — precision, recall, F1-score, confusion matrix, per-class accuracy, classification report
- **Expanded crop support** — additional crops, diseases, and pest categories
- **Edge deployment** — quantization and pruning for resource-constrained devices

---

## ⚠️ Disclaimer

This is an **AI-assisted crop disease identification tool** and is not a substitute for professional agricultural diagnosis. Treatment recommendations should be independently verified before real-world use.

---

## 👨‍💻 Author

**Satyam Ghosh**
AI/ML Engineer — Machine Learning · Generative AI · Computer Vision · NLP · Agentic AI · MLOps

---

## ⭐ Support

If you find this project useful, consider giving the repository a ⭐ on GitHub.
