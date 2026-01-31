# 📊 Comparison of Tree, Forest, Linear Models vs Gradient Boosting for Car Price Prediction
## 📌 Project Overview

Rusty Bargain, a used-car sales service, aims to build an application that estimates the market value of vehicles based on historical data such as technical specifications, equipment versions, and past prices.
The objective of this project is to compare different machine learning models focusing on:

* Prediction quality (RMSE)
* Training time
* Prediction speed

---
## 🧠 Models Evaluated

The following models were trained and evaluated:
* Linear Regression (baseline linear model)
* Decision Tree Regressor
* Random Forest Regressor
* LightGBM Regressor (Gradient Boosting)
* CatBoost Regressor (Gradient Boosting)

---
## ⚙️ Data Preparation

* Key preprocessing steps included:
* Replacing missing categorical values with "unknown"
* Removing unrealistic values in:
  * Power (0 or >1000)
  * RegistrationYear (<1900 or >2024)
  * Price (≤100)
* Treating RegistrationMonth as a categorical variable
* Dropping non-informative features (NumberOfPictures, dates, postal code)
* One-hot encoding categorical features for tree-based and linear models
* Native categorical handling for LightGBM and CatBoost

---
## 📈 Results Summary
| Model                | RMSE   | Training Time |
|---------------------|--------|---------------|
| Baseline (Mean)      | ~4593  | —             |
| Linear Regression    | ~2638  | ~5s           |
| Decision Tree        | ~2482  | ~2s           |
| Random Forest        | ~2424  | ~69s          |
| CatBoost             | ~1623  | ~76s          |
| LightGBM             | ~1561  | ~2s           |


---
## 🏆 Conclusions

* **Gradient boosting models significantly outperform traditional models.**
* **LightGBM achieved the best balance between accuracy and speed.**
* Random Forest performed well but required substantially more training time.
* Linear regression served as a useful sanity check but lacked predictive power.

**📌 LightGBM is recommended for deployment due to its superior performance and efficiency**.

---
## 🚀 Future Improvements

* Hyperparameter tuning with cross-validation
* Feature engineering (vehicle age, mileage per year)
* Model explainability (feature importance, SHAP values)
