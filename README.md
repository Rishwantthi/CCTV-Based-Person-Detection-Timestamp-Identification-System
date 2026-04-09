# 🎯 Automated Face Recognition & CCTV Tracking System

## 📌 Overview

This project implements an AI-based system to automatically identify and track a specific individual in CCTV footage using a custom-trained deep learning model.

The system eliminates the need for manual video analysis by:

* Detecting faces from frames
* Recognizing a target person using embeddings
* Tracking their presence over time
* Generating entry time, exit time, and duration

---

## 🚀 Features

* 🔍 Face recognition using custom-trained MobileNetV2 model
* 📐 Embedding-based similarity comparison
* ⚙️ Adaptive threshold (data-driven + safety margin)
* 🎯 Multi-frame verification for robustness
* ⏱️ Entry and exit time detection
* 📊 Duration calculation
* 🧠 Lightweight and efficient pipeline

---

## 🧠 Methodology

### 1. Data Preparation

* Dataset organized in person-wise folders
* Images resized to 160×160 and normalized

### 2. Model Training

* Base model: MobileNetV2 (pretrained on ImageNet)
* Custom dense layers added
* Trained for classification

### 3. Feature Extraction

* Convert face images → 128-dimensional embeddings
* Apply L2 normalization for stable comparison

### 4. Similarity Matching

* Euclidean distance between embeddings
* Adaptive threshold:

```
threshold = (avg_same + avg_diff) / 2 - margin
```

### 5. Tracking Logic

* Frame-by-frame comparison
* Multi-frame confirmation (reduces false detection)
* Entry and exit detection

### 6. Output

* Entry time
* Exit time
* Duration

---

## 🏗️ Architecture

CCTV Video
→ Frame Extraction
→ Face Detection
→ Face Cropping
→ Data Cleaning & Duplicate Filtering
→ Feature Extraction
→ Embedding Generation
→ Similarity Matching
→ Multi-frame Verification
→ Entry & Exit Detection
→ Time Calculation

---

## 🛠️ Tech Stack

* Python
* TensorFlow / Keras
* OpenCV
* NumPy
* Scikit-learn

---

## ▶️ How to Run

1. Open the notebook in Google Colab
2. Upload dataset zip when prompted
3. Run all cells sequentially
4. The system will:

   * Train the model
   * Compute threshold
   * Simulate video tracking
   * Output entry, exit, duration

---

## 📊 Results

* Same person accuracy: ~80%
* Different person accuracy: ~100%
* Zero false positives (critical for surveillance systems)

---

## 💡 Key Innovations

* ✅ Adaptive threshold (data-driven)
* ✅ Safety margin to reduce false positives
* ✅ Multi-frame verification strategy
* ✅ End-to-end automated pipeline

---

## 🎤 Explanation (Interview Ready)

**Problem:**
Manual CCTV analysis is time-consuming and inefficient.

**Solution:**
We convert faces into embeddings using a MobileNet-based model and compare them using Euclidean distance with an adaptive threshold. Multi-frame verification ensures robust detection and minimizes false positives.

---

## 🔮 Future Improvements

* Real-time video integration
* Advanced face detection (MTCNN / RetinaFace)
* Deployment as web application
* Larger dataset for better generalization

---

## 👨‍💻 Author

Developed as part of a mini project focusing on AI, Computer Vision, and real-world system design.

---

## ⭐ Project Highlights

* End-to-end ML pipeline
* Real-world application (surveillance)
* Strong focus on robustness and accuracy
* Designed for practical deployment

---

🔥 *This project demonstrates both deep learning knowledge and system-level thinking — ideal for placements and interviews.*
