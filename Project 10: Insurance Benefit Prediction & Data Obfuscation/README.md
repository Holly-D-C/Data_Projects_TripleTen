# Project 10 - Insurance Benefit Prediction & Data Obfuscation
---

## 🎯 Objective

Evaluate whether machine learning can be used at *Sure Tomorrow Insurance* to:

1. Identify similar customers for marketing purposes
2. Predict whether a customer will receive insurance benefits
3. Predict the *number* of benefits a customer will receive
4. Protect sensitive customer data **without degrading model performance**

---

### 🧠 Models & Methods

* **k‑Nearest Neighbors (kNN)** — classification
* **Linear Regression** — benefit count prediction
* **Matrix‑based Data Obfuscation** — privacy protection

---

### 🧪 Key Results

#### kNN Classification (Benefit Receipt)

* **F1‑score improvement:** **4.7×** over dummy baseline
* Demonstrated that **feature scaling is essential** for distance‑based models
* Unscaled models failed due to income dominating distance calculations

#### Linear Regression (Benefit Count)

* **RMSE:** 0.34
* **R²:** 0.66
* Confirmed **scale invariance** of linear regression

#### Data Obfuscation

* Implemented feature transformation: `X' = X × P` (invertible matrix)
* **Model performance unchanged** after obfuscation
* Guaranteed privacy while maintaining identical predictions

---

### 📊 Summary Table

| Task                   | Model             | Key Metric | Result               |
| ---------------------- | ----------------- | ---------- | -------------------- |
| Benefit Classification | kNN (scaled)      | F1         | **0.94**             |
| Benefit Count          | Linear Regression | RMSE       | **0.34**             |
| Obfuscated Regression  | Linear Regression | RMSE       | **0.35 (identical)** |

---

### 🛠 Tech Stack

* Python, pandas, NumPy
* scikit‑learn
* Mathematical validation of model invariance

---

## Project Link

📂 **Notebook:** [Project 10: Insurance Benefit Prediction & Data Obfuscation](https://holly-d-c.github.io/my-portfolio/Project_11/Project_11_Linear%20Algebra.html)
