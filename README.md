# Movie-Rating-Prediction

## 📌 Goal
Predict IMDb ratings for Indian movies using features like genre, director, actors, duration, votes, and year.

---

## 📊 Approach

1. Data Loading
   - Source IMDb Movies India dataset (CSV).
   - Loaded using pandas and encoded with 'ISO-8859-1' due to non-UTF-8 characters.

2. Preprocessing
   - Converted `Year`, `Duration`, and `Votes` columns to numeric.
   - Filled missing values using
     - Median for numeric columns.
     - `'Unknown'` for categorical fields (Genre, Director, Actors).
   - Categorical variables encoded with `LabelEncoder`.

3. Feature Engineering
   - Director Success Rate Average rating of all movies by a given director.
   - Genre Average Rating Mean rating across movies in the same genre.

4. Model Training
   - Target `Rating`
   - Features `Year`, `Duration`, `Votes`, `Genre`, `Director_Success`, `Genre_Avg_Rating`
   - Model `RandomForestRegressor`
   - Data split 80% training  20% testing

5. Evaluation
   - Metrics used
     - MAE (Mean Absolute Error) Measures average absolute error.
     - MSE (Mean Squared Error) Penalizes large errors more than MAE.
     - R² Score Proportion of variance explained by the model.

6. Output
   - Predictions saved to file.
   - Model persisted as `.pkl` file using `joblib`.
   - Evaluation metrics saved to `outputsmetrics.txt`.
   - Scatter plot of predicted vs actual ratings saved as `prediction_vs_actual.png`.

---

## 📈 Sample Evaluation Results
```
MAE 0.45
MSE 0.39
R² Score 0.74
```

---

## ▶️ How to Run

1. Place your dataset inside `IMDb Movies India.csv`
2. Run notebooks or scripts in `src`
3. Outputs will be saved to `outputs`
