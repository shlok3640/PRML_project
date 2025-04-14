# PRML PROJECT

# 🖊️ Hand-drawn Sketch Recognition  
### CSL2050: Pattern Recognition and Machine Learning  
**Indian Institute of Technology Jodhpur**

## 📌 Project Overview

This project explores traditional and hybrid machine learning approaches for classifying human-drawn object sketches. The main objective is to determine the most effective techniques in terms of **accuracy**, **efficiency**, and **robustness**, particularly in low-data and low-resource scenarios.

---

## 📄 Abstract

Humans have sketched to express visual understanding for millennia. This project investigates recognition of such sketches using computational methods. We evaluated models based on KNN, Random Forests, and hybrid combinations with CNN features (e.g., CNN+KNN, CNN+XGBoost). Our experiments demonstrate that **hybrid methods consistently outperform standalone approaches**, achieving **up to 44.7% accuracy**.

---

## 🧪 Dataset & Setup

### ✏️ TU-Berlin Sketch Dataset
- **20,000** human-drawn sketches across **250 categories**
- Crowdsourced from non-experts sketching objects like *car*, *teapot*, etc.
- **Human classification accuracy**: 73%
- **Model baseline**: 56% (BoF + SVM), chance: 0.4%

### ✅ Our Preprocessing
- Resized to **128×128** while preserving aspect ratio  
- Pixel values normalized to **[0, 1]**  
- Stratified train-test split: **80% training**, **20% testing**

---

## 🛠️ Methods Used

### 🔹 Traditional ML
- **KNN + HOG**
  - HOG: 8×8 cells, 16×16 block normalization
  - Accuracy: **26.5%**
- **Random Forest**
  - Features: Color histograms, LBP, Haralick textures, Hu moments
  - Accuracy: **39.17%**

### 🔹 Hybrid Approaches
- **CNN + Naive Bayes**
  - Features: ResNet50 embeddings (discretized)
  - Accuracy: **37.0%**

- **CNN + XGBoost**
  - ResNet50 features → Standardized → XGBoost (200 est., depth 6, lr 0.1)
  - Accuracy: **44.5%**

- **CNN + KNN**
  - ResNet50 features → Reduced to 50D → KNN (k=7, cosine distance)
  - Accuracy: **🟢 44.7% (Best)**

---

## 📊 Results Summary

| Method          | Accuracy | Precision | Recall | F1-Score | Top-5 Accuracy |
|-----------------|----------|-----------|--------|----------|----------------|
| KNN + HOG       | 26.5%    | 28.3%     | 25.7%  | 26.9%    | 48.2%          |
| Random Forest   | 39.17%   | 40.2%     | 38.6%  | 39.4%    | 63.5%          |
| CNN + Naive Bayes | 37.0%  | 38.4%     | 36.2%  | 37.3%    | 65.8%          |
| CNN + XGBoost   | 44.5%    | 45.8%     | 43.9%  | 44.8%    | 72.3%          |
| CNN + KNN       | 🟢 **44.7%** | **46.2%** | **44.1%** | **45.1%** | **73.9%**      |

---

## ⚙️ Computational Metrics

| Method          | Model Size | Training Time | Inference Time (ms/image) |
|-----------------|------------|----------------|----------------------------|
| KNN + HOG       | 42.5 MB    | 8.3 min        | 12.6 ms                    |
| Random Forest   | 185.6 MB   | 16.7 min       | 8.2 ms                     |
| CNN + Naive Bayes | 58.3 MB  | 83.5 min       | **6.4 ms**                 |
| CNN + XGBoost   | 87.4 MB    | 92.1 min       | 7.8 ms                     |
| CNN + KNN       | 52.7 MB    | 85.3 min       | 🔴 15.2 ms                 |

---

## 🧠 Insights & Observations

- **Hybrid models** (CNN + classical ML) outperform traditional or pure deep models.
- **Random Forest** offers a strong classical benchmark using handcrafted features.
- **CNN+KNN** shines in texture-rich categories (e.g., fabrics, plants).
- **CNN+XGBoost** performs well in shape-centric classes (e.g., vehicles, electronics).

### ⚠️ Error Analysis
- Visual similarity (e.g., sedan vs. coupe) leads to confusion.
- Underrepresented classes (<50 samples) suffer most.
- Complex backgrounds sometimes distract CNN attention.
- Occlusion and varied scales cause drops in performance.

---

## 📁 Repository Structure

- `Project_Report/` – PDF report with results and analysis
- `PRML_project_SVM.ipynb` – Traditional SVM experiments
- `PRML_project_knn.ipynb` – KNN model experiments
- `demo_PRML_Project_knn+CNN.ipynb` – Hybrid demos

---

## 👨‍💻 Contributors

- **Sonic Vyas** – b23cs1100@iitj.ac.in  
- **Yash Kumar Singh** – b23cs1102@iitj.ac.in  
- **Shardul Vikram Singh** – b23cs1067@iitj.ac.in  
- **Sarthak Bhiwaji Kolekar** – b23cs1065@iitj.ac.in  
- **Shlok Kanani** – b23cs1068@iitj.ac.in  

Affiliation: *Indian Institute of Technology Jodhpur*

---

## 🚀 Future Work

- Incorporate **transformer-based models** and **self-supervised learning**
- Explore **multi-modal sketch + text fusion**
- Improve performance on **low-data categories**
- Evaluate generalization on **real-world sketch input (mobile/stylus)**

---

## 📜 License

Available for academic and research use.
