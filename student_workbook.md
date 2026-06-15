---
marp: true
theme: default
paginate: true
size: A4
style: |
  section {
    font-family: 'Segoe UI', 'Noto Sans SC', sans-serif;
    font-size: 22px;
    padding: 40px;
  }
  section.lead {
    text-align: center;
    justify-content: center;
    background: linear-gradient(135deg, #1a3a5c, #1a5276);
    color: white;
  }
  section.lead h1 { font-size: 48px; color: white; }
  section.lead p { font-size: 24px; opacity: 0.9; }
  h1 { color: #1a3a5c; font-size: 32px; }
  h2 { color: #1a5276; font-size: 26px; border-bottom: 3px solid #2e86de; padding-bottom: 6px; }
  table { font-size: 18px; }
  .answer-box {
    border: 2px dashed #2e86de;
    border-radius: 8px;
    padding: 15px;
    margin: 10px 0;
    min-height: 60px;
  }
  .code { font-family: 'Consolas', monospace; background: #f0f2f5; padding: 2px 6px; border-radius: 4px; font-size: 0.85em; }
  .hl { background: #fef9e7; padding: 10px; border-left: 4px solid #f39c12; border-radius: 4px; }
  img[alt~="center"] { display: block; margin: 0 auto; }
  footer { font-size: 14px; }
---

<!-- _class: lead -->

# A4 Machine Learning
# Student Workbook

**IB DP Computer Science 2027**

Name: \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_ &nbsp;&nbsp;&nbsp; Class: \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

Date: \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_ &nbsp;&nbsp;&nbsp; SL / HL (circle one)

---

## How to Use This Workbook

This workbook accompanies the **A4 ML Projects** suite. For each project:

1. Open the HTML file in your browser
2. Read the **real Python code** shown
3. Look at the **real output** from the actual data
4. Click **▶ Run in Colab** to experiment yourself
5. Answer the questions below

**Datasets used (all real):**
- California Housing (US Census, 20,640 houses)
- Telco Customer Churn (Kaggle, 7,043 customers)
- Mall Customers (200 shoppers)
- Online Retail (5,000 real transactions)
- Fashion-MNIST (10,000 clothing images)

---

## Project 1: EDA & ML Types

### Key Concepts

| Term | Definition |
|------|-----------|
| **Supervised Learning** | Model learns from labelled data (features → target) |
| **Unsupervised Learning** | Model finds patterns in unlabelled data |
| **Reinforcement Learning** | Agent learns through trial-and-error + reward |
| **Regression** | Predicts a continuous numerical value |
| **EDA** | Exploratory Data Analysis — understand data through visualization |

### Questions

1. Look at the California housing data. What type of ML problem is this? Why?

<div class="answer-box">

Answer:

</div>

2. The correlation heatmap shows `MedInc` (median income) has the strongest correlation with house value. What does this tell you?

<div class="answer-box">

Answer:

</div>

3. If we removed the house prices (MedHouseVal) from the dataset, what type of ML could we still do?

<div class="answer-box">

Answer:

</div>

4. Would you need a GPU to train a simple regression model on 20,000 rows? Why or why not?

<div class="answer-box">

Answer:

</div>

---

## Project 2: Data Preprocessing

### Key Concepts

| Term | Definition |
|------|-----------|
| **Missing Value** | Data point that doesn't exist (NaN) |
| **Outlier** | Data point far from the normal range |
| **StandardScaler** | Transforms data to mean=0, std=1 |
| **MinMaxScaler** | Transforms data to range [0, 1] |
| **PCA** | Principal Component Analysis — reduces dimensions |
| **Feature Selection** | Choosing which features are most useful |

### Questions

1. What were the three types of data quality problems injected into the dataset?

<div class="answer-box">

Answer:

</div>

2. The IQR method uses `Q1 - 1.5×IQR` and `Q3 + 1.5×IQR` as fences. What percentage of normally distributed data falls outside these fences? (Hint: think about standard deviations)

<div class="answer-box">

Answer:

</div>

3. After PCA, what percentage of variance is explained by the first two components? Is this good enough?

<div class="answer-box">

Answer:

</div>

4. Why is feature scaling necessary before using PCA?

<div class="answer-box">

Answer:

</div>

---

## Project 3: Linear Regression

### Key Concepts

| Term | Definition |
|------|-----------|
| **R² (R-squared)** | Proportion of variance explained by the model (0 to 1) |
| **RMSE** | Root Mean Squared Error — average prediction error |
| **Residual** | Actual value - Predicted value |
| **Coefficient** | Weight assigned to each feature |
| **Regularization** | Penalty to prevent overfitting (Ridge/Lasso) |

### Questions

1. Compare the R² values: Simple regression (MedInc only) vs Multiple regression (8 features). Which is better and by how much?

<div class="answer-box">

Answer:

</div>

2. Look at the residual plots. Is there evidence of heteroscedasticity (funnel shape)? What does this mean?

<div class="answer-box">

Answer:

</div>

3. In the Ridge vs Lasso comparison, what happens when alpha=100 for Lasso? Why?

<div class="answer-box">

Answer:

</div>

4. Calculate: If a model has R²=0.58, what percentage of variance is <em>unexplained</em>?

<div class="answer-box">

Answer:

</div>

---

## Project 4: Hyperparameter Tuning

### Key Concepts

| Term | Definition |
|------|-----------|
| **Overfitting** | Model performs well on training data but poorly on new data |
| **Underfitting** | Model is too simple to capture patterns |
| **Cross-Validation** | Split data into k folds, train on k-1, validate on 1 |
| **Grid Search** | Try all combinations of hyperparameters |
| **Learning Curve** | Plot of performance vs training set size |

### Questions

1. Why do we need validation data separate from test data?

<div class="answer-box">

Answer:

</div>

2. The learning curve shows training and validation scores converging. What does this tell you about overfitting?

<div class="answer-box">

Answer:

</div>

3. If the training score is much higher than the validation score, what should you do?

<div class="answer-box">

Answer:

</div>

4. Grid Search found alpha=1.0 as best. What would happen if you used alpha=0.001 instead?

<div class="answer-box">

Answer:

</div>

---

## Project 5: Classification Demo

### Key Concepts

| Term | Definition |
|------|-----------|
| **K-NN** | K-Nearest Neighbours — classify by majority vote of k neighbours |
| **Decision Tree** | Tree of if-then rules for classification |
| **Accuracy** | (TP + TN) / (Total predictions) |
| **Precision** | TP / (TP + FP) — of predicted positives, how many are correct |
| **Recall** | TP / (TP + FN) — of actual positives, how many are found |

### Questions

1. When k=1 in K-NN, what happens? Why is accuracy lower than k=7?

<div class="answer-box">

Answer:

</div>

2. In the decision tree, which feature is most important for predicting house price category?

<div class="answer-box">

Answer:

</div>

3. K-NN has higher accuracy (83%) than Decision Tree (79%). But the Decision Tree is more interpretable. Which would you use in a real estate app? Why?

<div class="answer-box">

Answer:

</div>

4. Try the interactive K-NN slider. What happens to accuracy as k gets very large (e.g., k=101)?

<div class="answer-box">

Answer:

</div>

---

## Project 6: Ethics & Bias

### Key Concepts

| Term | Definition |
|------|-----------|
| **Algorithmic Bias** | Systematic, unfair treatment of certain groups |
| **Demographic Parity** | Predictions should be similar across demographic groups |
| **Accountability** | Who is responsible for model decisions? |
| **Carbon Footprint** | CO₂ emitted during model training |

### Questions

1. The model overprices Northern California and underprices Southern California. Is this bias or just accurate modeling?

<div class="answer-box">

Answer:

</div>

2. The data includes precise latitude/longitude. What privacy concerns does this raise?

<div class="answer-box">

Answer:

</div>

3. Training a neural network on GPU for 24 hours emits ~3.6 kg CO₂. How many trees would need to be planted to offset this? (1 tree absorbs ~22 kg CO₂/year)

<div class="answer-box">

Answer:

</div>

4. **TOK:** Is a mathematical model "objective" if its training data reflects historical inequalities?

<div class="answer-box">

Answer:

</div>

---

## Project 7: Customer Churn (Extension)

### Key Concepts

| Term | Definition |
|------|-----------|
| **Confusion Matrix** | TP / FP / TN / FN in a table |
| **ROC Curve** | True Positive Rate vs False Positive Rate at various thresholds |
| **AUC** | Area Under the ROC Curve — measure of model quality |
| **F1 Score** | Harmonic mean of Precision and Recall |

### Questions

1. Look at the confusion matrices. Which model does better at finding customers who will churn?

<div class="answer-box">

Answer:

</div>

2. The ROC AUC for the Decision Tree is ~0.82. A perfect classifier has AUC=1.0, random has AUC=0.5. Is 0.82 good?

<div class="answer-box">

Answer:

</div>

3. If you have budget to contact only 10% of customers for retention, would you prioritize Precision or Recall?

<div class="answer-box">

Answer:

</div>

---

## Project 8: Customer Segmentation (Extension)

### Key Concepts

| Term | Definition |
|------|-----------|
| **K-Means** | Partitions data into K clusters based on distance |
| **Elbow Method** | Plot inertia vs K, find the "elbow" |
| **Silhouette Score** | How similar a point is to its own cluster vs others |
| **DBSCAN** | Density-based clustering — finds arbitrary shapes |
| **Dendrogram** | Tree diagram of hierarchical clustering |

### Questions

1. Based on the Elbow Method and Silhouette analysis, what is the optimal K? Why?

<div class="answer-box">

Answer:

</div>

2. What are the 5 customer segments found by K-Means? Describe each in one sentence.

<div class="answer-box">

Answer:

</div>

3. Why did DBSCAN only find 1 cluster while K-Means found 5? What does this tell you about the data?

<div class="answer-box">

Answer:

</div>

4. As a mall manager, which customer segment would you target with a loyalty program? Why?

<div class="answer-box">

Answer:

</div>

---

## Project 9: Market Basket (Extension)

### Key Concepts

| Term | Definition |
|------|-----------|
| **Support** | P(A ∩ B) — frequency of both items appearing together |
| **Confidence** | P(B | A) — probability of B given A |
| **Lift** | P(B|A)/P(B) — how much more likely than random |
| **Apriori** | Algorithm that finds frequent itemsets efficiently |

### Questions

1. The rule "TEA TOWELS 2pk → TEA TOWELS 3pk" has Lift=2.32. Explain what this means in plain English.

<div class="answer-box">

Answer:

</div>

2. If Lift=0.8, what does it tell you? Would you recommend these items be placed together?

<div class="answer-box">

Answer:

</div>

3. What business action would you take based on the rule "CAKESTAND → T-LIGHT HOLDER" (Lift=2.17)?

<div class="answer-box">

Answer:

</div>

---

## Project 10: ANN vs CNN (Extension)

### Key Concepts

| Term | Definition |
|------|-----------|
| **ANN** | Artificial Neural Network — fully connected layers |
| **CNN** | Convolutional Neural Network — uses convolution filters |
| **Convolution** | Sliding window that detects patterns |
| **Pooling** | Downsampling to reduce spatial dimensions |
| **Weight Sharing** | Same filter applied to all locations |

### Questions

1. The ANN flattens a 28×28 image into 784 pixels. What spatial information is lost?

<div class="answer-box">

Answer:

</div>

2. CNN has fewer parameters (~25K) than ANN (~109K) but achieves higher accuracy. How is this possible?

<div class="answer-box">

Answer:

</div>

3. Look at the confusion matrix and misclassification examples. Which pair of clothing items is most often confused? Why?

<div class="answer-box">

Answer:

</div>

4. If you were classifying X-ray images for a hospital, would you choose ANN or CNN? Justify.

<div class="answer-box">

Answer:

</div>

---

<!-- _class: lead -->

# 📝 Quick Reference Card

## Supervised Learning Algorithms

| Algorithm | Type | Pros | Cons |
|-----------|------|------|------|
| Linear Regression | Regression | Simple, interpretable | Only linear relationships |
| K-NN | Both | Intuitive, no training | Slow on large data |
| Decision Tree | Both | Interpretable, handles non-linear | Prone to overfitting |
| ANN | Both | Flexible, powerful | Needs lots of data |
| CNN | Classification | Excellent for images | Needs GPU for training |

## Model Evaluation Metrics

| Metric | Range | Good Value | Use When |
|--------|-------|------------|----------|
| R² | (-∞, 1] | > 0.7 | Regression |
| RMSE | [0, ∞) | Lower = better | Regression |
| Accuracy | [0, 1] | > 0.8 | Balanced classification |
| Precision | [0, 1] | > 0.8 | Minimize false positives |
| Recall | [0, 1] | > 0.8 | Minimize false negatives |
| F1 Score | [0, 1] | > 0.8 | Balance precision & recall |
| ROC AUC | [0.5, 1] | > 0.8 | Overall classifier quality |

## Unsupervised Learning Algorithms

| Algorithm | Type | Pros | Cons |
|-----------|------|------|------|
| K-Means | Clustering | Fast, simple | Need to know K |
| Hierarchical | Clustering | Dendrogram, no K needed | Slow for large data |
| DBSCAN | Clustering | Detects noise, arbitrary shapes | Sensitive to parameters |
| Apriori | Association | Exhaustive search | Slow for many items |

---

## 📊 Data Science Workflow

```
1. Define Problem
       ↓
2. Collect Data ← All projects use REAL data
       ↓
3. Clean & Preprocess ← Project 2
       ↓
4. Explore (EDA) ← Project 1
       ↓
5. Feature Engineering
       ↓
6. Model Selection ← Project 10
       ↓
7. Train & Validate ← Project 3, 4
       ↓
8. Evaluate ← Project 5, 7
       ↓
9. Deploy
       ↓
10. Monitor (Ethics) ← Project 6
```

---

_End of Workbook · Victor 🧠_
