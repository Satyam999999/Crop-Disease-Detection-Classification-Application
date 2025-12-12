🌿 AI Crop Disease Detection Application

An end-to-end deep learning application that identifies 22 different types of crop diseases and pests from leaf images. It combines a fine-tuned Convolutional Neural Network (CNN) for visual classification with Google's Gemini AI to provide actionable agricultural advice.

📌 Project Overview

This project addresses the critical challenge of early crop disease diagnosis. By leveraging transfer learning with state-of-the-art architectures, the system achieves high accuracy in classifying diseases across Cashew, Cassava, Maize, and Tomato plants. The solution is deployed as a user-friendly Streamlit web application that not only identifies the issue but also suggests treatments and preventative measures using Generative AI.

✨ Features

Multi-Class Classification: Accurately identifies 22 distinct crop diseases and healthy states.

AI-Powered Insights: Integrates Google Gemini 1.5 Flash to generate real-time summaries, treatment options, and prevention tips for the detected disease.

Automatic Model Retrieval: The application automatically downloads the trained model weights from a secure external source upon the first run, bypassing GitHub's file size limits.

Robust Data Pipeline: Built on a rigorous training pipeline that handles data cleaning, augmentation, and validation to ensure model reliability.

Interactive UI: A clean, responsive interface built with Streamlit.


🛠️ Technologies Used

Frontend: Streamlit

Deep Learning: TensorFlow/Keras

Model Architecture: ResNet50 (Fine-tuned) / DenseNet121

Generative AI: Google Gemini API

Image Processing: Pillow (PIL), NumPy

Training Environment: Google Colab (GPU)

⚙️ How to Run Locally

Follow these steps to set up the project on your local machine.

1. Clone the Repository

git clone https://github.com/Satyam999999/Crop-Disease-Detection-Classification-Application
cd your-repo-name


2. Install Dependencies

Ensure you have Python 3.8+ installed. Then run:

pip install -r requirements.txt


3. Set Up API Credentials

You need a Google Gemini API Key to enable the AI advice feature.

Option A (Environment Variable - Recommended):

Linux/Mac: export GEMINI_API_KEY="your_actual_api_key"

Windows (PowerShell): $env:GEMINI_API_KEY="your_actual_api_key"

Option B (Secrets):

Create a folder .streamlit in the project root.

Create a file .streamlit/secrets.toml.

Add the line: GEMINI_API_KEY = "your_actual_api_key"

4. Run the Application

streamlit run app.py


Note: On the first run, the app will automatically download the trained model file (~100MB). This may take a few moments depending on your internet connection.

🔬 Model Development

The model was developed using a systematic approach:

Data Cleaning: Implemented a robust pipeline using TensorFlow decoding to remove corrupted images from the 1.35GB Kaggle dataset.

Architecture Search: Evaluated ANN, Custom CNN, VGG16, ResNet50, EfficientNetB3, and DenseNet121.

Optimization: The final model uses Transfer Learning with a two-stage fine-tuning process, data augmentation, L2 regularization, and Dropout to prevent overfitting.

Performance: Achieved a test accuracy of 85.62% on the unseen test set.

💡 Future Improvements

Object Detection: Implement YOLOv8 to localize the specific infected areas on a leaf.

Mobile Deployment: Convert the model to TensorFlow Lite (TFLite) for an offline Android/iOS mobile app.

Multilingual Support: Use Gemini to translate the advice into local languages for broader accessibility by farmers.
