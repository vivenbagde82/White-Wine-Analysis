# 🍷 Wine Quality Analysis and Prediction

This project focuses on analyzing and predicting the quality of wines based on their chemical properties. The dataset contains information about several physicochemical features of wines and their corresponding quality scores (ranging from 1 to 10). The objective of this project is to perform an end-to-end analysis, including data exploration, hypothesis testing, feature engineering, and machine learning.

---

## ✨ Features

This project covers the following steps:

1. **Data Exploration**:
    - Loaded and examined the dataset structure.
    - Analyzed distributions and relationships between features using visualizations such as histograms, scatterplots, and heatmaps.
    - Key insights from pairplots:
      - Most relationships are not perfectly linear, indicating complex interactions.
      - **Alcohol vs. Quality**:
        - Noticeable positive correlation: Higher alcohol content is associated with higher quality wines.
        - Lower alcohol content (9-11%) correlates with lower ratings (3-5), whereas higher alcohol (12-14%) aligns with higher quality ratings (6-8).
      - **Sulphates vs. Quality**:
        - Weak positive correlation: Higher sulphates are slightly associated with higher quality, but there's significant overlap.
        - Sulphates alone do not strongly predict quality.
      - **Density vs. Quality**:
        - Negative correlation: Higher density typically indicates lower quality wines.
        - High-quality wines (8-9) are clustered in the lower density range (0.98-1.00).
      - Other relationships:
        - **Alcohol vs. Sulphates**: Weak positive correlation.
        - **Alcohol vs. Density**: Clear negative correlation (higher alcohol leads to lower density).
        - **Sulphates vs. Density**: Very weak relationship.

2. **Data Cleaning**:
    - Checked for missing values and duplicates (none were found).
    - Dropped duplicate rows for cleaner analysis.

3. **Feature Scaling**:
    - Standardized select features (`free sulfur dioxide` and `total sulfur dioxide`) to improve model performance.

4. **Hypothesis Testing**:
    - Conducted statistical hypothesis tests to examine relationships:
      - Evaluated the impact of features like `pH`, `alcohol`, and `free sulfur dioxide` on wine quality.
      - Performed ANOVA and correlation tests to determine statistical significance.

5. **Predictive Modeling**:
    - Implemented machine learning models:
      - **Linear Regression**: Explored as a baseline regression model for predicting wine quality.
      - **Random Forest Classifier**: Used to predict `quality` as a categorical variable.
    - Assessed model performance using metrics such as accuracy, precision, recall, and F1-score.
    - **Comparison of Models**:
      - **Linear Regression**:
        - Metrics: MAE = 0.59, MSE = 0.578, RMSE = 0.76, R² = 0.295.
        - Limited performance in capturing non-linear relationships, with an R² of only ~29.5%.
      - **Random Forest Classifier**:
        - Achieved 53.7% accuracy.
        - Better at handling categorical predictions but struggled with class imbalance.
        - Stronger performance for majority classes like `quality 6` (F1-score = 0.59) compared to minority classes like `3` and `8`.

**Conclusion**: Random Forest Classifier performed better overall but has room for improvement through class balancing and hyperparameter tuning.

---

## 📊 Key Insights

- **Data Distributions**:
  - The target variable, `quality`, is imbalanced with most samples clustering around scores of 5 and 6.
  
- **Hypothesis Testing**:
  - pH showed no statistically significant impact on wine quality.
  - `free sulfur dioxide` exhibited a statistically significant effect on quality scores.

- **Model Results**:
  - Linear Regression provided an R² of ~0.29, indicating limited success in predicting continuous quality values.
  - Random Forest achieved 53.7% accuracy, with better performance for majority classes (`quality 6`).

