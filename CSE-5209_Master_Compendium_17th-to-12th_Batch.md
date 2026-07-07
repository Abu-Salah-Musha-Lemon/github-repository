# CSE-5209: Advanced Data Mining and Machine Learning
## Master Solutions Compendium — 17th to 12th Batch Final Examinations
### Jagannath University — Department of Computer Science & Engineering
### MSc. in CSE (P), 2nd Semester Final Examinations (Course Code: CSE-5209)

---

## Table of Contents

1. [17th Batch (2025)](#17th-batch-2025)
2. [16th Batch (2025)](#16th-batch-2025)
3. [15th Batch (2024)](#15th-batch-2024)
4. [14th Batch (2024)](#14th-batch-2024)
5. [13th Batch (2023)](#13th-batch-2023)
6. [12th Batch (2023)](#12th-batch-2023)
7. [Appendix: Key Formulas & Theoretical Reference](#appendix-key-formulas--theoretical-reference)

---

## How to Use This Compendium

This document compiles complete, worked solutions for **all six** available past exam papers of CSE-5209 (Advanced Data Mining & Machine Learning), ordered from the most recent (17th Batch) to the oldest (12th Batch). Several questions repeat verbatim or with minor variations across years (e.g., the K-means clustering task on points A1–C2, the chi-square "Health Status" dataset, the FCM 5-instance dataset, and the TF-IDF corpus) — where this happens, the **first full derivation is presented in detail**, and later occurrences reference back to it to avoid redundancy while still stating the final answer inline.

Each question is answered with **both the theoretical explanation** (definitions, concepts, when/why a method applies) **and the full mathematical derivation** (step-by-step formulas, intermediate values, and final results) so the reasoning is fully auditable, not just the final numbers.

---

# 17th Batch (2025)

### Full Solutions — MSc. in CSE (P), 2nd Semester Final Exam 2025 (17th Batch)

---

### Question 1

#### a) What is Machine Learning? Major types of ML algorithms.

**Machine Learning (ML)** is a branch of artificial intelligence in which a system learns patterns from data and improves its performance on a task without being explicitly programmed with fixed rules. Instead of hard-coding logic, an ML algorithm is trained on example data and builds a mathematical model that generalizes to new, unseen data.

**Major types of ML algorithms:**

1. **Supervised Learning** – The model learns from labeled data (input–output pairs). Used for classification (e.g., spam detection) and regression (e.g., price prediction). Examples: Linear Regression, Decision Trees, SVM, Naïve Bayes.
2. **Unsupervised Learning** – The model finds hidden structure in unlabeled data. Used for clustering (e.g., K-means) and association rule mining (e.g., Apriori), and dimensionality reduction (e.g., PCA).
3. **Semi-Supervised Learning** – Uses a small amount of labeled data combined with a large amount of unlabeled data to improve learning accuracy.
4. **Reinforcement Learning** – An agent learns by interacting with an environment, receiving rewards or penalties, and improving its policy over time (e.g., Q-learning, used in robotics and game-playing agents).

#### b) Application areas of ML

- Spam and fraud detection
- Medical diagnosis and disease prediction
- Recommendation systems (Netflix, Amazon)
- Speech and image recognition
- Natural language processing (chatbots, translation)
- Autonomous vehicles
- Credit scoring and risk assessment
- Predictive maintenance in manufacturing
- Stock market and sales forecasting

#### c) Supervised vs. Unsupervised Learning

| Aspect | Supervised Learning | Unsupervised Learning |
|---|---|---|
| Data | Labeled (input + known output) | Unlabeled (input only) |
| Goal | Predict output for new inputs | Discover hidden patterns/structure |
| Examples | Classification, Regression | Clustering, Association rule mining |
| Algorithms | Linear Regression, SVM, KNN, Decision Trees | K-means, DBSCAN, Apriori, PCA |
| Evaluation | Accuracy, Precision, Recall, MSE (ground truth available) | Silhouette score, cluster cohesion (no ground truth) |
| Use case | Spam detection, price prediction | Customer segmentation, anomaly detection |

---

### Question 2

#### a) Confusion Matrix, Precision, Recall, F1-score

True Labels: `[Spam, Not Spam, Spam, Not Spam, Not Spam, Spam, Not Spam, Spam, Not Spam, Not Spam]`
Predicted Labels: `[Spam, Spam, Not Spam, Not Spam, Spam, Spam, Not Spam, Not Spam, Not Spam, Not Spam]`

Taking **Spam = Positive class**, comparing pair by pair:

| # | True | Predicted | Result |
|---|------|-----------|--------|
| 1 | Spam | Spam | TP |
| 2 | Not Spam | Spam | FP |
| 3 | Spam | Not Spam | FN |
| 4 | Not Spam | Not Spam | TN |
| 5 | Not Spam | Spam | FP |
| 6 | Spam | Spam | TP |
| 7 | Not Spam | Not Spam | TN |
| 8 | Spam | Not Spam | FN |
| 9 | Not Spam | Not Spam | TN |
| 10 | Not Spam | Not Spam | TN |

**Counts:** TP = 2, FP = 2, FN = 2, TN = 4

**Confusion Matrix:**

|  | Predicted: Spam | Predicted: Not Spam |
|---|---|---|
| **Actual: Spam** | TP = 2 | FN = 2 |
| **Actual: Not Spam** | FP = 2 | TN = 4 |

**Calculations:**
- Precision = TP / (TP + FP) = 2 / (2+2) = **0.5**
- Recall = TP / (TP + FN) = 2 / (2+2) = **0.5**
- F1-score = 2×(Precision×Recall)/(Precision+Recall) = 2×(0.5×0.5)/(1.0) = **0.5**

#### b) Chi-square test for feature significance

Target class = **Health Status** (Good/Poor). Data:

| Age Group | Gender | Smoker | Health Status |
|---|---|---|---|
| Young | Male | Yes | Good |
| Middle | Female | No | Good |
| Young | Female | Yes | Poor |
| Elderly | Male | No | Poor |
| Middle | Male | Yes | Good |

Good = 3 rows, Poor = 2 rows, Total = 5.

**Feature: Smoker vs Health Status**

| | Good | Poor | Total |
|---|---|---|---|
| Yes | 2 | 1 | 3 |
| No | 1 | 1 | 2 |
| Total | 3 | 2 | 5 |

Expected values: E(Yes,Good)=1.8, E(Yes,Poor)=1.2, E(No,Good)=1.2, E(No,Poor)=0.8

χ² = (2-1.8)²/1.8 + (1-1.2)²/1.2 + (1-1.2)²/1.2 + (1-0.8)²/0.8 = 0.022+0.033+0.033+0.05 = **0.139**

**Feature: Gender vs Health Status**

Same distribution as Smoker (Male: 2 Good/1 Poor; Female: 1 Good/1 Poor) → **χ² = 0.139**

**Feature: Age Group vs Health Status**

| | Good | Poor | Total |
|---|---|---|---|
| Young | 1 | 1 | 2 |
| Middle | 2 | 0 | 2 |
| Elderly | 0 | 1 | 1 |
| Total | 3 | 2 | 5 |

Expected: E(Young,Good)=1.2, E(Young,Poor)=0.8, E(Middle,Good)=1.2, E(Middle,Poor)=0.8, E(Elderly,Good)=0.6, E(Elderly,Poor)=0.4

χ² = (1-1.2)²/1.2 + (1-0.8)²/0.8 + (2-1.2)²/1.2 + (0-0.8)²/0.8 + (0-0.6)²/0.6 + (1-0.4)²/0.4
= 0.033+0.05+0.533+0.8+0.6+0.9 = **2.917**

**Conclusion:** Age Group has the highest χ² statistic (2.917 vs 0.139 for Gender and Smoker), so **Age Group is the most significant feature** relative to the others in this small sample (though with df=2, this value is still below the χ²-critical value of 5.99 at α=0.05, so statistical significance would need a larger sample — the relative comparison is what identifies Age Group as the strongest of the three).

#### c) Python modules for ML/DL

- **NumPy** – numerical/array computation
- **Pandas** – data manipulation and analysis
- **Matplotlib / Seaborn** – data visualization
- **Scikit-learn** – classical ML algorithms (classification, regression, clustering)
- **SciPy** – scientific/statistical computation
- **TensorFlow / Keras** – deep learning framework
- **PyTorch** – deep learning framework
- **XGBoost / LightGBM** – gradient boosting
- **NLTK / spaCy** – natural language processing

---

### Question 3

#### a) Block diagram of Bagging ensemble algorithm

Bagging (**B**ootstrap **Agg**regat**ing**) works as follows:

```
                         Original Training Dataset (D)
                                    │
             ┌──────────────┬───────┴───────┬──────────────┐
        Bootstrap        Bootstrap       Bootstrap       Bootstrap
        Sample D1        Sample D2       Sample D3   ...  Sample Dn
        (sampled with    (sampled with   (sampled with    (sampled with
         replacement)     replacement)    replacement)     replacement)
             │                 │               │                │
        Base Model 1      Base Model 2    Base Model 3     Base Model n
        (e.g. Tree 1)     (e.g. Tree 2)   (e.g. Tree 3)    (e.g. Tree n)
             │                 │               │                │
             └────────┬────────┴───────┬───────┴────────────────┘
                       │                │
               Aggregation (Voting for classification /
                           Averaging for regression)
                       │
                 Final Prediction
```

Each base model is trained independently and in parallel on a different bootstrap sample of the original data. Their outputs are combined (majority vote for classification, average for regression) to produce a final, more stable and lower-variance prediction. Random Forest is the most well-known example of bagging.

#### b) Clustering algorithms comparison

| Algorithm | Cluster Shapes | Key Input Parameters | Limitations |
|---|---|---|---|
| **k-means** | Spherical, convex, roughly equal-sized | k (number of clusters) | Must pre-specify k; sensitive to initial centroids and outliers; poor with non-convex shapes |
| **k-medoids** | Spherical/convex (similar to k-means) | k | More robust to outliers than k-means but computationally expensive (O(k(n−k)²) per iteration); doesn't scale to large n |
| **CLARA** | Spherical/convex | k, sample size | Efficiency depends on sample representativeness; may miss the true best medoids if the sample is biased |
| **BIRCH** | Spherical, works best for even-sized numeric clusters | Branching factor, threshold radius, (optional) number of clusters | Sensitive to the order of data input; struggles with non-spherical or arbitrary-shaped clusters |
| **CHAMELEON** | Arbitrary, complex shapes | k-nearest-neighbor graph size, relative interconnectivity/closeness thresholds | Computationally expensive; parameter tuning is complex; does not scale well to very large datasets |
| **DBSCAN** | Arbitrary shape (dense regions separated by sparse regions) | eps (neighborhood radius), minPts (minimum points per neighborhood) | Struggles when clusters have varying densities; sensitive to eps/minPts choice; less effective in high-dimensional data |

#### c) List of Python modules — *(same as Q2c above; not repeated per exam instructions)*

---

### Question 4

#### a) Simple Linear Regression: predict weight at height = 175 cm

Data: Height = [150,160,170,180,190], Weight = [45,50,60,70,80]

Mean height x̄ = 170, mean weight ȳ = 61

| x−x̄ | y−ȳ | (x−x̄)(y−ȳ) | (x−x̄)² |
|---|---|---|---|
| −20 | −16 | 320 | 400 |
| −10 | −11 | 110 | 100 |
| 0 | −1 | 0 | 0 |
| 10 | 9 | 90 | 100 |
| 20 | 19 | 380 | 400 |
| **Σ** | | **900** | **1000** |

Slope: b₁ = Σ(x−x̄)(y−ȳ) / Σ(x−x̄)² = 900/1000 = **0.9**

Intercept: b₀ = ȳ − b₁x̄ = 61 − 0.9(170) = 61 − 153 = **−92**

Regression equation: **Weight = −92 + 0.9 × Height**

At Height = 175 cm: Weight = −92 + 0.9(175) = −92 + 157.5 = **65.5 kg**

#### b) Designing/fine-tuning SVM parameters

Key SVM hyperparameters and how to tune them:

- **C (regularization parameter):** Controls the trade-off between maximizing the margin and minimizing classification error. Small C → wider margin, more tolerance for misclassification (less overfitting, more bias). Large C → narrower margin, fits training data more tightly (risk of overfitting).
- **Kernel choice:** Linear (for linearly separable data), Polynomial, RBF (Radial Basis Function — good default for non-linear data), Sigmoid. Choice depends on the data's underlying structure.
- **Gamma (for RBF/poly kernels):** Controls how far the influence of a single training example reaches. Low gamma → smoother decision boundary (may underfit). High gamma → boundary closely fits individual points (may overfit).

**Practical approach:** Use **Grid Search** or **Randomized Search** combined with **k-fold cross-validation** to systematically try combinations of C, gamma, and kernel, selecting the combination that gives the best validation accuracy/F1-score while avoiding overfitting.

#### c) Classification vs Regression

| Aspect | Classification | Regression |
|---|---|---|
| Output | Discrete category/class label | Continuous numeric value |
| Example | Predicting whether an email is spam or not | Predicting the price of a house |
| Evaluation | Accuracy, Precision, Recall, F1 | MSE, RMSE, MAE, R² |
| Algorithms | Logistic Regression, SVM, Decision Tree, KNN | Linear Regression, Polynomial Regression, SVR |

---

### Question 5

#### a) Data visualization — definition and types

**Data visualization** is the graphical representation of data and information, using visual elements like charts, graphs, and maps to help identify patterns, trends, and outliers in data.

**Types of data visualizations:**
- Bar chart / column chart
- Line chart
- Scatter plot
- Histogram
- Pie chart
- Box plot
- Heatmap
- Area chart
- Bubble chart
- Tree map / dendrogram

#### b) Different ML types to solve a problem

- **Supervised learning** — when labeled historical data with known outcomes is available (e.g., classifying loan applications as approved/rejected based on past labeled records).
- **Unsupervised learning** — when no labels exist and the goal is to discover structure (e.g., segmenting customers into groups based on purchase behavior).
- **Semi-supervised learning** — when only a small subset of data is labeled, useful when labeling is expensive (e.g., medical image analysis where only some images have expert-verified labels).
- **Reinforcement learning** — when the problem involves sequential decision-making with feedback from an environment (e.g., training a robot or a game-playing agent).

The right type depends on: whether labeled data exists, the nature of the desired output (prediction, grouping, or action policy), and how the system receives feedback.

#### c) Forward propagation vs Backpropagation

| Aspect | Forward Propagation | Backpropagation |
|---|---|---|
| Direction | Input → hidden layers → output | Output → hidden layers → input (error flows backward) |
| Purpose | Compute the predicted output using current weights | Compute the gradient of the loss w.r.t. each weight to update them |
| Process | Applies weights, biases, and activation functions layer by layer | Uses the chain rule of calculus to propagate the error gradient backward |
| Result | Produces a prediction | Produces weight/bias updates (used with gradient descent) |
| When it runs | Every prediction / every training pass (first step) | Only during training, after the loss is computed (second step) |

---

### Question 6

#### a) Dendrogram via Agglomerative Clustering (Single Linkage)

*Note: The distance table has one internal inconsistency (Chittagong–Barisal is listed as 445 in one row and 415 in another); the calculation below uses 415, taking the Barisal row as the reference. The linkage method used is single linkage (nearest-neighbor distance) since the exam question does not specify one.*

**Step 1:** Smallest distance = Khulna–Barisal = **135** → merge into cluster (Khulna, Barisal)

**Step 2:** Recompute distances (minimum to either member): Dhaka–(Khulna,Barisal) = min(215,170) = **170** → smallest remaining → merge Dhaka in → cluster (Dhaka, Khulna, Barisal)

**Step 3:** Sylhet–(Dhaka,Khulna,Barisal) = min(240,360,390) = **240** → smallest remaining → merge Sylhet in → cluster (Dhaka, Khulna, Barisal, Sylhet)

**Step 4:** Chittagong–(Dhaka,Khulna,Barisal,Sylhet) = min(245,440,415,345) = **245** → merge Chittagong in

**Step 5:** Rajshahi joins the rest at distance **255** (min of its distances to all merged cities)

**Merge sequence (dendrogram heights):**

```
135 — Khulna + Barisal
170 — Dhaka joins (Khulna, Barisal)
240 — Sylhet joins (Dhaka, Khulna, Barisal)
245 — Chittagong joins (Dhaka, Khulna, Barisal, Sylhet)
255 — Rajshahi joins — all cities merged into one cluster
```

Text dendrogram (heights increase left→right):

```
Khulna    ─┐
           ├─ 135 ─┐
Barisal   ─┘        ├─ 170 ─┐
Dhaka     ──────────┘        ├─ 240 ─┐
Sylhet    ────────────────────┘       ├─ 245 ─┐
Chittagong────────────────────────────┘        ├─ 255
Rajshahi ───────────────────────────────────────┘
```

#### b) Fuzzy C-Means (FCM), one iteration, m = 2

*Note: Instance 5's given membership values (0.6, 0.6) don't sum to 1 as required; used (0.6, 0.4) for Instance 5, consistent with the standard FCM constraint that memberships across clusters sum to 1.*

**Data:**

| Instance | X | Y | C1 | C2 |
|---|---|---|---|---|
| 1 | 1 | 3 | 0.2 | 0.8 |
| 2 | 2 | 4 | 0.3 | 0.7 |
| 3 | 3 | 2 | 0.5 | 0.5 |
| 4 | 5 | 5 | 0.4 | 0.6 |
| 5 | 4 | 6 | 0.6 | 0.4 |

**Step 1 — Compute new cluster centers** (weighted by uᵢⱼ², since m=2):

v₁ = ( Σuᵢ₁²·xᵢ / Σuᵢ₁² , Σuᵢ₁²·yᵢ / Σuᵢ₁² ) = **(3.567, 4.378)**

v₂ = ( Σuᵢ₂²·xᵢ / Σuᵢ₂² , Σuᵢ₂²·yᵢ / Σuᵢ₂² ) = **(2.532, 3.758)**

**Step 2 — Compute Euclidean distances of each point to both centers:**

| Instance | d(i, v1) | d(i, v2) |
|---|---|---|
| 1 | 2.913 | 1.709 |
| 2 | 1.612 | 0.584 |
| 3 | 2.444 | 1.819 |
| 4 | 1.563 | 2.763 |
| 5 | 1.679 | 2.680 |

**Step 3 — Update membership matrix** using uᵢⱼ = 1 / Σₖ (dᵢⱼ/dᵢₖ)^(2/(m−1)); with m=2, exponent = 2:

| Instance | C1 (updated) | C2 (updated) |
|---|---|---|
| 1 | 0.256 | 0.744 |
| 2 | 0.116 | 0.884 |
| 3 | 0.356 | 0.644 |
| 4 | 0.758 | 0.242 |
| 5 | 0.718 | 0.282 |

**Cluster membership after iteration 1** (assigning each instance to its higher-membership cluster):

- **Cluster 1:** Instances 4, 5
- **Cluster 2:** Instances 1, 2, 3

---

### Question 7

#### a) Neural network design (4 inputs, 1 hidden layer of 3 neurons, 1 output neuron)

A **neural network** is a computational model inspired by biological neurons, consisting of layers of interconnected nodes that transform input data through weighted connections and activation functions to produce an output.

**Architecture:**

```
Input Layer (4 neurons)      Hidden Layer (3 neurons)     Output Layer (1 neuron)

   x1 ──┐
   x2 ──┼──[W1: 3×4, b1: 3×1]──►  h1, h2, h3  ──[W2: 1×3, b2: scalar]──►  ŷ
   x3 ──┤        (with activation, e.g. ReLU/Sigmoid)      (with activation, e.g. Sigmoid)
   x4 ──┘
```

- **W1** is a 3×4 weight matrix connecting 4 inputs to 3 hidden neurons; **b1** is a 3×1 bias vector.
- Each hidden neuron computes: hⱼ = f(Σ Wᵢⱼxᵢ + bⱼ), where f is an activation function (e.g., ReLU or Sigmoid).
- **W2** is a 1×3 weight vector connecting the 3 hidden neurons to the single output; **b2** is a scalar bias.
- Output: ŷ = f(Σ W2ⱼhⱼ + b2), typically using Sigmoid for binary classification.

#### b) Pandas code for student_scores.csv

```python
import pandas as pd

df = pd.read_csv('student_scores.csv')
print(df.head())

max_math = df['Math'].max()
min_math = df['Math'].min()
print(f"Max Math score: {max_math}")
print(f"Min Math score: {min_math}")

avg_scores = df[['Math', 'Science', 'History']].mean()
print("Average scores per subject:")
print(avg_scores)
```

#### c) What is hyperparameter tuning?

**Hyperparameter tuning** is the process of finding the optimal set of hyperparameters (settings configured before training, such as learning rate, number of trees, k in KNN, C/gamma in SVM, or number of hidden layers in a neural network) that produce the best model performance on unseen/validation data. Unlike model parameters (weights), hyperparameters are not learned directly from the training data — they are chosen through methods like **Grid Search**, **Random Search**, or **Bayesian Optimization**, typically evaluated using cross-validation, to balance underfitting and overfitting and maximize generalization performance.

---

*End of solutions — Questions 1–7, 17th Batch (2025) exam paper.*

---

# 16th Batch (2025)

### Full Solutions — MSc. in CSE (P), 2nd Semester Final Exam 2025 (16th Batch)

---

### Question 1

#### a) Can machine learning solve any problem? Justify with examples.

No — machine learning is not a universal problem-solver. It works well when three conditions hold: (1) there is enough relevant, quality data, (2) the problem has learnable statistical patterns (not pure randomness), and (3) some tolerance for imperfect/probabilistic answers is acceptable.

- **Where ML works well:** Spam filtering (patterns in word usage), image recognition (patterns in pixel structure), price prediction (patterns in historical trends).
- **Where ML struggles or fails:** Problems requiring exact logical/deterministic answers with zero data (e.g., proving a mathematical theorem), problems with insufficient or biased data (e.g., predicting rare disease outbreaks with only 5 recorded cases), or problems requiring true causal/common-sense reasoning beyond correlation (e.g., understanding sarcasm reliably without huge contextual data).

So ML can solve *many* problems, but not *any* problem — it depends on data availability and problem structure.

#### b) Types of machine learning algorithms

1. **Supervised Learning** — learns from labeled data to predict outputs (classification/regression). E.g., Decision Trees, SVM, Linear Regression.
2. **Unsupervised Learning** — finds structure in unlabeled data (clustering, association rules). E.g., K-means, Apriori.
3. **Semi-Supervised Learning** — combines small labeled + large unlabeled data.
4. **Reinforcement Learning** — an agent learns via rewards/penalties from interacting with an environment. E.g., Q-learning.

#### c) Classification vs Regression

| Aspect | Classification | Regression |
|---|---|---|
| Output | Discrete class label | Continuous numeric value |
| Example | Email spam/not spam | Predicting house price |
| Metrics | Accuracy, Precision, Recall, F1 | MSE, RMSE, R² |

#### d) Normalizing {200, 300, 400, 600, 1000}

**I. Min-max normalization** (min=0, max=1): v' = (v − min)/(max − min), where min=200, max=1000

| Value | Normalized |
|---|---|
| 200 | 0.000 |
| 300 | 0.125 |
| 400 | 0.250 |
| 600 | 0.500 |
| 1000 | 1.000 |

**II. Z-score normalization**: mean μ = 500, standard deviation σ = 316.23

| Value | Z-score |
|---|---|
| 200 | −0.949 |
| 300 | −0.632 |
| 400 | −0.316 |
| 600 | 0.316 |
| 1000 | 1.581 |

**III. Z-score using Mean Absolute Deviation (MAD)**: MAD = (1/n)Σ|v−μ| = 240

| Value | Z-score (MAD) |
|---|---|
| 200 | −1.250 |
| 300 | −0.833 |
| 400 | −0.417 |
| 600 | 0.417 |
| 1000 | 2.083 |

**IV. Decimal scaling**: divide by 10^j, where j = number of digits in max value (1000 → j=4, since 10³ ≤ 1000 < 10⁴... using j such that max scaled value < 1, j=4)

| Value | Scaled |
|---|---|
| 200 | 0.02 |
| 300 | 0.03 |
| 400 | 0.04 |
| 600 | 0.06 |
| 1000 | 0.10 |

---

### Question 2

#### a) KNN Classification (k=3, Euclidean distance)

New fruit: Weight = 155, Texture = 1

| Training Point | Weight | Texture | Label | Distance to (155,1) |
|---|---|---|---|---|
| 1 | 150 | 1 | Apple | √(25+0) = **5.00** |
| 5 | 160 | 1 | Apple | √(25+0) = **5.00** |
| 2 | 170 | 1 | Apple | √(225+0) = 15.00 |
| 3 | 140 | 0 | Orange | √(225+1) = 15.03 |
| 4 | 130 | 0 | Orange | √(625+1) = 25.02 |
| 6 | 120 | 0 | Orange | √(1225+1) = 35.01 |

**3 Nearest Neighbors:** Instance 1 (Apple, d=5.00), Instance 5 (Apple, d=5.00), Instance 2 (Apple, d=15.00)

All 3 nearest neighbors are **Apple** → **Predicted class = Apple**

#### b) Accuracy, Sensitivity, Specificity, Precision, Recall

|  | Predicted: Yes | Predicted: No | Total |
|---|---|---|---|
| **Actual: Yes** | TP = 6954 | FN = 46 | 7000 |
| **Actual: No** | FP = 412 | TN = 2588 | 3000 |
| **Total** | 7366 | 2634 | 10000 |

- **Accuracy** = (TP+TN)/Total = (6954+2588)/10000 = 9542/10000 = **95.42%**
- **Sensitivity (Recall)** = TP/(TP+FN) = 6954/7000 = **99.34%**
- **Specificity** = TN/(TN+FP) = 2588/3000 = **86.27%**
- **Precision** = TP/(TP+FP) = 6954/7366 = **94.41%**
- **Recall** = same as Sensitivity = **99.34%**

#### c) Categorical encoding methods

**1. Label Encoding** — assigns an integer to each category (already partially shown in the "Categorical value of fruit" column):

| Fruit | Label Encoded | Price |
|---|---|---|
| apple | 1 | 5 |
| mango | 2 | 10 |
| apple | 1 | 15 |
| orange | 3 | 20 |

*Caution:* Label encoding implies an ordinal relationship (1<2<3) that doesn't actually exist between fruit types, which can mislead distance-based or linear models.

**2. One-Hot Encoding** — creates a binary column per category, avoiding false ordinal relationships:

| apple | mango | orange | Price |
|---|---|---|---|
| 1 | 0 | 0 | 5 |
| 0 | 1 | 0 | 10 |
| 1 | 0 | 0 | 15 |
| 0 | 0 | 1 | 20 |

One-hot encoding is generally preferred for nominal (non-ordinal) categorical features like fruit type.

---

### Question 3

#### a) Standard ensemble learning strategies

1. **Bagging (Bootstrap Aggregating)** — trains multiple base models independently on bootstrap samples of the data, then combines predictions via voting/averaging (e.g., Random Forest). Reduces variance.
2. **Boosting** — trains models sequentially, where each new model focuses on correcting the errors of the previous ones (e.g., AdaBoost, XGBoost, Gradient Boosting). Reduces bias.
3. **Stacking** — trains several different base models, then uses a meta-model to combine their outputs into a final prediction.
4. **Voting** — combines predictions of multiple different models via majority vote (classification) or averaging (regression), without a formal meta-learner.

#### b) Chi-square test for feature significance (Health Status dataset)

Same dataset structure as before. Good=3, Poor=2, Total=5.

**Smoker vs Health Status:** χ² = **0.139**
**Gender vs Health Status:** χ² = **0.139**
**Age Group vs Health Status:**

| | Good | Poor | Total |
|---|---|---|---|
| Young | 1 | 1 | 2 |
| Middle | 2 | 0 | 2 |
| Elderly | 0 | 1 | 1 |

χ² = 0.033+0.05+0.533+0.8+0.6+0.9 = **2.917**

**Conclusion: Age Group is the most significant feature** (χ² = 2.917, the highest among the three features tested), indicating the strongest association with Health Status in this sample.

---

### Question 4

#### a) K-means clustering (3 clusters)

Points: A1(2,10), A2(2,5), A3(8,4), B1(5,8), B2(7,5), B3(6,4), C1(1,2), C2(4,9)
Initial centers: A1(2,10), B1(5,8), C1(1,2)

**Round 1 — assign each point to nearest initial center:**

| Point | Dist to A1(2,10) | Dist to B1(5,8) | Dist to C1(1,2) | Assigned |
|---|---|---|---|---|
| A1(2,10) | 0.00 | 3.61 | 8.06 | A |
| A2(2,5) | 5.00 | 4.24 | 3.16 | C |
| A3(8,4) | 8.49 | 5.00 | 7.28 | B |
| B1(5,8) | 3.61 | 0.00 | 7.21 | B |
| B2(7,5) | 7.07 | 3.61 | 6.71 | B |
| B3(6,4) | 7.21 | 4.12 | 5.39 | B |
| C1(1,2) | 8.06 | 7.21 | 0.00 | C |
| C2(4,9) | 2.24 | 1.41 | 7.62 | B |

**I. Cluster centers after first round:**
- Cluster A: {A1} → center = **(2.0, 10.0)**
- Cluster B: {A3, B1, B2, B3, C2} → center = **(6.0, 6.0)**
- Cluster C: {A2, C1} → center = **(1.5, 3.5)**

**II. Final clusters (after iterating to convergence):**

Continuing to reassign points to the nearest updated center and recomputing centers until no changes occur, the algorithm converges to:

- **Cluster A** = {A1, B1, C2} → final center ≈ **(3.67, 9.0)**
- **Cluster B** = {A3, B2, B3} → final center ≈ **(7.0, 4.33)**
- **Cluster C** = {A2, C1} → final center = **(1.5, 3.5)**

#### b) Key parameters of SVM and their influence

| Parameter | Role | Effect on model |
|---|---|---|
| **C (regularization)** | Trade-off between margin width and misclassification | Small C → wider margin, more bias, less overfitting. Large C → narrower margin, fits data tightly, risk of overfitting |
| **Kernel** (linear, poly, RBF, sigmoid) | Transforms data into higher-dimensional space to find a separating hyperplane | Choice depends on data linearity; RBF handles non-linear boundaries well |
| **Gamma (γ)** (RBF/poly) | Controls the influence radius of a single training example | Low γ → smoother, more generalized boundary (underfit risk). High γ → tightly fit boundary (overfit risk) |
| **Degree** (poly kernel only) | Degree of the polynomial | Higher degree → more complex boundary, higher overfitting risk |

These parameters directly control the bias-variance trade-off, model flexibility, and generalization to unseen data — typically tuned via grid search + cross-validation.

---

### Question 5

#### a) Linear Regression + MSE

**Training data:** Height=[152,158,165,172,178], Weight=[47,51,58,66,72]

x̄ = 165, ȳ = 58.8

| x−x̄ | y−ȳ | product | (x−x̄)² |
|---|---|---|---|
| −13 | −11.8 | 153.4 | 169 |
| −7 | −7.8 | 54.6 | 49 |
| 0 | −0.8 | 0 | 0 |
| 7 | 7.2 | 50.4 | 49 |
| 13 | 13.2 | 171.6 | 169 |
| **Σ** | | **430** | **436** |

b₁ = 430/436 = **0.9862**
b₀ = 58.8 − 0.9862(165) = 58.8 − 162.72 = **−103.92**

**Regression equation:** Weight = −103.92 + 0.9862 × Height

**i. Model trained** (equation above).

**ii. Predictions on test set** Height=[154,160,168]:

| Height | Predicted Weight |
|---|---|
| 154 | −103.92 + 0.9862(154) = **48.95** |
| 160 | −103.92 + 0.9862(160) = **54.86** |
| 168 | −103.92 + 0.9862(168) = **62.76** |

**iii. Mean Squared Error** (actual = [49, 53, 61]):

| Actual | Predicted | Error | Squared Error |
|---|---|---|---|
| 49 | 48.95 | 0.05 | 0.0025 |
| 53 | 54.86 | −1.86 | 3.460 |
| 61 | 62.76 | −1.76 | 3.098 |

MSE = (0.0025+3.460+3.098)/3 = 6.56/3 ≈ **2.19**

#### b) Importance of hyperparameter tuning

Hyperparameter tuning is critical because hyperparameters (e.g., learning rate, k, C, number of trees, number of hidden layers) are not learned from data — they control model capacity and the bias-variance trade-off directly. Poorly chosen hyperparameters can cause underfitting (model too simple) or overfitting (model memorizes training data). Systematic tuning (Grid Search, Random Search, Bayesian Optimization) with cross-validation ensures the model generalizes well to unseen data, often producing significant performance gains without changing the underlying algorithm.

#### c) Evaluating a classifier on an imbalanced multi-class dataset

Accuracy alone is misleading on imbalanced data (a model predicting only the majority class can still score high accuracy). Better approaches:

- **Per-class Precision, Recall, F1-score** — computed separately for each class to reveal poor performance on minority classes.
- **Macro-averaged F1** — averages F1 across classes equally (treats all classes as equally important, regardless of size).
- **Weighted-averaged F1** — averages F1 weighted by class frequency.
- **Confusion matrix** — shows exactly where misclassifications occur across classes.
- **Cohen's Kappa** — measures agreement corrected for chance.

**Example:** In a 3-class fraud dataset (Normal=9000, Suspicious=800, Fraud=200), a model predicting "Normal" for everything gets 90% accuracy but 0% recall on Fraud — macro F1 would expose this failure clearly, whereas overall accuracy would not.

---

### Question 6

#### a) What is an Artificial Neural Network (ANN)?

An **Artificial Neural Network** is a computational model inspired by the structure of biological neurons in the brain. It consists of layers of interconnected nodes (neurons) — an input layer, one or more hidden layers, and an output layer — where each connection has an associated weight. Neurons apply an activation function to a weighted sum of their inputs, allowing the network to learn complex, non-linear relationships between inputs and outputs through training (typically via backpropagation and gradient descent).

#### b) Design: 3 input neurons, 1 hidden layer (4 neurons), 2 output neurons

```
Input Layer (3)         Hidden Layer (4)          Output Layer (2)

  x1 ──┐
  x2 ──┼──[W1: 4×3, b1: 4×1]──► h1,h2,h3,h4 ──[W2: 2×4, b2: 2×1]──► y1, y2
  x3 ──┘         (activation function, e.g. ReLU/Sigmoid)   (activation, e.g. Softmax/Sigmoid)
```

- **W1** is a 4×3 weight matrix (3 inputs → 4 hidden neurons); **b1** is a 4×1 bias vector.
- Hidden layer computation: **h = f(W1·x + b1)**
- **W2** is a 2×4 weight matrix (4 hidden neurons → 2 outputs); **b2** is a 2×1 bias vector.
- Output layer computation: **y = f(W2·h + b2)**
- Total trainable parameters: (3×4 + 4) + (4×2 + 2) = 16 + 10 = **26 parameters**

#### c) Single-layer NN with sigmoid activation

net = w₁x₁ + w₂x₂ + bias; output = sigmoid(net) = 1/(1+e^(−net))

**i. weights = (0.5, 0.5), bias = −0.7:**

| Input (x1,x2) | net | Output (sigmoid) |
|---|---|---|
| (0,0) | −0.7 | **0.332** |
| (0,1) | −0.2 | **0.450** |
| (1,0) | −0.2 | **0.450** |
| (1,1) | 0.3 | **0.574** |

**ii. weights = (−0.5, 0.5), bias = 0.8:**

| Input (x1,x2) | net | Output (sigmoid) |
|---|---|---|
| (0,0) | 0.8 | **0.690** |
| (0,1) | 1.3 | **0.786** |
| (1,0) | 0.3 | **0.574** |
| (1,1) | 0.8 | **0.690** |

---

### Question 7

#### a) TF-IDF feature matrix

Corpus:
- Doc1: "Artificial intelligence is transforming industries."
- Doc2: "Machine learning is a subset of artificial intelligence."
- Doc3: "Deep learning is a popular branch of machine learning."

Using **TF-IDF = tf × log₁₀(N/df)**, N=3 documents:

| Term | df | idf = log₁₀(3/df) |
|---|---|---|
| a | 2 | 0.176 |
| artificial | 2 | 0.176 |
| branch | 1 | 0.477 |
| deep | 1 | 0.477 |
| industries | 1 | 0.477 |
| intelligence | 2 | 0.176 |
| is | 3 | 0.000 |
| learning | 2 | 0.176 |
| machine | 2 | 0.176 |
| of | 2 | 0.176 |
| popular | 1 | 0.477 |
| subset | 1 | 0.477 |
| transforming | 1 | 0.477 |

**TF-IDF matrix:**

| Term | Doc1 | Doc2 | Doc3 |
|---|---|---|---|
| a | 0.000 | 0.176 | 0.176 |
| artificial | 0.176 | 0.176 | 0.000 |
| branch | 0.000 | 0.000 | 0.477 |
| deep | 0.000 | 0.000 | 0.477 |
| industries | 0.477 | 0.000 | 0.000 |
| intelligence | 0.176 | 0.176 | 0.000 |
| is | 0.000 | 0.000 | 0.000 |
| learning | 0.000 | 0.176 | 0.352 |
| machine | 0.000 | 0.176 | 0.176 |
| of | 0.000 | 0.176 | 0.176 |
| popular | 0.000 | 0.000 | 0.477 |
| subset | 0.000 | 0.477 | 0.000 |
| transforming | 0.477 | 0.000 | 0.000 |

*Note: "is" gets a TF-IDF of 0 because it appears in every document (idf=log(3/3)=0), correctly identifying it as a non-discriminative term.*

#### b) N-grams for: "LLM models are now making software automatically"

Tokens: [LLM, models, are, now, making, software, automatically] (7 tokens)

**Unigrams (7):** LLM | models | are | now | making | software | automatically

**Bigrams (6):**
LLM models | models are | are now | now making | making software | software automatically

**Trigrams (5):**
LLM models are | models are now | are now making | now making software | making software automatically

---

*End of solutions — Questions 1–7, 16th Batch (2025) exam paper.*

---

# 15th Batch (2024)

### Full Solutions — MSc. in CSE (P), 2nd Semester Final Exam 2024 (15th Batch)

---

### Question 1

#### a) Characteristics of noisy/unprocessed data & how to identify them

**Common characteristics of noisy/unprocessed data:**

- **Missing values** — blank cells or nulls in the dataset. *Impact:* biases statistics, breaks algorithms that can't handle NaNs, reduces effective sample size.
- **Outliers** — values that deviate drastically from the rest of the data (e.g., an age of 300). *Impact:* skews means/variances, distorts model coefficients (especially in linear models), can dominate distance-based methods like KNN/K-means.
- **Inconsistent formatting** — e.g., dates as "2024-01-05" in some rows and "05/01/2024" in others, or "NY" vs "New York". *Impact:* algorithms treat inconsistent labels as different categories, fragmenting what should be one group.
- **Irrelevant/redundant features** — columns that don't contribute predictive signal (e.g., a customer ID) or duplicate the same information as another column. *Impact:* adds noise, increases overfitting risk, and slows training without adding value.
- **Duplicate records** — the same entity recorded multiple times. *Impact:* over-weights certain patterns, biasing the model.

**How these are identified during initial exploration:**
- Summary statistics (`.describe()`) reveal impossible min/max values (outliers) and count mismatches (missing values).
- Histograms/box plots visually reveal outliers and skew.
- `.value_counts()` on categorical columns reveals inconsistent labels/typos.
- Correlation matrices reveal redundant/irrelevant features.
- `.duplicated()` checks reveal duplicate rows.

#### b) Z-scores for {10,20,30,40,50}, μ=30, σ=14.14

Z = (x − μ) / σ

| x | Z-score |
|---|---|
| 10 | (10−30)/14.14 = **−1.414** |
| 20 | (20−30)/14.14 = **−0.707** |
| 30 | (30−30)/14.14 = **0.000** |
| 40 | (40−30)/14.14 = **0.707** |
| 50 | (50−30)/14.14 = **1.414** |

#### c) KNN (k=3, Manhattan/Hamming distance for categorical data) — predict class of (Red, Large, Square)

For categorical attributes, Manhattan distance reduces to a mismatch count (0 if same, 1 if different) summed across attributes:

| Instance | Color | Size | Shape | Class | Distance to (Red,Large,Square) |
|---|---|---|---|---|---|
| 1 | Red | Large | Circle | A | (0)+(0)+(1) = **1** |
| 4 | Green | Large | Square | B | (1)+(0)+(0) = **1** |
| 2 | Blue | Medium | Square | B | (1)+(1)+(0) = **2** |
| 3 | Red | Small | Circle | A | (0)+(1)+(1) = **2** |
| 5 | Red | Medium | Circle | A | (0)+(1)+(1) = **2** |

*Note: there's a tie — Instances 1 and 4 are tied at distance 1, and Instances 2, 3, 5 are tied at distance 2. Taking the 3 nearest in the given data order (Instance 1, Instance 4, then Instance 2 as the next tied entry): neighbors = {A, B, B}.*

**Majority vote → Predicted Class = B** (2 out of 3 nearest neighbors are class B)

*(If instead Instance 3 or 5 is picked as the tie-breaker for the 3rd neighbor — both class A — the result would tie 2-2... but with the given data ordering, class B is the majority.)*

---

### Question 2

#### a) Age data: quartiles, five-number summary, boxplot, Q-Q vs quantile plot

Data (n=27, sorted): 13,15,16,16,19,20,20,21,22,22,25,25,25,25,30,33,33,35,35,35,35,36,40,45,46,52,70

**I. Q1 and Q3:**
Using position (n+1)/4 = 7th value → **Q1 = 20**
Using position 3(n+1)/4 = 21st value → **Q3 = 35**

**II. Five-number summary:**
Minimum = 13, Q1 = 20, Median (Q2) = 25, Q3 = 35, Maximum = 70

**III. Boxplot:**

```
   13         20      25       35              70
   |──────────┤███████│████████┤───────────────|
 Min          Q1     Median    Q3             Max
        (whiskers)  (box: IQR = Q3-Q1 = 15)  (whisker)
```
The box spans Q1(20) to Q3(35) with a line at the median (25); whiskers extend to the min (13) and max (70), assuming no extreme outliers beyond 1.5×IQR.

**IV. Q-Q plot vs Quantile plot:**
A **quantile plot** displays the quantiles of a *single* dataset against their corresponding f-values (percentiles) — it shows the distribution of one variable. A **quantile-quantile (Q-Q) plot** compares the quantiles of *two* datasets (or one dataset against a theoretical distribution, like the normal distribution) against each other — it's used to check whether two distributions have the same shape or whether data follows an assumed distribution.

#### b) Handling missing values

- **Ignore the tuple** — drop rows with missing values (only advisable when few rows are affected).
- **Fill manually** — a domain expert fills in the missing value (impractical for large datasets).
- **Fill with a global constant** — e.g., "Unknown" or 0 (can distort analysis if overused).
- **Fill with the attribute mean/median** — for numeric attributes (mean for symmetric data, median for skewed data).
- **Fill with the mean/median of the same class** — using class-conditional statistics for more accuracy in supervised settings.
- **Fill using the most probable value** — via regression, decision tree induction, or other predictive imputation methods (most sophisticated and generally most accurate).

#### c) Normalizing {200, 300, 400, 600, 1000} — *(identical task to 16th Batch Q1d)*

**I. Min-max [0,1]:** 0.000, 0.125, 0.250, 0.500, 1.000
**II. Z-score** (μ=500, σ=316.23): −0.949, −0.632, −0.316, 0.316, 1.581
**III. Z-score with MAD** (MAD=240): −1.250, −0.833, −0.417, 0.417, 2.083
**IV. Decimal scaling** (÷10⁴): 0.02, 0.03, 0.04, 0.06, 0.10

---

### Question 3

#### a) TF-IDF feature matrix — *(identical corpus to 16th Batch Q7a)*

Using TF-IDF = tf × log₁₀(N/df), N=3:

| Term | Doc1 | Doc2 | Doc3 |
|---|---|---|---|
| a | 0.000 | 0.176 | 0.176 |
| artificial | 0.176 | 0.176 | 0.000 |
| branch | 0.000 | 0.000 | 0.477 |
| deep | 0.000 | 0.000 | 0.477 |
| industries | 0.477 | 0.000 | 0.000 |
| intelligence | 0.176 | 0.176 | 0.000 |
| is | 0.000 | 0.000 | 0.000 |
| learning | 0.000 | 0.176 | 0.352 |
| machine | 0.000 | 0.176 | 0.176 |
| of | 0.000 | 0.176 | 0.176 |
| popular | 0.000 | 0.000 | 0.477 |
| subset | 0.000 | 0.477 | 0.000 |
| transforming | 0.477 | 0.000 | 0.000 |

(Full derivation with df/idf table available in the 16th Batch solution document, Q7a.)

#### b) Standard ensemble learning strategies

1. **Bagging** — parallel training on bootstrap samples, combined via voting/averaging (reduces variance). E.g., Random Forest.
2. **Boosting** — sequential training where each model corrects prior errors (reduces bias). E.g., AdaBoost, XGBoost.
3. **Stacking** — a meta-model learns how to best combine the outputs of several different base models.
4. **Voting** — simple majority vote (classification) or average (regression) across multiple independently trained models.

---

### Question 4

#### a) Linear Regression + MSE (Height → Weight)

**Training data:** Height=[150,160,170,180,190], Weight=[45,50,60,70,80]

x̄=170, ȳ=61; Σ(x−x̄)(y−ȳ)=900; Σ(x−x̄)²=1000

b₁ = 900/1000 = **0.9**
b₀ = 61 − 0.9(170) = **−92**

**Regression equation: Weight = −92 + 0.9 × Height**

**Predictions on test set** Height=[155,165,175,185], Actual=[48,55,68,75]:

| Height | Predicted | Actual | Error | Squared Error |
|---|---|---|---|---|
| 155 | −92+0.9(155)=47.5 | 48 | −0.5 | 0.25 |
| 165 | −92+0.9(165)=56.5 | 55 | 1.5 | 2.25 |
| 175 | −92+0.9(175)=65.5 | 68 | −2.5 | 6.25 |
| 185 | −92+0.9(185)=74.5 | 75 | −0.5 | 0.25 |

**MSE** = (0.25+2.25+6.25+0.25)/4 = 9/4 = **2.25**

#### b) How to design an SVM model that achieves the highest accuracy?

- **Feature scaling:** Normalize/standardize features first — SVM is distance-based and sensitive to feature scale.
- **Kernel selection:** Try linear kernel for linearly separable data; RBF kernel for non-linear data (usually a strong default).
- **Hyperparameter tuning:** Systematically tune **C** (regularization) and **gamma** (kernel coefficient) using Grid Search or Random Search with k-fold cross-validation.
- **Handle class imbalance:** Use class weighting (`class_weight='balanced'`) if classes are imbalanced.
- **Avoid overfitting:** Use cross-validation to check generalization rather than only training accuracy; avoid excessively high C or gamma.
- **Feature selection/dimensionality reduction:** Remove noisy/irrelevant features (or apply PCA) to improve the margin quality.
- **Ensemble/combine with other models** if a single SVM underperforms, via voting/stacking.

---

### Question 5

#### a) Chi-square test — Loan Approval dataset

Target: Loan Approved (Yes=3, No=2)

**Education Level vs Loan Approved:**

| | Yes | No |
|---|---|---|
| Graduate | 2 | 0 |
| High School | 0 | 2 |
| Postgraduate | 1 | 0 |

χ² = **5.00**

**Marital Status vs Loan Approved:**

| | Yes | No |
|---|---|---|
| Married | 2 | 0 |
| Single | 1 | 1 |
| Divorced | 0 | 1 |

χ² = **2.917**

**Employment Type vs Loan Approved:**

| | Yes | No |
|---|---|---|
| Salaried | 2 | 0 |
| Self-Employed | 1 | 1 |
| Unemployed | 0 | 1 |

χ² = **2.917**

**Conclusion: Education Level is the most significant feature** (χ² = 5.00, the highest among the three), showing the strongest association with loan approval outcome in this sample — every "Graduate" and "Postgraduate" applicant was approved, while every "High School" applicant was rejected, a perfect separation that drives the high chi-square value.

#### b) Bar chart — income group most likely to purchase

*Note: The bar chart image referenced in this question wasn't extractable as readable data from the uploaded document — I can't determine the specific income group without seeing the actual chart values. If you can share the chart (image or the underlying numbers), I can identify which income group has the tallest bar/highest purchase likelihood.*

#### c) Importance of hyperparameter tuning — *(same explanation as 16th Batch Q5b)*

Hyperparameter tuning is essential because hyperparameters control model capacity and the bias-variance trade-off but aren't learned from the training data itself. Poor choices lead to underfitting or overfitting; systematic tuning (Grid Search, Random Search, Bayesian Optimization) combined with cross-validation ensures the best generalization to unseen data.

---

### Question 6

#### a) K-means clustering (3 clusters) — *(identical task to 16th Batch Q4a)*

Points: A1(2,10), A2(2,5), A3(8,4), B1(5,8), B2(7,5), B3(6,4), C1(1,2), C2(4,9)
Initial centers: A1, B1, C1

**I. Cluster centers after first round:**
- Cluster A: {A1} → **(2.0, 10.0)**
- Cluster B: {A3, B1, B2, B3, C2} → **(6.0, 6.0)**
- Cluster C: {A2, C1} → **(1.5, 3.5)**

**II. Final clusters (after convergence):**
- **Cluster A** = {A1, B1, C2} → center ≈ **(3.67, 9.0)**
- **Cluster B** = {A3, B2, B3} → center ≈ **(7.0, 4.33)**
- **Cluster C** = {A2, C1} → center = **(1.5, 3.5)**

(Full step-by-step reassignment iterations are shown in the 16th Batch solution document, Q4a.)

---

*End of solutions — Questions 1–6 answered (Q5b bar chart could not be solved without the actual chart data), 15th Batch (2024) exam paper.*

---

# 14th Batch (2024)

### Full Solutions — MSc. in CSE (P), 2nd Semester Final Exam 2024 (14th Batch)

---

### Question 1

#### a) What is data mining?

**Data mining** is the process of discovering interesting, non-trivial, previously unknown, and potentially useful patterns or knowledge from large volumes of data, using techniques drawn from statistics, machine learning, database systems, and pattern recognition.

**I. Is it another hype?** No — data mining is not just hype. While the term became a buzzword, the underlying need (extracting actionable knowledge from ever-growing data volumes) is a genuine, persistent business and scientific requirement, evidenced by its continued real-world use in fraud detection, recommendation engines, genomics, and more, decades after the term was coined.

**II. Is it simply a transformation/application of existing technology?** Partly — data mining does build on and integrate techniques from databases (efficient storage/retrieval), statistics (inference, hypothesis testing), machine learning (predictive modeling), and pattern recognition (structure discovery). However, it is more than a simple repackaging: it specifically focuses on scalability to very large datasets, automation of the discovery process, and extracting *actionable, novel* patterns rather than merely applying existing statistical tests, which requires distinct algorithmic innovations (e.g., Apriori, FP-Growth, scalable clustering).

#### b) Example where data mining is crucial to business success

**Example:** A large e-commerce retailer (like Amazon) uses data mining to power its **recommendation system**, mining patterns such as "customers who bought X also bought Y" (association rule mining), customer segments with similar purchasing behavior (clustering), and predicting which customers are likely to churn (classification).

**Could these patterns be generated by simple query processing or statistics alone?** No — simple SQL queries can only answer questions you already know to ask (e.g., "how many customers bought X"), and basic statistics can reveal simple correlations but not complex, multi-way, previously-unknown association patterns across millions of transactions and thousands of products. Data mining algorithms (like Apriori/FP-Growth for pattern discovery, or collaborative filtering for recommendations) are needed to automatically discover these non-obvious, scalable patterns that a human analyst or a static query could not feasibly find by hand.

#### c) Challenges of mining huge data vs. small data

| Challenge | Small dataset (hundreds of tuples) | Huge dataset (billions of tuples) |
|---|---|---|
| **Scalability** | Any algorithm runs quickly, fits in memory | Requires distributed/parallel processing (e.g., Hadoop/Spark); many algorithms don't scale linearly |
| **I/O and memory constraints** | Entire data fits in RAM | Data often can't fit in memory; disk I/O becomes the bottleneck |
| **Noise and data quality** | Easier to manually inspect and clean | Noise, missing values, and inconsistencies are pervasive and can't be manually fixed |
| **Algorithm complexity** | Even exponential algorithms may be feasible | Algorithms with high time complexity (e.g., O(n²) or worse) become computationally infeasible |
| **Result interpretability** | Few patterns, easy to interpret manually | Enormous numbers of patterns/rules generated, requiring additional filtering for interestingness |
| **Real-time constraints** | Not usually critical | Streaming/real-time mining requirements are common at this scale (e.g., fraud detection) |

---

### Question 2

#### a) Confusion Matrix, Precision, Recall — *(identical labels to 17th Batch Q2a)*

TP=2, FP=2, FN=2, TN=4

|  | Predicted: Spam | Predicted: Not Spam |
|---|---|---|
| **Actual: Spam** | 2 | 2 |
| **Actual: Not Spam** | 2 | 4 |

**Precision** = 2/4 = **0.5**
**Recall** = 2/4 = **0.5**

#### b) Chi-square test for feature significance — *(identical dataset structure to 17th Batch Q2b)*

- **Smoker vs Health Status:** χ² = **0.139**
- **Gender vs Health Status:** χ² = **0.139**
- **Age Group vs Health Status:** χ² = **2.917**

**Conclusion: Age Group is the most significant feature** (highest χ² = 2.917).

---

### Question 3

#### a) Algorithm to determine if itemset X is frequent (given closed frequent itemsets C)

Given the set **C** of all frequent **closed** itemsets and their support counts, to determine whether an itemset **X** is frequent (and find its support if so):

1. Search **C** for the smallest closed itemset **Y** such that **X ⊆ Y** (i.e., find all closed itemsets that are supersets of X, and pick the one with the smallest support count among them — since support is anti-monotonic, the smallest superset closed itemset gives the tightest support bound).
2. If such a **Y** exists: **X is frequent**, and **support(X) = support(Y)** for the smallest such Y (because closed itemsets capture the maximal itemset sharing that support value — any subset of a closed itemset Y has support ≥ support(Y), and the *tightest* such bound comes from the smallest enclosing closed itemset).
3. If no closed itemset in **C** is a superset of X, then **X is not frequent** (its true support is below the minimum support threshold).

This works because the set of closed frequent itemsets is a lossless, compact representation of all frequent itemsets and their exact supports — every frequent itemset's support equals the support of the smallest closed itemset that contains it.

#### b) Apriori vs FP-Growth — market basket analysis

Transactions:
- T100: {King's-Crab, Sunset-Milk, Dairyland-Cheese, Best-Bread}
- T200: {Best-Cheese, Dairyland-Milk, Goldenfarm-Apple, Tasty-Pie, Wonder-Bread}
- T300: {Westcoast-Apple, Dairyland-Milk, Wonder-Bread, Tasty-Pie}
- T400: {Wonder-Bread, Sunset-Milk, Dairyland-Cheese}

min_sup = 60% of 4 transactions = 2.4 → **minimum support count needed = 3**

**Item support counts:**

| Item | Count | Support % |
|---|---|---|
| Wonder-Bread | 3 (T200,T300,T400) | 75% |
| Sunset-Milk | 2 (T100,T400) | 50% |
| Dairyland-Cheese | 2 (T100,T400) | 50% |
| Dairyland-Milk | 2 (T200,T300) | 50% |
| Tasty-Pie | 2 (T200,T300) | 50% |
| King's-Crab, Best-Bread, Best-Cheese, Goldenfarm-Apple, Westcoast-Apple | 1 each | 25% |

**Apriori:** Scans the database level-by-level. L1 (frequent 1-itemsets, count≥3) = **{Wonder-Bread}** only. Since only *one* item is frequent, no candidate 2-itemsets can be generated (joining requires at least 2 frequent (k-1)-itemsets), so the algorithm terminates. **Final frequent itemsets = {Wonder-Bread} (support 75%)**.

**FP-Growth:** Builds a frequency-ordered FP-tree (Wonder-Bread first, as the most frequent item), then mines conditional pattern bases per item without candidate generation. Since no other item reaches the support-count threshold of 3, the conditional pattern base mining also yields only **{Wonder-Bread}** as frequent.

**No association rules can be generated** at min_conf=80% since rule generation requires a frequent itemset of size ≥ 2 (to split into antecedent → consequent), and none exists at this support threshold.

**Efficiency comparison:** Apriori requires multiple full database scans (one per itemset-size level) and generates many candidate itemsets that must be tested against the database — this candidate generation-and-test approach becomes very expensive as itemsets grow, especially with lower support thresholds or denser data. FP-Growth requires only **two** database scans total (one to compute item frequencies, one to build the FP-tree), and mines frequent patterns directly from the compressed tree structure via recursive conditional pattern-base construction — avoiding candidate generation entirely. In this tiny 4-transaction example both trivially terminate at the same single-itemset answer, but on large/dense datasets FP-Growth is significantly more efficient than Apriori.

---

### Question 4

#### a) Constraint-based association rule mining — classify each constraint

| Constraint | Type | How to mine it |
|---|---|---|
| **i. Containing at least one Blu-ray DVD movie** | **Succinct constraint** (also monotonic) — can be directly translated into a specific data-selection condition without needing iterative testing | Directly restrict candidate generation to only itemsets containing at least one Blu-ray DVD item — since satisfying supersets remain satisfying, once found, all supersets automatically qualify, so no further checking of this condition is needed as the itemset grows |
| **ii. Sum of prices < $150** | **Anti-monotonic constraint** — if a itemset violates it (sum ≥ $150), every superset also violates it (since prices are non-negative, adding items can't decrease the sum) | Prune during candidate generation: once an itemset's sum reaches/exceeds $150, discard it and all its supersets immediately (similar pruning logic to the support-based Apriori pruning) |
| **iii. One free item (price=0) + sum of other items ≥ $200** | **Convertible constraint** — not simply anti- or monotonic in raw form, but becomes monotonic if items are sorted by price in a particular order | Sort items by price; process/mine in that order so the constraint behaves monotonically along the sorted sequence, enabling early pruning/stopping during mining |
| **iv. Average price of all items between $100 and $500** | **Convertible constraint** — average is not monotonic or anti-monotonic in general (adding a cheap item can lower the average, adding an expensive item can raise it) | Sort items by price (ascending or descending depending on which bound is being tested) so that the average constraint becomes monotonic/anti-monotonic along that specific ordering, allowing it to be pushed into the mining process similarly to anti-monotonic pruning |

#### b) Accuracy, sensitivity, specificity, precision, recall — *(identical confusion matrix to 16th Batch Q2b)*

- **Accuracy** = 9542/10000 = **95.42%**
- **Sensitivity (Recall)** = 6954/7000 = **99.34%**
- **Specificity** = 2588/3000 = **86.27%**
- **Precision** = 6954/7366 = **94.41%**

---

### Question 5

#### a) Significance test comparing M1 vs M2 (paired, α=0.01)

Since the *same* data partitioning is used for both models in each round, a **paired t-test** on the per-round error differences is appropriate.

M1 errors: 30.5, 32.2, 20.7, 20.6, 31.0, 41.0, 27.7, 26.0, 21.5, 26.0
M2 errors: 22.4, 14.5, 22.4, 19.6, 20.7, 20.4, 22.1, 19.4, 16.2, 35.0

- Mean of differences (M1−M2): **d̄ = 6.45**
- Std. deviation of differences: **s_d ≈ 8.70**
- Standard error: s_d/√10 ≈ 2.751
- **t-statistic = d̄ / (s_d/√n) = 6.45 / 2.751 ≈ 2.344**
- Degrees of freedom = n−1 = **9**
- Two-tailed critical value at α=0.01, df=9: **t_crit ≈ 3.250**
- p-value ≈ 0.044

**Conclusion:** Since |t| = 2.344 < t_crit = 3.250 (and p ≈ 0.044 > 0.01), we **fail to reject the null hypothesis** at the 1% significance level. **There is not enough statistical evidence to conclude that M2 is significantly better than M1** at α=0.01, even though M2 has a numerically lower average error rate across the 10 rounds. (Note: at a less strict α=0.05, the result would be significant, since 0.044 < 0.05 — but the question specifically asks about the 1% level.)

#### b) Handling class imbalance (bank fraud detection example)

**General methods for class imbalance:**
- **Oversampling the minority class** (e.g., SMOTE — Synthetic Minority Oversampling Technique — generates synthetic fraud examples).
- **Undersampling the majority class** (randomly reduce non-fraud examples, risking loss of information).
- **Cost-sensitive learning** — assign a higher misclassification cost to the minority (fraud) class so the model is penalized more for missing fraud cases.
- **Ensemble methods** — e.g., Balanced Random Forest, EasyEnsemble, which combine sampling with ensemble learning.
- **Anomaly/outlier detection framing** — treat fraud as a rare anomaly detection problem instead of standard binary classification (e.g., One-Class SVM, Isolation Forest).
- **Threshold moving** — adjust the classification decision threshold (instead of the default 0.5) to favor recall on the minority class.
- **Appropriate evaluation metrics** — use Precision, Recall, F1, AUC-PR instead of plain accuracy, which is misleading on imbalanced data.

**Applied to bank fraud detection:** With a large set of non-fraud transactions and very few fraud cases, a quality classifier can be built by: (1) applying SMOTE to oversample the fraud class (or combining SMOTE with random undersampling of non-fraud transactions to balance the training set), (2) training a cost-sensitive model (e.g., Random Forest or XGBoost with `class_weight`/`scale_pos_weight` set to penalize missed fraud heavily), and (3) evaluating using Precision-Recall AUC and Recall-at-fixed-Precision rather than accuracy, since a model predicting "not fraud" for everything would still show >99% accuracy but be useless in practice.

---

### Question 6

#### a) K-means clustering (3 clusters) — *(identical task to 16th/15th Batch)*

**I. Cluster centers after first round:**
- Cluster A: {A1} → **(2.0, 10.0)**
- Cluster B: {A3, B1, B2, B3, C2} → **(6.0, 6.0)**
- Cluster C: {A2, C1} → **(1.5, 3.5)**

**II. Final clusters (after convergence):**
- **Cluster A** = {A1, B1, C2} → center ≈ **(3.67, 9.0)**
- **Cluster B** = {A3, B2, B3} → center ≈ **(7.0, 4.33)**
- **Cluster C** = {A2, C1} → center = **(1.5, 3.5)**

#### b) Clustering algorithms comparison — *(identical to 17th Batch Q3b)*

| Algorithm | Cluster Shapes | Key Parameters | Limitations |
|---|---|---|---|
| **k-means** | Spherical, convex | k | Sensitive to initial centroids/outliers; must pre-specify k |
| **k-medoids** | Spherical/convex | k | Robust to outliers but computationally expensive; doesn't scale well |
| **CLARA** | Spherical/convex | k, sample size | Depends on sample representativeness |
| **BIRCH** | Spherical, even-sized | Branching factor, threshold radius | Sensitive to data order; struggles with non-spherical clusters |
| **CHAMELEON** | Arbitrary shapes | k-NN graph size, interconnectivity/closeness thresholds | Computationally expensive; complex tuning |
| **DBSCAN** | Arbitrary shape | eps, minPts | Struggles with varying density; sensitive to parameters |

---

### Question 7

#### a) Overview of ML techniques + FCM clustering

**Brief overview of ML techniques:** Supervised learning (classification, regression), unsupervised learning (clustering, association rules, dimensionality reduction), semi-supervised learning, and reinforcement learning — see Q1(b) of the 17th Batch solution document for full details.

**FCM Clustering (m=2), one iteration** — *(identical dataset to 17th Batch Q6c)*:

Data: Instance(X,Y,C1,C2): (1,3,0.2,0.8), (2,4,0.3,0.7), (3,2,0.5,0.5), (5,5,0.4,0.6), (4,6,0.6,0.4)

**Cluster centers:** v1 = (3.567, 4.378), v2 = (2.532, 3.758)

**Updated membership matrix:**

| Instance | C1 | C2 |
|---|---|---|
| 1 | 0.256 | 0.744 |
| 2 | 0.116 | 0.884 |
| 3 | 0.356 | 0.644 |
| 4 | 0.758 | 0.242 |
| 5 | 0.718 | 0.282 |

**Cluster membership:** Cluster 1 = {4, 5}, Cluster 2 = {1, 2, 3}

*(Full step-by-step distance calculations shown in the 17th Batch solution document, Q6c.)*

#### b) BOW / TF-IDF feature matrix — cat/dog corpus

*(Question numbering repeats "5.a." here in the original paper — treating as Q7's second half; also, only 3 documents are given despite the text saying "four".)*

Corpus:
- Doc1: "The cat is on the mat."
- Doc2: "The dog is chasing the cat."
- Doc3: "The dog and the cat are playing together."

**Bag-of-Words (raw counts):**

| Term | Doc1 | Doc2 | Doc3 |
|---|---|---|---|
| and | 0 | 0 | 1 |
| are | 0 | 0 | 1 |
| cat | 1 | 1 | 1 |
| chasing | 0 | 1 | 0 |
| dog | 0 | 1 | 1 |
| is | 1 | 1 | 0 |
| mat | 1 | 0 | 0 |
| on | 1 | 0 | 0 |
| playing | 0 | 0 | 1 |
| the | 2 | 2 | 2 |
| together | 0 | 0 | 1 |

**TF-IDF** (tf × log₁₀(N/df), N=3):

| Term | Doc1 | Doc2 | Doc3 |
|---|---|---|---|
| and | 0.000 | 0.000 | 0.477 |
| are | 0.000 | 0.000 | 0.477 |
| cat | 0.000 | 0.000 | 0.000 |
| chasing | 0.000 | 0.477 | 0.000 |
| dog | 0.000 | 0.176 | 0.176 |
| is | 0.176 | 0.176 | 0.000 |
| mat | 0.477 | 0.000 | 0.000 |
| on | 0.477 | 0.000 | 0.000 |
| playing | 0.000 | 0.000 | 0.477 |
| the | 0.000 | 0.000 | 0.000 |
| together | 0.000 | 0.000 | 0.477 |

*Note: "cat" and "the" both get a TF-IDF of 0 because they appear in all 3 documents (idf = log(3/3) = 0), correctly marking them as non-discriminative for distinguishing between these documents.*

#### c) Ensemble learning strategies — *(same as 16th Batch Q3a)*

Bagging, Boosting, Stacking, and Voting — see the 16th Batch solution document, Q3a, for full descriptions.

---

### Question 6 (second instance in the original paper) — Neural Network Design

#### a) What is a neural network? Design: 4 input, 1 hidden layer (3 neurons), 1 output

*(Identical to 17th Batch Q7a — see that document for the full architecture diagram and explanation.)*

#### b) NN with 3 input, 4 hidden, 2 output units, sigmoid activation

⚠️ **I need to double-check this one with you.** The specific weight and bias values for this question were embedded as an image in the original document rather than as text, and I want to make sure I use the exact numbers rather than guess at values I can't fully confirm from the image. Could you share the specific weight matrix and bias values (as text or a clearer image), and I'll compute the full forward pass (net inputs, hidden layer activations, and final output activations) for you right away?

**The general method**, once you provide the numbers: For each hidden neuron j: `h_j = sigmoid(Σ(w_ij × x_i) + b_j)` using the 3 inputs; then for each output neuron k: `y_k = sigmoid(Σ(w_jk × h_j) + b_k)` using the 4 hidden layer outputs.

---

*End of solutions — Questions 1–7 (Q6b's second part pending weight values), 14th Batch (2024) exam paper.*

---

# 13th Batch (2023)

### Full Solutions — MSc. in CSE (P), 2nd Semester Final Exam 2023 (13th Batch)

---

### Question 1

#### a) Min-max normalization: X=75, min=60, max=90

v' = (X − min) / (max − min) = (75 − 60) / (90 − 60) = 15/30 = **0.5**

#### b) KNN (k=3) — predict class of (Blue, Small, Circle)

Using Hamming/Manhattan distance (mismatch count) on categorical features:

| Instance | F1 | F2 | F3 | Class | Distance to (Blue,Small,Circle) |
|---|---|---|---|---|---|
| 1 | Red | Small | Circle | Class 0 | (1)+(0)+(0) = **1** |
| 5 | Blue | Medium | Circle | Class 1 | (0)+(1)+(0) = **1** |
| 2 | Blue | Medium | Square | Class 1 | (0)+(1)+(1) = **2** |
| 4 | Red | Small | Square | Class 1 | (1)+(0)+(1) = **2** |
| 3 | Green | Large | Triangle | Class 0 | (1)+(1)+(1) = **3** |
| 6 | Green | Large | Triangle | Class 0 | (1)+(1)+(1) = **3** |

**3 Nearest Neighbors:** Instance 1 (Class 0, d=1), Instance 5 (Class 1, d=1), then a tie at d=2 between Instance 2 and Instance 4 (both Class 1) — taking Instance 2 as the next nearest in data order.

Neighbors = {Class 0, Class 1, Class 1} → **Predicted Class = Class 1** (majority: 2 out of 3)

---

### Question 2

#### a) Confusion Matrix, Precision, Recall, F1 (COVID prediction)

True: [Pos, Neg, Pos, Pos, Neg, Pos, Neg, Neg, Pos, Pos]
Predicted: [Pos, Pos, Pos, Neg, Neg, Pos, Neg, Neg, Pos, Pos]

Positive class = Positive:

| # | True | Predicted | Result |
|---|------|-----------|--------|
| 1 | Positive | Positive | TP |
| 2 | Negative | Positive | FP |
| 3 | Positive | Positive | TP |
| 4 | Positive | Negative | FN |
| 5 | Negative | Negative | TN |
| 6 | Positive | Positive | TP |
| 7 | Negative | Negative | TN |
| 8 | Negative | Negative | TN |
| 9 | Positive | Positive | TP |
| 10 | Positive | Positive | TP |

**Counts:** TP = 5, FP = 1, FN = 1, TN = 3

**Confusion Matrix:**

|  | Predicted: Positive | Predicted: Negative |
|---|---|---|
| **Actual: Positive** | 5 | 1 |
| **Actual: Negative** | 1 | 3 |

- **Precision** = 5/(5+1) = **0.833**
- **Recall** = 5/(5+1) = **0.833**
- **F1-score** = 2×(0.833×0.833)/(0.833+0.833) = **0.833**

#### b) Chi-square test — Outlook/Wind vs Play Tennis

Data: Play Tennis Yes=3, No=3, Total=6

**Outlook vs Play Tennis:**

| | Yes | No |
|---|---|---|
| Sunny | 1 | 1 |
| Cloudy | 1 | 1 |
| Overcast | 1 | 1 |

Every category is split exactly 50/50, matching the overall Yes/No ratio exactly → **χ²(Outlook) = 0** (no association at all)

**Wind vs Play Tennis:**

| | Yes | No |
|---|---|---|
| Clear | 1 | 1 |
| Rainy | 0 | 2 |
| Foggy | 2 | 0 |

Expected (each row total=2, so E=1 for each cell):
χ² = (1−1)²/1 + (1−1)²/1 + (0−1)²/1 + (2−1)²/1 + (2−1)²/1 + (0−1)²/1 = 0+0+1+1+1+1 = **4.0**

**Conclusion: Wind is the most significant feature** (χ² = 4.0 vs. 0 for Outlook) — Rainy always means "No" and Foggy always means "Yes" in this data, a perfect split that Outlook does not show.

---

### Question 3

#### a) Classification vs Regression

| Aspect | Classification | Regression |
|---|---|---|
| Output | Discrete class label | Continuous numeric value |
| Example | Email spam/not spam | House price prediction |
| Metrics | Accuracy, Precision, Recall, F1 | MSE, RMSE, R² |
| Algorithms | Logistic Regression, SVM, Decision Tree, KNN | Linear Regression, Polynomial Regression, SVR |

#### b) Linear Regression: predict fuel efficiency at engine size=1800cc

Engine Size = [1000,1500,2000,2500,3000], Fuel Efficiency = [18,15,12,10,8]

x̄ = 2000, ȳ = 12.6

| x−x̄ | y−ȳ | product | (x−x̄)² |
|---|---|---|---|
| −1000 | 5.4 | −5400 | 1,000,000 |
| −500 | 2.4 | −1200 | 250,000 |
| 0 | −0.6 | 0 | 0 |
| 500 | −2.6 | −1300 | 250,000 |
| 1000 | −4.6 | −4600 | 1,000,000 |
| **Σ** | | **−12,500** | **2,500,000** |

b₁ = −12500/2500000 = **−0.005**
b₀ = 12.6 − (−0.005)(2000) = 12.6 + 10 = **22.6**

**Regression equation: Fuel Efficiency = 22.6 − 0.005 × Engine Size**

At Engine Size = 1800cc: FE = 22.6 − 0.005(1800) = 22.6 − 9.0 = **13.6 km/l**

#### c) How SVM parameters impact model performance

- **C (regularization):** controls the margin-vs-error trade-off. Small C → wider margin, more misclassification tolerance (higher bias, lower variance). Large C → narrow margin, fits training data tightly (higher variance, overfitting risk).
- **Kernel type:** determines the shape of the decision boundary. Linear kernel for linearly separable data; RBF/polynomial for complex, non-linear boundaries.
- **Gamma (RBF/poly kernels):** controls the influence radius of individual points. Low gamma → smoother, more generalized boundary. High gamma → tightly fit boundary that can overfit.
- **Degree (polynomial kernel):** higher degree → more complex/flexible decision boundary, but higher overfitting risk and computational cost.

In a specific classification problem, these parameters are tuned together (typically via grid search + cross-validation) since they jointly determine model flexibility, generalization ability, and training time.

---

### Question 4

#### a) Standard ensemble learning strategies

1. **Bagging** — parallel training on bootstrap samples, combined via voting/averaging (reduces variance; e.g., Random Forest).
2. **Boosting** — sequential training where each model corrects prior errors (reduces bias; e.g., AdaBoost, XGBoost).
3. **Stacking** — a meta-model learns to best combine outputs of multiple different base models.
4. **Voting** — majority vote (classification) or average (regression) across multiple independently trained models.

#### b) Why is feature selection important? Dimensions of it

**Importance:**
- **Reduces overfitting** by removing noisy/irrelevant features that the model could otherwise fit to spurious patterns.
- **Improves model performance/accuracy** by keeping only informative features.
- **Reduces training time and computational cost**, especially important for high-dimensional data.
- **Improves interpretability** — fewer features make the model easier to understand and explain.
- **Mitigates the curse of dimensionality**, where distance-based and statistical methods degrade as dimensions increase relative to sample size.

**Dimensions/approaches to feature selection:**
1. **Filter methods** — select features based on statistical measures independent of the model (e.g., correlation coefficient, Chi-square test, mutual information, variance threshold). Fast but ignores feature interactions.
2. **Wrapper methods** — evaluate feature subsets using the actual model's performance (e.g., Recursive Feature Elimination, forward/backward selection). More accurate but computationally expensive.
3. **Embedded methods** — feature selection is built into the model training process itself (e.g., LASSO regression's L1 penalty, tree-based feature importance in Random Forest/XGBoost). Balances accuracy and efficiency.

---

### Question 5

#### a) Age data: quartiles, five-number summary, boxplot, Q-Q plot

*Note: the age list in the original question appears to have a few values out of the stated "increasing order" (e.g., "35, 38, 38, 35, 36" isn't sorted) — likely a transcription/OCR artifact. Sorting the given 27 values first:*

Sorted: 13,15,16,16,19,20,20,21,22,22,25,25,25,25,30,33,33,35,35,36,38,38,40,45,46,52,70

**I. Q1 and Q3:**
Position (n+1)/4 = 7th value → **Q1 = 20**
Position 3(n+1)/4 = 21st value → **Q3 = 38**

**II. Five-number summary:** Min = 13, Q1 = 20, Median = 25, Q3 = 38, Max = 70

**III. Boxplot:**

```
   13         20      25        38                70
   |──────────┤███████│█████████┤──────────────────|
 Min          Q1     Median     Q3                Max
```

**IV. Q-Q plot vs Quantile plot:** A quantile plot shows the distribution of a single variable's data against its percentile ranks. A Q-Q (quantile-quantile) plot compares the quantiles of two datasets (or one dataset vs. a theoretical distribution like normal) against each other, to check if they share the same distribution shape.

#### b) Handling missing values — *(same as 15th Batch Q2b)*

- Ignore the tuple (if few affected rows)
- Fill manually (expert-driven, impractical at scale)
- Fill with a global constant (e.g., "Unknown")
- Fill with attribute mean/median
- Fill with the mean/median of the same class (class-conditional)
- Fill using the most probable value via regression/decision tree/predictive imputation (most sophisticated)

#### c) Normalizing {200, 300, 400, 600, 1000} — *(identical task to 16th Batch Q1d)*

- **Min-max [0,1]:** 0.000, 0.125, 0.250, 0.500, 1.000
- **Z-score** (μ=500, σ=316.23): −0.949, −0.632, −0.316, 0.316, 1.581
- **Z-score (MAD=240):** −1.250, −0.833, −0.417, 0.417, 2.083
- **Decimal scaling (÷10⁴):** 0.02, 0.03, 0.04, 0.06, 0.10

---

### Question 6

#### a) Difference between clustering and classification

**Classification** is a **supervised** learning task: the model learns from labeled training data (predefined classes) and predicts a discrete class label for new instances. **Clustering** is an **unsupervised** learning task: there are no predefined labels, and the algorithm groups data points into clusters based purely on similarity/distance, discovering structure rather than predicting a known category.

#### b) Soft clustering: k-means vs fuzzy c-means

**Fuzzy C-Means (FCM) represents soft clustering.** In k-means, each data point belongs entirely to exactly one cluster (hard assignment). In FCM, each point has a *degree of membership* (between 0 and 1) to every cluster simultaneously, summing to 1 across all clusters — allowing a point to partially belong to multiple clusters, which better reflects ambiguous or overlapping real-world groupings.

#### c) FCM clustering — 6 instances, m=2, one iteration

Data:

| Instance | X | Y | C1 | C2 |
|---|---|---|---|---|
| 1 | 1 | 6 | 0.8 | 0.2 |
| 2 | 2 | 5 | 0.9 | 0.1 |
| 3 | 3 | 8 | 0.7 | 0.3 |
| 4 | 4 | 4 | 0.3 | 0.7 |
| 5 | 5 | 7 | 0.5 | 0.5 |
| 6 | 6 | 9 | 0.2 | 0.8 |

**Step 1 — Cluster centers** (weighted by uᵢⱼ², m=2):

v1 = ( Σuᵢ₁²·xᵢ / Σuᵢ₁² , Σuᵢ₁²·yᵢ / Σuᵢ₁² ) = **(2.405, 6.155)**

v2 = ( Σuᵢ₂²·xᵢ / Σuᵢ₂² , Σuᵢ₂²·yᵢ / Σuᵢ₂² ) = **(4.855, 6.895)**

**Step 2 — Euclidean distances:**

| Instance | d(i, v1) | d(i, v2) |
|---|---|---|
| 1 | 1.414 | 3.958 |
| 2 | 1.224 | 3.427 |
| 3 | 1.938 | 2.160 |
| 4 | 2.681 | 3.018 |
| 5 | 2.729 | 0.179 |
| 6 | 4.584 | 2.396 |

**Step 3 — Updated membership matrix** (uᵢⱼ = 1/Σₖ(dᵢⱼ/dᵢₖ)²):

| Instance | C1 (updated) | C2 (updated) |
|---|---|---|
| 1 | 0.887 | 0.113 |
| 2 | 0.887 | 0.113 |
| 3 | 0.554 | 0.446 |
| 4 | 0.559 | 0.441 |
| 5 | 0.004 | 0.996 |
| 6 | 0.215 | 0.785 |

**Cluster membership after iteration 1:**
- **Cluster 1:** Instances 1, 2, 3, 4 (all with C1 membership > C2)
- **Cluster 2:** Instances 5, 6

---

### Question 7

#### a) K-means clustering (3 clusters) — *(identical task to 16th/15th/14th Batch)*

**I. Cluster centers after first round:**
- Cluster A: {A1} → **(2.0, 10.0)**
- Cluster B: {A3, B1, B2, B3, C2} → **(6.0, 6.0)**
- Cluster C: {A2, C1} → **(1.5, 3.5)**

**II. Final clusters (after convergence):**
- **Cluster A** = {A1, B1, C2} → center ≈ **(3.67, 9.0)**
- **Cluster B** = {A3, B2, B3} → center ≈ **(7.0, 4.33)**
- **Cluster C** = {A2, C1} → center = **(1.5, 3.5)**

#### b) Clustering algorithms comparison — *(identical to 17th/14th Batch)*

| Algorithm | Cluster Shapes | Key Parameters | Limitations |
|---|---|---|---|
| **k-means** | Spherical, convex | k | Sensitive to initial centroids/outliers; must pre-specify k |
| **k-medoids** | Spherical/convex | k | Robust to outliers but computationally expensive; doesn't scale well |
| **CLARA** | Spherical/convex | k, sample size | Depends on sample representativeness |
| **BIRCH** | Spherical, even-sized | Branching factor, threshold radius | Sensitive to data order; struggles with non-spherical clusters |
| **CHAMELEON** | Arbitrary shapes | k-NN graph size, interconnectivity/closeness thresholds | Computationally expensive; complex tuning |
| **DBSCAN** | Arbitrary shape | eps, minPts | Struggles with varying density; sensitive to parameters |

---

*End of solutions — Questions 1–7, 13th Batch (2023) exam paper.*

---

# 12th Batch (2023)

### Full Solutions — MSc. in CSE (P), 2nd Semester Final Exam 2023 (12th Batch)

---

### Question 1

#### a) Why is normalization important in data preprocessing?

Normalization scales numeric attributes to a common range, which is important because:
- **Prevents scale dominance:** Features with larger raw ranges (e.g., income in thousands vs. age in years) would otherwise dominate distance-based algorithms (KNN, K-means, SVM) and gradient-based training (neural networks) purely due to scale, not actual importance.
- **Speeds up convergence:** Gradient descent-based algorithms converge faster and more stably when features are on comparable scales.
- **Improves comparability:** Makes coefficients/weights more directly interpretable and comparable across features.

**Mechanisms of normalization:**
- **Min-max normalization:** rescales values to a fixed range (commonly [0,1]) using v' = (v−min)/(max−min).
- **Z-score (standard score) normalization:** rescales using the mean and standard deviation: v' = (v−μ)/σ, producing a distribution with mean 0 and std 1.
- **Z-score using Mean Absolute Deviation (MAD):** similar to z-score but uses MAD instead of standard deviation, making it more robust to outliers.
- **Decimal scaling:** moves the decimal point of values based on the maximum absolute value, i.e., v' = v/10^j, where j is the smallest integer such that max(|v'|) < 1.

#### b) Chi-square test for feature selection

Target = 3 Yes, 3 No.

**Feature 1 vs Target:**

| | Yes | No |
|---|---|---|
| A | 2 | 1 |
| B | 1 | 2 |

χ² = **0.667**

**Feature 2 vs Target:**

| | Yes | No |
|---|---|---|
| Yes | 3 | 0 |
| No | 0 | 3 |

χ² = **6.0** — a *perfect* split (Feature2=Yes always → Target=Yes; Feature2=No always → Target=No)

**Feature 3 vs Target:**

| | Yes | No |
|---|---|---|
| High | 1 | 1 |
| Low | 1 | 1 |
| Medium | 1 | 1 |

χ² = **0.0** (no association at all — perfectly balanced across every category)

**Conclusion: Feature 2 is by far the most relevant feature** (χ² = 6.0, a perfect predictor in this sample), followed distantly by Feature 1 (χ² = 0.667), while Feature 3 shows zero association with the target and should be dropped.

---

### Question 2

#### a) KNN Classification (k=3, Euclidean distance) — new instance (4,3)

| Point | (F1,F2) | Class | Distance to (4,3) |
|---|---|---|---|
| (4,2) | (4,2) | A | √(0+1) = **1.000** |
| (3,4) | (3,4) | A | √(1+1) = **1.414** |
| (2,3) | (2,3) | A | √(4+0) = **2.000** |
| (5,5) | (5,5) | B | √(1+4) = 2.236 |
| (6,4) | (6,4) | B | √(4+1) = 2.236 |
| (7,6) | (7,6) | B | √(9+9) = 4.243 |

**3 Nearest Neighbors:** (4,2)→A (d=1.0), (3,4)→A (d=1.414), (2,3)→A (d=2.0)

All 3 nearest neighbors are **Class A** → **Predicted class = A**

#### b) Intuition behind Support Vector Machines (SVM)

SVM's core intuition is to find the **hyperplane that best separates two classes with the maximum possible margin** — the largest distance between the hyperplane and the nearest data points from either class (called **support vectors**). Rather than just finding *any* separating boundary, SVM specifically maximizes this margin because a wider margin tends to generalize better to unseen data.

**How it works:**
1. Among all possible separating hyperplanes, SVM identifies the one that maximizes the distance to the closest points of each class.
2. Only the closest points (support vectors) actually influence the position of the hyperplane — points far from the boundary don't matter.
3. For data that isn't linearly separable, SVM uses **kernel functions** (e.g., RBF, polynomial) to implicitly map the data into a higher-dimensional space where a linear separator does exist — this is known as the "kernel trick."
4. A regularization parameter **C** controls the trade-off between maximizing the margin and tolerating misclassified points (a "soft margin" for real-world noisy data).

---

### Question 3

#### a) Min-max normalization to range [1,10]: value=850, original range 800–1000

v' = ((v−min)/(max−min)) × (new_max−new_min) + new_min
= ((850−800)/(1000−800)) × (10−1) + 1
= (50/200) × 9 + 1
= 0.25 × 9 + 1
= 2.25 + 1 = **3.25**

#### b) What is an outlier? Find the outlier in the batsman's runs

**An outlier** is a data point that deviates significantly from the rest of the observations in a dataset, often indicating measurement error, rare events, or genuine anomalies.

Runs: 21, 14, 26, 8, 12, 12, 14, 76, 28, 20, 32, 38

Using the **IQR method**:
- Q1 = 13.5, Q3 = 29.0, IQR = Q3−Q1 = 15.5
- Lower bound = Q1 − 1.5×IQR = 13.5 − 23.25 = **−9.75**
- Upper bound = Q3 + 1.5×IQR = 29.0 + 23.25 = **52.25**

Any value below −9.75 or above 52.25 is an outlier. **76 is the only outlier** (it's far above the upper bound of 52.25).

*(This is confirmed by z-score too: 76 has a z-score of ≈2.76 standard deviations from the mean of 25.08, clearly the most extreme value in the dataset.)*

#### c) Architecture of a typical data warehouse

A typical **data warehouse architecture** consists of the following layers:

```
┌─────────────────────────────────────────────────────────┐
│  Data Sources (operational DBs, external files, OLTP)    │
└───────────────────────┬───────────────────────────────────┘
                         │ ETL (Extract, Transform, Load)
                         ▼
┌─────────────────────────────────────────────────────────┐
│              Data Staging Area (temporary storage        │
│              for cleaning/transformation before loading) │
└───────────────────────┬───────────────────────────────────┘
                         ▼
┌─────────────────────────────────────────────────────────┐
│         Data Warehouse (central repository — often       │
│         modeled with star/snowflake schema, fact and      │
│         dimension tables)                                 │
└───────────────────────┬───────────────────────────────────┘
                         ▼
              ┌──────────┴──────────┐
              ▼                     ▼
     ┌────────────────┐    ┌─────────────────┐
     │  Data Marts     │    │  OLAP Engine     │
     │  (subject-      │    │  (multidimensional│
     │  specific        │    │  analysis, cube   │
     │  subsets)        │    │  operations)       │
     └────────┬────────┘    └────────┬─────────┘
              └───────────┬───────────┘
                          ▼
              ┌───────────────────────┐
              │  Front-End Tools       │
              │  (reporting, BI        │
              │  dashboards, data      │
              │  mining tools)         │
              └───────────────────────┘
```

**Explanation:**
1. **Data Sources** — operational/transactional databases and external data feed into the warehouse.
2. **ETL process** — data is Extracted from sources, Transformed (cleaned, standardized, aggregated), and Loaded into the warehouse.
3. **Data Staging Area** — a temporary holding area where raw extracted data is cleaned and transformed before being loaded into the warehouse proper.
4. **Data Warehouse** — the central, subject-oriented, integrated, time-variant, and non-volatile repository, typically organized with fact tables (measures) and dimension tables (context) in a star or snowflake schema.
5. **Data Marts** — smaller, department/subject-specific subsets of the warehouse (e.g., a Sales data mart, a Finance data mart).
6. **OLAP Engine** — supports multidimensional analysis (drill-down, roll-up, slice, dice) over the warehouse/marts.
7. **Front-End Tools** — reporting, dashboards, and data mining tools that business users and analysts interact with to derive insights.

---

### Question 4

#### a) Confusion Matrix, Accuracy, Precision, Recall, F1 (Diabetes prediction)

True: [1,0,1,1,0,1,0,0,1,1]
Predicted: [1,1,1,0,0,1,0,0,1,1]

| | Predicted: 1 | Predicted: 0 |
|---|---|---|
| **Actual: 1** | TP = 5 | FN = 1 |
| **Actual: 0** | FP = 1 | TN = 3 |

- **Accuracy** = (5+3)/10 = **0.80**
- **Precision** = 5/(5+1) = **0.833**
- **Recall** = 5/(5+1) = **0.833**
- **F1-score** = 2×(0.833×0.833)/(0.833+0.833) = **0.833**

#### b) Linear regression: predict house price at 1800 sq. ft.

House Size = [1000,1500,2000,2500,3000], Price = [200,300,400,500,600]

This data is **perfectly linear**: each 500 sq. ft. increase corresponds to exactly a $100k price increase.

x̄=2000, ȳ=400; b₁ = Σ(x−x̄)(y−ȳ)/Σ(x−x̄)² = **0.2**; b₀ = 400 − 0.2(2000) = **0**

**Regression equation: Price = 0.2 × Size**

At Size = 1800 sq. ft.: Price = 0.2 × 1800 = **$360,000 (360 in $1000s)**

---

### Question 5

#### a) Collaborative filtering — recommend movies to User 1

Ratings matrix:

| | Movie 1 | Movie 2 | Movie 3 | Movie 4 | Movie 5 |
|---|---|---|---|---|---|
| User 1 | 4 | – | 3 | – | 5 |
| User 2 | – | 2 | 4 | 3 | – |
| User 3 | 3 | 1 | – | 4 | 2 |
| User 4 | – | 3 | 2 | – | 4 |
| User 5 | 5 | – | 4 | 2 | 3 |

**Approach (user-based collaborative filtering):**

1. **Compute similarity** between User 1 and every other user, based only on movies they've *both* rated (using cosine similarity or Pearson correlation).
2. **Identify the most similar users** ("neighbors") to User 1.
3. **Predict User 1's missing ratings** (Movie 2, Movie 4) as a similarity-weighted average of the ratings given by similar users for those movies.
4. **Recommend** the movie(s) with the highest predicted rating that User 1 hasn't already rated.

**Step 1 — Similarity to User 1** (cosine similarity on commonly-rated movies):

| User | Common movies rated with User 1 | Cosine similarity |
|---|---|---|
| User 2 | Movie 3 only: (3,4) | 1.000 |
| User 3 | Movie 1, Movie 5: (4,3),(5,2) | 0.953 |
| User 4 | Movie 3, Movie 5: (3,2),(5,4) | 0.997 |
| User 5 | Movie 1, Movie 3, Movie 5: (4,5),(3,4),(5,3) | 0.940 |

**Step 2 — Predict missing ratings** using weighted average: predicted = Σ(sim × rating) / Σ(sim), over users who rated that movie:

- **Movie 2** (rated by User2=2, User3=1, User4=3): predicted ≈ **2.01**
- **Movie 4** (rated by User2=3, User3=4, User5=2): predicted ≈ **3.00**

**Recommendation:** Comparing User 1's actual ratings (Movie1=4, Movie3=3, Movie5=5) with the predicted ones (Movie2≈2.01, Movie4≈3.00), **Movie 4 (predicted ≈3.00) is the better recommendation** of the two unrated movies, since it's predicted higher than Movie 2 — though neither predicted rating is as high as User 1's existing favorites (Movie 1 and Movie 5), so neither is a strong recommendation on an absolute scale.

#### b) Steps to handle missing values in a dataset

1. **Detect** missing values (check for nulls, blanks, sentinel values like "-", "?", "N/A").
2. **Analyze the pattern** of missingness (missing completely at random, missing at random, or missing not at random) to choose an appropriate strategy.
3. **Choose a handling method:**
   - Ignore/drop the tuple (if few rows affected).
   - Fill manually (expert-driven, only for small datasets).
   - Fill with a global constant (e.g., "Unknown", 0).
   - Fill with the attribute mean/median (numeric) or mode (categorical).
   - Fill with the mean/median of the same class (class-conditional imputation).
   - Predict the missing value using regression, KNN imputation, or a decision tree.
4. **Validate** the imputed data doesn't introduce bias or distort the distribution.
5. **Document** the imputation approach for reproducibility and transparency.

---

### Question 6

#### a) Hard clustering vs Soft clustering

| Aspect | Hard Clustering | Soft Clustering |
|---|---|---|
| Membership | Each point belongs to exactly **one** cluster | Each point has a **degree of membership** (0 to 1) across all clusters |
| Example algorithm | K-means | Fuzzy C-Means (FCM) |
| Output | A single cluster label per point | A membership vector per point (summing to 1) |
| Best suited for | Well-separated, distinct groups | Overlapping/ambiguous groups where boundaries aren't crisp |

#### b) FCM clustering — 6 instances, m=2, one iteration — *(identical dataset to 13th Batch Q6c)*

**Cluster centers:** v1 = (2.405, 6.155), v2 = (4.855, 6.895)

**Updated membership matrix:**

| Instance | C1 | C2 |
|---|---|---|
| 1 | 0.887 | 0.113 |
| 2 | 0.887 | 0.113 |
| 3 | 0.554 | 0.446 |
| 4 | 0.559 | 0.441 |
| 5 | 0.004 | 0.996 |
| 6 | 0.215 | 0.785 |

**Cluster membership:** Cluster 1 = {1,2,3,4}, Cluster 2 = {5,6}

*(Full distance calculations shown in the 13th Batch solution document, Q6c.)*

#### c) Label encoding — Car Type and Fuel Type

Car Type: [Sedan, SUV, Hatchback, SUV, Crossover]
Fuel Type: [Petrol, Diesel, Petrol, Petrol, Diesel]

Assigning integer codes in order of first appearance:

**Car Type encoding:** Sedan=0, SUV=1, Hatchback=2, Crossover=3

**Fuel Type encoding:** Petrol=0, Diesel=1

| Car Type | Car Type (encoded) | Fuel Type | Fuel Type (encoded) |
|---|---|---|---|
| Sedan | 0 | Petrol | 0 |
| SUV | 1 | Diesel | 1 |
| Hatchback | 2 | Petrol | 0 |
| SUV | 1 | Petrol | 0 |
| Crossover | 3 | Diesel | 1 |

*Caution: Label encoding introduces an artificial ordinal relationship between categories (implying Crossover(3) > Sedan(0)), which can mislead distance-based or linear models — one-hot encoding is often preferable for nominal features like these unless using tree-based models, which aren't affected by this issue.*

---

### Question 7

#### a) Types of Hierarchical Clustering

1. **Agglomerative (bottom-up)** — starts with each data point as its own cluster, then repeatedly merges the two closest clusters until only one cluster (or a stopping criterion) remains.
2. **Divisive (top-down)** — starts with all data points in a single cluster, then repeatedly splits clusters into smaller ones until each point is its own cluster (or a stopping criterion is reached).

#### b) Agglomerative clustering — 6 points, show 3 iterations (single linkage)

Points: A1(4,6), A2(2,5), A3(9,3), A4(6,9), A5(7,5), A6(5,7)

**Initial pairwise distances (selected smallest):**
A1–A6 = 1.414, A1–A2 = 2.236, A4–A6 = 2.236, A3–A5 = 2.828, A5–A6 = 2.828, A1–A5 = 3.162, A1–A4 = 3.606, A2–A6 = 3.606, A4–A5 = 4.123

**Iteration 1:** Smallest distance = A1–A6 = **1.414** → merge into cluster **{A1, A6}**

Updated distances (single linkage — minimum to either member):
- {A1,A6}–A2 = min(2.236, 3.606) = 2.236
- {A1,A6}–A3 = min(5.831, 5.657) = 5.657
- {A1,A6}–A4 = min(3.606, 2.236) = 2.236
- {A1,A6}–A5 = min(3.162, 2.828) = 2.828

**Iteration 2:** Smallest distance = {A1,A6}–A2 = **2.236** (tied with {A1,A6}–A4, resolved by taking A2 first) → merge into cluster **{A1, A2, A6}**

Updated distances:
- {A1,A2,A6}–A3 = min(5.657, 7.280) = 5.657
- {A1,A2,A6}–A4 = min(2.236, 5.657) = 2.236
- {A1,A2,A6}–A5 = min(2.828, 5.000) = 2.828

**Iteration 3:** Smallest distance = {A1,A2,A6}–A4 = **2.236** → merge into cluster **{A1, A2, A4, A6}**

**State after 3 iterations:**
- Cluster: **{A1, A2, A4, A6}**
- Remaining unmerged singletons: **A3**, **A5**

(Continuing further would next merge A3–A5 at distance 2.828, then merge that pair into the main cluster, eventually forming one single cluster — but only 3 iterations were requested.)

---

*End of solutions — Questions 1–7, 12th Batch (2023) exam paper.*

---


# Appendix: Key Formulas & Theoretical Reference

This appendix summarizes the core mathematical formulas and theoretical concepts used repeatedly across the six papers, for quick reference.

## 1. Classification Evaluation Metrics

Given a confusion matrix with True Positives (TP), False Positives (FP), False Negatives (FN), True Negatives (TN):

- **Accuracy** = (TP + TN) / (TP + FP + FN + TN)
- **Precision** = TP / (TP + FP) — *"Of everything predicted positive, how much was actually positive?"*
- **Recall (Sensitivity)** = TP / (TP + FN) — *"Of everything actually positive, how much did we correctly find?"*
- **Specificity** = TN / (TN + FP) — *"Of everything actually negative, how much did we correctly identify?"*
- **F1-score** = 2 × (Precision × Recall) / (Precision + Recall) — harmonic mean of precision and recall, balances both.

**Theory:** Accuracy alone is misleading on imbalanced datasets, since a trivial "always predict majority class" model can score high accuracy while being useless. Precision/Recall/F1 expose per-class performance that accuracy hides.

## 2. Chi-Square (χ²) Test for Feature Significance

For a contingency table of a categorical feature vs. a categorical target:

χ² = Σ [(O − E)² / E]

where **O** = observed frequency in each cell, and **E** = expected frequency = (row total × column total) / grand total, assuming no association (independence) between the feature and target.

**Theory:** A **higher χ² statistic** indicates a **stronger deviation from independence**, i.e., a stronger association between the feature and the target — making that feature more useful for prediction. The statistic is compared against a critical value from the χ² distribution (with degrees of freedom = (rows−1)×(columns−1)) at a chosen significance level (e.g., α=0.05) to determine formal statistical significance; however, even below the critical threshold, relative comparison of χ² values across features indicates *relative* predictive strength.

## 3. Simple Linear Regression

Model: **ŷ = b₀ + b₁x**

- **Slope:** b₁ = Σ(xᵢ−x̄)(yᵢ−ȳ) / Σ(xᵢ−x̄)²
- **Intercept:** b₀ = ȳ − b₁x̄

**Mean Squared Error (MSE)** = (1/n) Σ(yᵢ − ŷᵢ)² — measures average squared prediction error on a test set; lower is better.

**Theory:** Linear regression finds the line that minimizes the sum of squared residuals (Ordinary Least Squares) between predicted and actual values, assuming a linear relationship between the independent and dependent variables.

## 4. K-Nearest Neighbors (KNN)

**Distance metrics:**
- **Euclidean distance** (numeric features): d(p,q) = √Σ(pᵢ−qᵢ)²
- **Manhattan/Hamming distance** (categorical features, mismatch count): d(p,q) = Σ|pᵢ−qᵢ| (for categorical: 0 if same, 1 if different)

**Procedure:** Find the *k* training points nearest to the query point; predict the majority class among those *k* neighbors (classification) or the average value (regression).

**Theory:** KNN is a "lazy," instance-based learner — it doesn't build an explicit model during training, but instead defers all computation to prediction time, directly comparing the new instance to stored training examples. Choice of *k* controls the bias-variance trade-off: small *k* → low bias/high variance (sensitive to noise); large *k* → high bias/low variance (smoother, more generalized boundary).

## 5. K-Means Clustering

**Objective:** Partition *n* points into *k* clusters minimizing within-cluster variance:

Minimize Σₖ Σ(x∈Cₖ) ||x − μₖ||²

**Algorithm:**
1. Initialize *k* cluster centers (centroids).
2. **Assign** each point to its nearest centroid (by Euclidean distance).
3. **Update** each centroid as the mean of all points assigned to it.
4. Repeat steps 2–3 until assignments no longer change (convergence).

**Theory:** K-means is a **hard clustering** algorithm — each point belongs to exactly one cluster. It's sensitive to the initial choice of centroids (can converge to different local optima) and assumes roughly spherical, similarly-sized clusters; it also requires *k* to be specified in advance.

## 6. Fuzzy C-Means (FCM) Clustering

**Membership update rule** (with fuzziness parameter *m*, typically m=2):

uᵢⱼ = 1 / Σₖ ( dᵢⱼ / dᵢₖ )^(2/(m−1))

**Cluster center update:**

vⱼ = ( Σᵢ uᵢⱼᵐ · xᵢ ) / ( Σᵢ uᵢⱼᵐ )

where dᵢⱼ is the distance from point *i* to cluster center *j*.

**Theory:** FCM is a **soft/fuzzy clustering** algorithm — each point has a graded membership (between 0 and 1, summing to 1 across all clusters) in *every* cluster simultaneously, rather than a single hard assignment. This better models real-world data where cluster boundaries are ambiguous or overlapping. The parameter *m* controls the degree of fuzziness (m=1 approaches hard clustering; larger *m* produces fuzzier memberships).

## 7. Hierarchical (Agglomerative) Clustering

**Single-linkage distance** between two clusters A and B: d(A,B) = min over all a∈A, b∈B of d(a,b)

**Procedure:** Start with every point as its own cluster; repeatedly merge the two closest clusters (by the chosen linkage criterion) until one cluster remains (or a stopping criterion is met); the merge history forms a **dendrogram**.

**Theory:** Unlike k-means, hierarchical clustering doesn't require pre-specifying the number of clusters — instead, the dendrogram can be "cut" at any height to yield a chosen number of clusters. Besides single-linkage (nearest neighbor), other common linkage criteria include complete-linkage (farthest neighbor) and average-linkage.

## 8. TF-IDF (Term Frequency–Inverse Document Frequency)

**TF-IDF(t, d) = tf(t,d) × idf(t)**

- **tf(t,d)** = raw count (or frequency) of term *t* in document *d*
- **idf(t) = log(N / df(t))**, where N = total number of documents, df(t) = number of documents containing term *t*

**Theory:** TF-IDF weights terms by how frequently they appear in a specific document (tf) *offset* by how common they are across the whole corpus (idf) — a term appearing in every document (like "is" or "the") gets idf=0, correctly identifying it as non-discriminative, while a term unique to one document gets a high idf, marking it as distinctive/important for that document.

## 9. Ensemble Learning Strategies

- **Bagging (Bootstrap Aggregating):** parallel training on bootstrap samples, combined by voting/averaging → reduces **variance** (e.g., Random Forest).
- **Boosting:** sequential training where each model corrects the errors of previous ones → reduces **bias** (e.g., AdaBoost, XGBoost, Gradient Boosting).
- **Stacking:** a meta-model learns to optimally combine the outputs of multiple different base models.
- **Voting:** simple majority vote (classification) or averaging (regression) across independently trained models, without a formal meta-learner.

**Theory:** Ensembles exploit the idea that combining multiple "weak" or diverse models reduces overall error more than any single model alone, by averaging out individual mistakes (bagging) or focusing sequentially on hard cases (boosting).

## 10. Support Vector Machines (SVM)

**Core idea:** find the hyperplane that maximizes the margin (distance) between the two classes' nearest points (**support vectors**).

**Key hyperparameters:**
- **C** — regularization; controls margin-width vs. misclassification tolerance trade-off.
- **Kernel** (linear, polynomial, RBF, sigmoid) — transforms data into higher dimensions to handle non-linear separability (the "kernel trick").
- **Gamma (γ)** — controls the influence radius of individual points in RBF/polynomial kernels.

**Theory:** A wider margin generally generalizes better to unseen data; only the support vectors (points closest to the boundary) influence the final decision boundary — all other points are irrelevant to the model once trained.

## 11. Data Normalization Techniques

- **Min-max normalization:** v' = (v−min)/(max−min) [× (new_max−new_min) + new_min, if rescaling to a custom range]
- **Z-score normalization:** v' = (v−μ)/σ
- **Z-score with Mean Absolute Deviation (MAD):** v' = (v−μ)/MAD, more robust to outliers than standard deviation
- **Decimal scaling:** v' = v/10ʲ, where *j* is the smallest integer such that all scaled values have absolute value < 1

**Theory:** Normalization prevents features with larger numeric ranges from dominating distance-based algorithms (KNN, K-means, SVM) or slowing gradient-based training purely due to scale rather than actual importance.

## 12. Neural Networks (Forward Propagation)

For a layer with weight matrix **W**, bias vector **b**, and activation function *f*:

**output = f(W · input + b)**

Common activation: **Sigmoid** f(x) = 1/(1+e⁻ˣ), squashes output to (0,1), commonly used for binary classification outputs.

**Theory:** A neural network stacks multiple such layers, allowing it to learn increasingly abstract, non-linear representations of the input. **Forward propagation** computes the prediction; **backpropagation** (using the chain rule) computes gradients of the loss with respect to each weight, which are then used by gradient descent to update the weights during training.

---

*End of Master Compendium — CSE-5209, 17th through 12th Batch, Jagannath University.*
