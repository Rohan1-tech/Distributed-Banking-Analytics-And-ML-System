# Distributed Banking Analytics & ML System for Customer Subscription Prediction

![Python](https://img.shields.io/badge/Python-3.10-blue?style=for-the-badge&logo=python)
![PySpark](https://img.shields.io/badge/PySpark-3.x-orange?style=for-the-badge&logo=apachespark)
![Hadoop](https://img.shields.io/badge/Hadoop-HDFS-yellow?style=for-the-badge&logo=apachehadoop)
![XGBoost](https://img.shields.io/badge/XGBoost-Best%20Model-green?style=for-the-badge)
![Sklearn](https://img.shields.io/badge/Scikit--Learn-ML-red?style=for-the-badge&logo=scikitlearn)
![License](https://img.shields.io/badge/License-MIT-purple?style=for-the-badge)

---

##  Project Overview

This project demonstrates an end-to-end **Distributed Machine Learning Pipeline** for banking analytics. Using the **bank.csv** dataset, the system predicts whether a customer will subscribe to a term deposit based on demographic, financial, and campaign interaction data.

The project integrates distributed computing technologies including **Apache Hadoop**, **Hive**, **Apache Spark**, **Spark ML**, and **Spark Streaming** to simulate how modern banks process and analyze large-scale customer data efficiently.

---

##  Problem Statement

Modern banking institutions generate massive volumes of customer and transaction data every day. Traditional single-machine systems struggle with:

- Large data volumes
- Slow processing speeds
- Inability to handle real-time data streams

This project solves these challenges using distributed machine learning and big data technologies to generate actionable insights from large-scale banking datasets.

---

##  Dataset Information

| Feature | Description |
|---|---|
| `age` | Age of the customer |
| `job` | Type of job or occupation |
| `marital` | Marital status |
| `education` | Education qualification level |
| `default` | Credit default status |
| `balance` | Average yearly account balance |
| `housing` | Housing loan status |
| `loan` | Personal loan status |
| `contact` | Communication type |
| `duration` | Last contact call duration (seconds) |
| `campaign` | Contacts during current campaign |
| `pdays` | Days since last contact from previous campaign |
| `previous` | Contacts before current campaign |
| `poutcome` | Previous campaign outcome |
| `y` | **Target** — Term deposit subscription (yes/no) |

- **Total Records:** 4521
- **Total Features:** 17
- **Target Variable:** `y` (Binary Classification)
- **Class Distribution:** 88.5% No — 11.5% Yes (Imbalanced)

---

##  Tech Stack

| Technology | Purpose |
|---|---|
| Python | Core programming language |
| Pandas & NumPy | Data manipulation and analysis |
| Matplotlib & Seaborn | Data visualization |
| Scikit-Learn | Traditional ML models |
| XGBoost | Best performing ML model |
| Apache PySpark | Distributed data processing |
| Spark ML | Distributed machine learning |
| Spark Streaming | Real-time transaction analysis |
| Hadoop HDFS (Simulated) | Distributed storage using Parquet |
| Hive (Spark SQL) | SQL-based querying layer |
| SMOTE | Class imbalance handling |
| Pickle | Model serialization and deployment |

---

##  Project Workflow

```
Bank Dataset (bank.csv)
        ↓
Hadoop HDFS Storage (Parquet Format)
        ↓
Hive Query Layer (Spark SQL)
        ↓
Apache Spark Processing
        ↓
EDA & Feature Engineering
        ↓
Spark ML Prediction Models
        ↓
Spark Streaming Analysis
        ↓
Insights & Monitoring
```

---

##  Machine Learning Models & Results

### Traditional ML Models (Scikit-Learn)

| Model | Accuracy | Precision | Recall | F1 Score | ROC AUC |
|---|---|---|---|---|---|
| Logistic Regression | 0.8652 | 0.4237 | 0.4808 | 0.4505 | 0.8353 |
| Random Forest | 0.8862 | 0.5067 | 0.3654 | 0.4246 | 0.8957 |
| Tuned Random Forest | 0.8906 | 0.5316 | 0.4038 | 0.4590 | 0.8908 |
| XGBoost | 0.8840 | 0.4945 | 0.4327 | 0.4615 | 0.9023 |
| **Tuned XGBoost ⭐** | **0.8895** | **0.5200** | **0.5000** | **0.5098** | **0.8978** |

### Spark ML Models (Distributed)

| Model | Accuracy | F1 Score | ROC AUC |
|---|---|---|---|
| Logistic Regression | 0.9033 | 0.8808 | 0.8636 |
| **Random Forest ⭐** | **0.9092** | **0.8747** | **0.8807** |
| Gradient Boosted Trees | 0.8880 | 0.8791 | 0.8814 |

---

##  Key Features

- ✅ Complete **end-to-end distributed ML pipeline**
- ✅ **Hadoop HDFS simulation** using Parquet format
- ✅ **Hive query layer** using Spark SQL with 5 analytical queries
- ✅ **Distributed feature engineering** using PySpark
- ✅ **Spark ML Pipeline** with 3 models trained and evaluated
- ✅ **Real-time Spark Streaming** simulation for fraud detection
- ✅ **Class imbalance handling** using SMOTE
- ✅ **Hyperparameter tuning** with GridSearchCV and RandomizedSearchCV
- ✅ **Model deployment** using Pickle
- ✅ **13+ EDA visualizations** with business insights
- ✅ **Hypothesis testing** using T-Test and Chi-Square

---

## 📁 Repository Structure

```
📁 Distributed-Banking-Analytics-ML-System
├──  Distributed_Banking_Analytics_&_ML_System.ipynb
├──  bank .csv
├──  tuned_xgboost_model.pkl
└──  README.md
```

---

##  Real-Time Streaming Results

| Risk Category | Transactions |
|---|---|
| Medium Risk  | 47 |
| Normal  | 42 |
| Suspicious  | 11 |

- **81%** of streamed customers showed high subscription potential
- **11** suspicious transactions detected in real time

---

##  Key Insights

- **Call Duration** is the strongest predictor of term deposit subscription
- **Account Balance** and **Age** significantly influence subscription behavior
- **Previous Campaign Success** is a strong predictor of current subscription
- Customers with **longer calls and higher balances** are most likely to subscribe
- **Students and Retired** customers show the highest subscription rates

---

##  How to Run

### 1. Clone the Repository
```bash
git clone https://github.com/your-username/Distributed-Banking-Analytics-ML-System.git
cd Distributed-Banking-Analytics-ML-System
```

### 2. Install Dependencies
```bash
pip install pandas numpy matplotlib seaborn scikit-learn xgboost pyspark findspark imbalanced-learn
```

### 3. Open in Google Colab
- Upload `Distributed_Banking_Analytics_&_ML_System.ipynb` to Google Colab
- Upload `bank .csv` to Google Drive
- Run all cells in order

### 4. Load Saved Model
```python
import pickle

with open('tuned_xgboost_model.pkl', 'rb') as f:
    model = pickle.load(f)

prediction = model.predict(your_data)
```

---

##  Future Improvements

- Deploy model using **Flask or FastAPI** as REST API
- Integrate **Apache Kafka** for production-grade streaming
- Deploy on **AWS or Google Cloud** for scalable production use
- Implement advanced **fraud detection algorithms**
- Build **real-time dashboard** using Streamlit or Grafana
- Continuously retrain model with new campaign data

---

##  Author

**Rohan** — Individual Project

