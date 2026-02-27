# 🫁 Tuberculosis Detection & Management System  
### Explainable Ensemble Learning with EfficientNet-B7

---

## 📌 Business / Healthcare Problem

Tuberculosis (TB) remains one of the leading infectious causes of death worldwide, particularly in low-resource regions where access to trained radiologists and diagnostic infrastructure is limited.

### Key Challenges

- Manual chest X-ray interpretation requires experienced radiologists  
- Diagnostic variability due to fatigue and subjectivity  
- Lack of scalable and real-time diagnostic systems  
- Limited interpretability of AI-based medical models  

### This Project Addresses

- Can we build an accurate and explainable AI model for TB detection?  
- Can we improve trust in AI diagnostics using visual explanations?  
- Can this system be deployed in scalable cloud environments for real-time use?  

---

## 🏗️ System Architecture Overview

The system follows a modular pipeline:
<img width="1139" height="620" alt="image" src="https://github.com/user-attachments/assets/edc6ca0f-af13-4a12-94d3-16a5d666f0a3" />

Data Collection  
→ Data Preprocessing  
→ Deep Learning Training (EfficientNet-B7)  
→ Disease Detection  
→ Explainability (Grad-CAM)  
→ Feature Aggregation (Gradient Boosting)  
→ Personalized Recommendation  
→ Final Output  

---

## 🔬 Methodology

### 1️⃣ Data Collection

**Dataset:** Shenzhen Chest X-ray Dataset  

Binary classification task:
- TB-Positive  
- TB-Negative  

---

### 2️⃣ Data Preprocessing

To improve model generalization and robustness:

- Converted images to grayscale  
- Applied CLAHE (Contrast Limited Adaptive Histogram Equalization)  
- Resized images to **224 × 224**  
- Pixel normalization  
- Data augmentation:
  - Rotation  
  - Horizontal flipping  
  - Zooming  
  - Width & height shifts  

This reduces noise, enhances contrast, and simulates real-world variability.

---

### 3️⃣ Model Architecture

**Base Model:** EfficientNet-B7 (Transfer Learning)

- Pretrained on ImageNet  
- Fine-tuned for TB binary classification  
- Internal activation: **Swish**  
- Output activation: **Sigmoid**  
- Loss Function: **Binary Cross-Entropy**  
- Optimizer: **Adam**  

EfficientNet-B7 extracts high-level semantic features from chest X-rays while maintaining computational efficiency.

---

### 4️⃣ Ensemble Learning

To improve classification robustness:

- Deep features extracted from EfficientNet-B7  
- Combined with metadata (age, gender if applicable)  
- Gradient Boosting Classifier used as a meta-model  

### Improvements Achieved

- Better generalization  
- Increased robustness  
- Reduced false positives  
- Improved classification stability  

---

### 5️⃣ Explainability Module

To avoid black-box behavior, the system integrates **Grad-CAM**.

- Applied to final convolutional layers  
- Generates heatmaps highlighting:
  - Pulmonary opacities  
  - Cavitations  
  - Nodular lesions  

This ensures clinical interpretability and builds trust in AI predictions.

---

## 🛠️ Skills & Technologies Used

### Deep Learning
- TensorFlow  
- Keras  
- EfficientNet-B7  

### Machine Learning
- Gradient Boosting  
- Scikit-learn  

### Image Processing
- OpenCV  
- CLAHE  

### Explainable AI
- Grad-CAM  

### Deployment Concepts
- AWS Lambda / Serverless Architecture  
- Cloud-based inference  

---

## 📊 Results & Performance

The model was evaluated using:

- Accuracy  
- Precision  
- Recall (Sensitivity)  
- F1-Score  
- AUC-ROC  
- Confusion Matrix  

### Key Observations

- The ensemble approach improved classification reliability  
- Maintained strong interpretability  
- Grad-CAM visualizations confirmed focus on clinically relevant lung regions  

---

## 🚀 Key Contributions

✔ EfficientNet-B7 based TB detection system  
✔ Explainable AI integration using Grad-CAM  
✔ Ensemble learning for improved robustness  
✔ Real-time scalable deployment architecture  
✔ Personalized recommendation module  

---

## 🏥 Business / Clinical Impact

- Supports early TB screening  
- Reduces dependency on expert radiologists  
- Enables AI-assisted diagnosis in rural areas  
- Improves trust through visual explanations  
- Scalable for telemedicine environments  

---

## 🔮 Future Enhancements

- Multi-disease detection (Pneumonia, COVID-19, Lung Cancer)  
- Drug-resistance prediction (MDR-TB)  
- Integration with Electronic Health Records (EHR)  
- Mobile/offline inference support  
- AutoML-based continuous learning  

---

## 📌 Conclusion

This project demonstrates the integration of deep learning, explainable AI, and ensemble learning into a scalable tuberculosis detection system. By combining diagnostic accuracy with interpretability and cloud deployment capabilities, the system offers a practical AI-assisted solution for real-world healthcare environments.
