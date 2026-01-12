# 📊 PCA Analysis on Breast Cancer Dataset

## 📌 Dataset Overview
We used the Breast Cancer Wisconsin Dataset which contains:
- Total Samples: 569
- Original Features: 30
- Target Shape: (569,)

এই dataset টি binary classification problem এর জন্য ব্যবহৃত হয়
(Benign vs Malignant tumor classification)।

---

## 📈 Descriptive Statistics (Before PCA)
প্রথমে dataset এর basic statistical properties analyze করা হয়েছে:

For each feature we calculated:
- Mean
- Standard Deviation (std)
- Minimum value
- Maximum value

Example features include:
- mean radius
- mean texture
- mean perimeter
- mean area
- mean smoothness
- mean compactness
- mean concavity
- mean concave points
- mean symmetry
- mean fractal dimension

👉 Observation:
Features গুলোর scale ভিন্ন হওয়ায় PCA করার আগে data standardization অত্যন্ত গুরুত্বপূর্ণ ছিল।

---

## 🔄 Principal Component Analysis (PCA)

### ▶ Explained Variance Ratio
PCA করার পর প্রথম 10টি Principal Component নেওয়া হয়েছে।

Explained Variance Ratio:
PC1  = 44.27%  
PC2  = 18.97%  
PC3  =  9.39%  
PC4  =  6.60%  
PC5  =  5.49%  
PC6  =  4.02%  
PC7  =  2.25%  
PC8  =  1.59%  
PC9  =  1.39%  
PC10 =  1.16%

👉 PC1 একাই প্রায় অর্ধেক information explain করে।

---

### ▶ Cumulative Explained Variance
Cumulative variance after components:
- First 2 PCs  → ~63%
- First 5 PCs  → ~85%
- First 10 PCs → ~95%

👉 Only 10 components দিয়েই dataset এর 95% information retain করা সম্ভব হয়েছে,
যা dimensionality reduction এর জন্য খুব effective।

---

## 🧮 PCA Transformed Data
After PCA:
- New Feature Shape: (569, 10)

Each Principal Component হলো original features এর weighted combination।

Example:
- PC1 heavily influenced by:
  mean radius, mean perimeter, mean area,
  mean concavity, mean concave points

- PC2 বেশি influenced by:
  mean texture, mean symmetry, mean fractal dimension

👉 This shows PCA successfully captured correlation among features।

---

## 🤖 Model Performance Comparison

### 🔹 Without PCA
Accuracy: **98.60%**

### 🔹 With PCA (10 Components)
Accuracy: **97.90%**

---

## 📌 Final Observation
- PCA করার পর accuracy সামান্য কমেছে
- কিন্তু feature সংখ্যা 30 → 10 এ নেমে এসেছে
- Model এখন:
  ✔ Faster  
  ✔ Less complex  
  ✔ Less prone to overfitting  

👉 Conclusion:
PCA is very effective when we want a balance between
**high performance** and **low dimensionality**.

---

## ✅ Conclusion (In Short)
- PCA successfully reduced dimensions
- Most variance captured by first few components
- Classification performance remains almost the same
- PCA is suitable for real-world ML pipelines

✨ This analysis proves PCA is a powerful feature reduction technique.
