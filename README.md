# HEART-DISEASE-PREDICTIONS

**Heart Disease Prediction Model**
**Overview**
This project demonstrates the use of a Logistic Regression Model for predicting the likelihood of heart disease based on various clinical parameters. The model uses data preprocessing, visualization, and statistical techniques to achieve accurate and interpretable predictions.
**Features**
•	Data preprocessing, including handling duplicates and converting variables.
•	Data visualization to explore relationships and distributions.
•	Logistic regression modeling and optimization.
•	Model diagnostics and validation (e.g., multicollinearity, residual analysis).
•	Performance evaluation using metrics such as ROC-AUC.
**Tools and Libraries**
•	R Programming Language
•	Libraries:
o	tidyverse
o	ggplot2
o	dplyr
o	caTools
o	pROC
o	performance
**Workflow**
**Step 1: Load Data**
The dataset heart.csv was loaded and examined for structure, missing values, and duplicates.
heart <- read_csv("path/to/heart.csv")
**Step 2: Data Preprocessing**
•	Removed duplicate rows.
•	Converted categorical variables into factors for better interpretation and modeling.
**Step 3: Data Exploration**
•	Visualized distributions (e.g., age histogram) and relationships (e.g., boxplots for cholesterol levels by target).
•	Computed correlation matrix and visualized it using a heatmap.
**Step 4: Splitting Data**
•	Split the dataset into training (80%) and testing (20%) sets to prevent overfitting.
set.seed(2)
split <- sample.split(heart$target, SplitRatio = 0.8)
training <- subset(heart, split == TRUE)
testing <- subset(heart, split == FALSE)
**Step 5: Model Building**
•	Built a logistic regression model to predict target (heart disease presence).
model <- glm(target ~ ., training, family = binomial)
**Step 6: Model Optimization**
•	Removed insignificant variables iteratively to improve AIC and performance.
**Step 7: Model Validation**
•	Checked assumptions:
o	Linearity of log-odds.
o	Independence of residuals.
o	Multicollinearity using Variance Inflation Factor (VIF).
•	Evaluated performance with ROC-AUC.
**Step 8: Predictions**
•	Generated predictions on the test set.
•	Visualized probabilities and assessed model accuracy.
**Results**
•	Optimized logistic regression model achieved an AUC of 0.955, indicating excellent classification performance.
•	Significant predictors included:
o	Chest pain type.
o	Maximum heart rate achieved.
o	Resting blood pressure.
**Visualizations**
•	Correlation heatmaps.
•	Distribution histograms for key features.
•	ROC curve showing classification performance.
**How to Run**
1.	Clone the repository:
git clone https://github.com/AjinkyaLab/heart-disease-prediction.git
2.	Ensure you have R and the necessary libraries installed.
3.	Run the heart_disease_prediction.R script.
