# What Drives the Price of a Car?

## 📌 Project Overview

This project explores the key factors that influence used car prices. Using a dataset of car listings, we cleaned, visualized, and modeled the data to understand which features best explain variation in car prices.
Our ultimate goal is to provide actionable insights into what drives car value and to build a predictive model that estimates car prices.

---

## 🗂️ Project Organization

* **`README.md`** → Project summary (this file)
* **`used_car_analysis.ipynb`** → Main Jupyter notebook with full analysis
* **`images/`** → Folder containing saved visualizations
* **`models/`** → Saved trained model pipelines (`.pkl`) for deployment

---

## 🛠️ Methods and Workflow

1. **Data Cleaning & Preparation**

   * Handled missing values with median (numeric) and most-frequent (categorical) imputation
   * Scaled numeric features and encoded categorical variables using one-hot encoding
   * Removed outliers in price and mileage for better model stability

2. **Exploratory Data Analysis (EDA)**

   * Distribution plots of prices and odometer readings
   * Boxplots and violin plots for categorical drivers (e.g., brand, condition, fuel type)
   * Hexbin density plots to visualize nonlinear relationships (price vs. mileage)

3. **Modeling**

   * Trained and compared **three regression models**:

     * Linear Regression (baseline)
     * Random Forest Regressor
     * HistGradientBoosting Regressor
   * Used **RMSE (Root Mean Squared Error)** and **R² (coefficient of determination)** as evaluation metrics
   * Hyperparameter tuning and cross-validation performed for Random Forest

4. **Deployment**

   * Built a **deployment-ready pipeline** with preprocessing + best model wrapped in `Pipeline`
   * Saved trained pipeline using `joblib` for future predictions
   * Example function provided: `predict_price(new_data)`

---

## 📊 Key Findings

* **Linear Regression** performed poorly (RMSE ≈ 11,720, R² ≈ 0.39), showing that simple linear models struggle with nonlinear car price patterns.
* **Random Forest Regressor** improved performance (RMSE ≈ 8,227, R² ≈ 0.70), capturing more complex relationships.
* **HistGradientBoosting Regressor** was the **best model** (RMSE ≈ 7,546, R² ≈ 0.75), balancing accuracy and efficiency.

👉 **Most influential factors:**

* **Odometer reading** (negative impact on price)
* **Car brand / manufacturer**
* **Year of manufacture**
* **Fuel type and condition**

---

## 📈 Example Visualizations

* Price distribution and skewness correction
* Price vs. odometer hexbin density plots
* Bar charts of top 10 feature importances from Random Forest and HGB
* Model comparison chart (RMSE vs. R² across models)

---

## 🧾 Business Insights

* **Mileage strongly decreases car value** — customers and dealers should weigh this heavily in pricing strategies.
* **Brand reputation matters** — premium brands retain higher value even at higher mileage.
* **Fuel type and condition** affect resale — electric and hybrid cars show stronger retention, while poor condition leads to sharp price drops.
* **Recommendations:**

  * Sellers should highlight condition and fuel efficiency in listings.
  * Buyers should consider high-value brands with slightly higher mileage for better value.
  * Dealerships could use the model to set **fair, data-driven price ranges**.

---

## 🚀 Next Steps

* Incorporate more external factors (e.g., regional demand, economic indicators).
* Perform deeper hyperparameter tuning on HGB for even better accuracy.
* Deploy as a simple **Flask/FastAPI web app** for interactive predictions.

---

## 📌 Notebook Link

👉 [Jupyter Notebook: used_car_analysis.ipynb](./used_car_analysis.ipynb)

