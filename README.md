# 📊 Data Mining for Personalized Online Learning

*Market Basket Analysis • Recommender Systems • Anomaly Detection • Time Series Forecasting*

This project explores **student behavior**, **dropout patterns**, and **course recommendation strategies** using a combination of **data mining techniques**. It was developed as part of an advanced **Data Mining & Analytics course project**, using a synthetic 10,000-student personalized learning dataset.

---

## 📌 Project Objectives

This project applies four major data mining techniques to understand and improve online learning platforms:

1. **Market Basket Analysis (MBA)**
2. **Recommender Systems (Content-Based + Collaborative Filtering)**
3. **Anomaly Detection**
4. **Time Series Forecasting**

Each technique is implemented in a separate notebook.

---

## 📁 Repository Structure

```
├── assets/                          # plots, charts, saved screenshots
├── personalized_learning_dataset.csv
├── MBA.ipynb                        # Market Basket Analysis
├── Recommender_syatem.ipynb         # Recommender Systems
├── Anomaly_Detection.ipynb          # Anomaly Detection
├── Time_Series_&_Forecasting.ipynb  # Time Series + Forecasting Models
└── README.md
```

---

# 📘 Notebooks Overview

## 1️⃣ Market Basket Analysis (MBA)

**Goal:** Discover associations between student engagement patterns and dropout likelihood.

### ✔ Main Steps

* Converted numerical performance features into categorical bins (Low/Medium/High)
* Built a one-hot encoded basket of 32 binary features
* Generated frequent itemsets using **Apriori** (min_support = 0.05)
* Extracted **407 high-confidence association rules** (min_confidence = 0.6)
* Ranked rules by **Lift** to highlight the strongest relationships

### ✔ Key Insights

* Strong relationships between **low engagement** and **dropout likelihood**
* High performance metrics tend to co-occur
* Learning styles correlate with engagement behaviors

---

## 2️⃣ Recommender System

**Goal:** Recommend suitable courses for students based on behavior, performance, and similarity patterns.

### ✔ Methods Used

### **A. Content-Based Filtering**

Uses student attributes → Creates student vectors → Computes cosine similarity → Suggests similar courses

### **B. Collaborative Filtering**

User-user similarity → Finds nearest neighbors → Recommends courses not yet taken

### ✔ Evaluation

* Compared recommendations for sample students
* Plotted CBF vs CF scores
* Average Top-N Scores:

  * **Content-Based:** 0.72
  * **Collaborative:** 9.49

### ✔ Insight

Both methods produced consistent, meaningful course suggestions.

---

## 3️⃣ Anomaly Detection

**Goal:** Detect abnormal student behavior (cheating, sudden performance drop, misreported engagement).

### ✔ Models Applied

* **Isolation Forest (contamination=0.05)** → 500 anomalies
* **Local Outlier Factor (LOF, contamination=0.05)** → 500 anomalies
* **DBSCAN (eps=1.5)** → 379 anomalies

### ✔ Visualization

* PCA (2D) projection
* Scatter plots for each algorithm showing anomaly vs normal

---

## 4️⃣ Time Series & Forecasting

**Goal:** Predict student performance trends over time.

### ✔ Workflow

* Created synthetic **weekly time series** from exam scores
* Engineered lag features + rolling windows
* Trained:

  * Baseline (Lag-1)
  * Random Forest
  * Gradient Boosting
  * LSTM
  * AutoARIMA

### ✔ Results (MSE | MAE)

* Baseline: **4.19 | 1.63**
* Random Forest: **2.87 | 1.44**
* Gradient Boosting: **2.39 | 1.29** ← *Best*
* LSTM: **5.73 | 1.99**
* AutoARIMA: **4.05 | 1.53**

### ✔ Key Insight

Gradient Boosting outperformed all models.

---

# 📊 Summary of Findings

| Task                    | Best Technique          | Key Outcome                            |
| ----------------------- | ----------------------- | -------------------------------------- |
| Market Basket Analysis  | Apriori                 | 407 strong association rules           |
| Recommender System      | Collaborative Filtering | Strong, diverse course recommendations |
| Anomaly Detection       | Isolation Forest / LOF  | Consistent detection of rare behavior  |
| Time Series Forecasting | Gradient Boosting       | Lowest prediction error                |

This project demonstrates diverse analytical techniques relevant to **EdTech**, **student performance prediction**, and **personalized learning systems**.

---

# 🛠 Tech Stack

* Python, Pandas, NumPy
* Scikit-Learn, XGBoost, TensorFlow/Keras
* MLxtend (Apriori & Rules)
* Statsmodels (ARIMA)
* Matplotlib, Seaborn, Plotly

---
