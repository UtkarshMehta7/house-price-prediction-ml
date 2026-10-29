# 🏠 House Price Prediction using Machine Learning

Predictive Analytics project — predicting median house prices of California districts using 5 different regression models and comparing their performance.

## 📌 About the Project

The aim of this project is to predict `median_house_value` of a housing block using features like median income, location, number of rooms, population, ocean proximity etc.

Complete workflow followed:
1. **Data Cleaning** – handling missing values, duplicates, capped values and outliers
2. **Exploratory Data Analysis (EDA)** – distributions, correlation heatmap, geographical plot, boxplots
3. **Feature Engineering** – rooms per household, bedrooms per room, population per household + one hot encoding
4. **Model Building** – 5 regression models
5. **Model Evaluation** – R² Score, MSE, RMSE, MAE + 5-fold Cross Validation

## 📊 Dataset

- **Name:** California Housing Prices (1990 Census)
- **Rows:** 20,640 | **Columns:** 10
- **Source:** Publicly available — [Kaggle](https://www.kaggle.com/datasets/camnugent/california-housing-prices) / StatLib repository
- After cleaning: 19,277 rows used for modelling

| Column | Description |
|---|---|
| longitude, latitude | Location of the block |
| housing_median_age | Median age of houses |
| total_rooms, total_bedrooms | Total rooms / bedrooms in block |
| population, households | People and households in block |
| median_income | Median income (in tens of thousands $) |
| ocean_proximity | Distance category from ocean |
| **median_house_value** | **Target variable** |

## 🤖 Models Used

1. Linear Regression
2. Ridge Regression
3. Decision Tree Regressor
4. Random Forest Regressor
5. XGBoost Regressor

## 📈 Results

| Rank | Model | R² Score (Accuracy) | MSE | RMSE | MAE |
|---|---|---|---|---|---|
| 1 | **XGBoost** | **0.8280 (82.80%)** | 1.75 × 10⁹ | 41,843 | 28,179 |
| 2 | Random Forest | 0.7906 (79.06%) | 2.13 × 10⁹ | 46,170 | 31,040 |
| 3 | Decision Tree | 0.6799 (67.99%) | 3.26 × 10⁹ | 57,079 | 38,649 |
| 4 | Linear Regression | 0.6345 (63.45%) | 3.72 × 10⁹ | 60,992 | 44,656 |
| 5 | Ridge Regression | 0.6345 (63.45%) | 3.72 × 10⁹ | 60,991 | 44,655 |

> Since this is a regression problem, R² score is used as accuracy.

**XGBoost performed the best** with ~83% R² score and lowest error. Cross validation scores were also consistent (XGBoost CV mean R² = 0.8165).

## 🔍 Key Insights

- `median_income` is the most important feature (correlation ≈ 0.65 with price)
- Houses near the coast / Bay Area are much costlier, INLAND houses are cheapest
- Linear models are not enough because relation between features and price is non-linear
- Ensemble models (Random Forest, XGBoost) give much better results

## 🛠️ Tech Stack

Python, Pandas, NumPy, Matplotlib, Seaborn, Scikit-learn, XGBoost, Jupyter Notebook

## ▶️ How to Run

```bash
git clone https://github.com/UtkarshMehta7/house-price-prediction-ml.git
cd house-price-prediction-ml
pip install -r requirements.txt
jupyter notebook House_Price_Prediction.ipynb
```

## 📁 Project Structure

```
├── House_Price_Prediction.ipynb   # main notebook (cleaning, EDA, models)
├── housing.csv                    # dataset
├── requirements.txt
└── README.md
```

## 🚀 Future Scope

- Hyperparameter tuning using GridSearchCV
- Try LightGBM and CatBoost
- Deploy as a web app using Streamlit

---
Made by **Utkarsh Mehta** ✨
