# PredictingNBAawards

## Overview  
This project explores the prediction of NBA annual award winners, such as the **Most Valuable Player (MVP)**, **Most Improved Player (MIP)**, **Defensive Player of the Year (DPOY)**, and **All-NBA selections**, using advanced player statistics. By leveraging machine learning models, we analyze key performance metrics to determine which players are most likely to win these prestigious awards.  

## Data Sources  
- **Basketball Reference**: Comprehensive player statistics from the 2015-2024 NBA seasons  
- Advanced metrics: **Shooting percentage, assist percentage, Player Efficiency Rating (PER), Real Plus-Minus (RPM), Value Over Replacement Player (VORP)**  
- Team performance factors such as **win-loss records**  

## Methodology  

### 1. Predictor Selection  
Given the high-dimensional nature of NBA player statistics, we conducted **exploratory data analysis (EDA)** using histograms, correlation matrices, and feature importance analysis. To prevent multicollinearity, we prioritized impactful features such as **VORP** and **RPM**, identified through **Random Forest and Gradient Boosting** models.  

### 2. Model Selection  
Since award predictions involve ranking and scoring players based on performance, we utilized **regression models** rather than traditional classification methods. The models tested include:  
- **Linear Regression**  
- **Decision Tree Regression**  
- **Random Forest Regression**  
- **Gradient Boosting Regression**  

To select the best model, we applied **GridSearchCV** for hyperparameter tuning and performed **5-fold cross-validation**.  

### 3. Best Model Selection  
- **Random Forest Regression** was ultimately chosen due to its strong balance of accuracy and interpretability.  
- **Gradient Boosting Regression** performed similarly but presented challenges in interpretability.  

## Results and Performance  
Using our test validation set, the **Random Forest Regression model** achieved:  
- **R² Score**: **0.8334** (83.34% of variance explained)  
- **Mean Squared Error (MSE)**: **0.0066**  
- **Mean Absolute Error (MAE)**: **0.0288**  
- **Confusion Matrix Accuracy**: **98.89%**  

However, this high accuracy is influenced by an **imbalanced dataset** where award winners are a small fraction of all players. The MVP award, for instance, is given to only **one** player per season, making non-winners easier to classify correctly.  

## Key Insights  
- **Multi-label classification**: Instead of predicting awards individually, we modeled them together, as performance metrics influencing one award often correlate with others.  
- **Limitations**: The model does not capture external factors such as **public perception, media narratives, or team success**, which influence voting outcomes.  
- **Potential Improvements**: Adding contextual features like **game-by-game trends, social media sentiment, and advanced tracking data** could improve accuracy.  
