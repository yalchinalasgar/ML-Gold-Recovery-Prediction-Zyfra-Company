# 🟡 Gold Recovery Prediction using Machine Learning

## 📌 Project Overview
This project focuses on building a **machine learning regression model** to predict gold recovery from mining process data. The main objective is to optimize prediction accuracy using the **Final SMAPE (Symmetric Mean Absolute Percentage Error)** metric.

The project covers the full data science pipeline — from preprocessing and exploratory analysis to model selection, tuning, and evaluation.

---

## ⚙️ Data Preprocessing
- Converted `date` column from **object → datetime**
- Handled missing values using a custom **`ffill_drop` function** (forward fill grouped by date)
- Ensured **train-test consistency**:
  - Added missing **target columns** to test set
  - Kept only **common features** between train and test sets
- **Validated recovery calculation** to ensure correctness of target values

---

## 📊 Exploratory Data Analysis (EDA)
- Analyzed **metal concentration changes** (`Au`, `Ag`, `Pb`) across purification stages
- Compared **feed particle size distributions** between train and test datasets
- Examined **feature distributions** to detect anomalies
- Identified ~600 rows with **near-zero total metal concentration**
  - Treated as anomalies and **removed from dataset**

---

## 🧠 Feature Engineering
- Applied **Standard Scaling** to normalize feature distributions
- Created custom evaluation metrics:
  - `SMAPE`
  - `Final SMAPE` (primary metric)

---

## 🤖 Models Used
The following regression models were evaluated:

- Decision Tree Regressor  
- Random Forest Regressor  
- Linear Regression  
- XGBoost Regressor  

---

## 🔧 Model Tuning
- Applied **GridSearchCV** for hyperparameter optimization  
- Used **RandomizedSearchCV** for further tuning  
- Models were compared using **Final SMAPE (lower is better)**  

---

## 🏆 Best Model
**XGBoost Regressor** achieved the best performance.

### 📈 Results:
- **Test Set Final SMAPE:** `5.90`
- **Baseline (DummyRegressor):** `~9.20`
- ✅ **Performance Improvement:** ~**36% better than baseline**

---

## 💡 Key Insights
- Tree-based and boosting models outperform linear models → data has **non-linear relationships**
- Removing anomalies significantly improved model reliability
- Moderate improvement over baseline suggests:
  - 📌 **Feature engineering is the key next step**
  - Model complexity alone has limited impact

---

## 🚀 Future Improvements
- Advanced **feature engineering**
- Domain-specific feature creation
- Time-series based modeling (if applicable)
- Ensemble techniques for further optimization

---

## 🛠️ Tech Stack
- Python (Pandas, NumPy)
- Scikit-learn
- XGBoost
- Matplotlib / Seaborn

---

## 👤 Author
**Yalchin Alasgarli**
- LinkedIn: https://www.linkedin.com/in/yalchin-alasgarli/

- Aspiring Data Scientist  
- Background in GIS & Analytics  
- Passionate about solving real-world problems with data  

---

## ⭐ If you found this project useful, feel free to star the repo!
