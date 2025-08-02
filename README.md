# rate-my-professor
📊 EDA digging into biases in RMP data

## 🔧 Data Processing
- **Weighted Rating**: `avg_rating × log(num_ratings)` to handle rating volume bias
- **STEM Classification**: Binary encoding using keyword matching  
- **PCA**: Dimensionality reduction for regression models
- **Reproducibility**: Random seed `16987856`

## 📈 Key Findings

### 👨‍🏫 Gender Bias
- Male professors receive significantly higher ratings (p ≈ 0)
- Cohen's d = 0.088 (small effect)

### 🎓 Experience vs Quality  
- High experience professors rated higher (p ≈ 0)
- Cohen's d = 0.074 (small effect)

### 📚 Rating vs Difficulty
- Strong negative correlation: r = -0.537
- 28.8% of rating variance explained by difficulty

### 💻 Online vs In-Person
- In-person classes rated higher (p ≈ 0)
- Cohen's d = 0.387 (small-moderate effect)

### 🔄 Rating vs Retake Rate
- Strong positive correlation: r = 0.767
- 58.8% of rating variance explained

### 🌶️ "Hot or Not" Effect
- "Hot" professors rated significantly higher (p ≈ 0)
- Cohen's d = 1.016 (large effect)

## 🤖 Predictive Models

### Linear Regression (Rating from Difficulty)
- R² = 0.29, RMSE = 0.95
- Coefficient: -0.61 (each difficulty point drops rating ~0.6)

### Multiple Regression (All Factors)
- R² = 0.75, RMSE = 0.43
- 75% variance explained vs 29% difficulty-only

### Logistic Regression (Predicting "Hotness")
- Rating only: AUROC = 0.692
- All factors: AUROC = 0.742

## 🎯 Extra Credit: STEM vs Humanities
- **No significant difference** in ratings (p = 0.096)
- STEM courses significantly more difficult (p ≈ 0)
- Difficulty doesn't translate to rating bias

## 🛠️ Tech Stack
- pandas, numpy, scipy, sklearn
- Mann-Whitney U tests, Pearson correlation
- PCA, Linear/Logistic regression
- Bootstrap validation
