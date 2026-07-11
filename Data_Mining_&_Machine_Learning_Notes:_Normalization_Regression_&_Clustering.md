# Data Mining & Machine Learning Notes: Normalization, Regression, and Clustering

A complete beginner-to-advanced reference following textbook order: **Data Preprocessing → Linear Regression → Clustering (K-Means & Fuzzy C-Means)**. Every formula is broken down piece by piece, and every numerical example is solved step by step.

---

## Table of Contents

- [Part 1: Data Normalization & Standardization](#part-1-data-normalization--standardization)
- [Part 2: Linear Regression](#part-2-linear-regression)
- [Part 3: Foundations of Clustering](#part-3-foundations-of-clustering)
- [Part 4: What is Clustering?](#part-4-what-is-clustering)
- [Part 5: Types of Clustering](#part-5-types-of-clustering)
- [Part 6: Hard vs Fuzzy Clustering](#part-6-hard-vs-fuzzy-clustering)
- [Part 7: K-Means Clustering](#part-7-k-means-clustering)
- [Part 8: Fuzzy C-Means (FCM)](#part-8-fuzzy-c-means-fcm)
- [Part 9: K-Means vs FCM — Comparison](#part-9-k-means-vs-fcm--comparison)
- [Part 10: Exam Revision Notes](#part-10-exam-revision-notes)
- [What to Learn Next](#what-to-learn-next)

---

## Part 1: Data Normalization & Standardization

### 1.1 Why Do We Normalize Data?

In easy words: real datasets often mix features with very different scales. Height might range `152–178` (cm) while weight ranges `47–72` (kg), or in another dataset one column might be `200–1000` while another is `0–1`. Many algorithms (K-Means, KNN, gradient descent, regression with multiple features) are sensitive to scale — a feature with bigger raw numbers can unfairly dominate distance or error calculations.

**Normalization / Standardization** rescales features onto a common footing so every feature contributes fairly.

There are three common techniques:

1. **Min-Max Normalization** — squeezes data into a fixed range, usually `[0, 1]`
2. **Z-Score Normalization (Standard Deviation)** — centers data around 0 using the mean and standard deviation
3. **Z-Score Normalization (Mean Absolute Deviation / MAD)** — same idea as z-score, but uses a more outlier-resistant spread measure

We'll learn the theory and formula for each, then solve a full worked example using:

```
Dataset: 200, 300, 400, 600, 1000
```

---

### 1.2 Min-Max Normalization

#### Theory (Easy Words)

Min-Max normalization stretches or squeezes your data so that the **smallest value becomes 0** and the **largest value becomes 1**. Everything else lands proportionally in between.

#### Formula

$$X' = \frac{X - X_{min}}{X_{max} - X_{min}}$$

**Breaking it down:**

| Symbol | Meaning |
|---|---|
| $X$ | The original value |
| $X_{min}$ | The smallest value in the dataset |
| $X_{max}$ | The largest value in the dataset |
| $X'$ | The normalized value (always between 0 and 1) |

**Logic:** `(X − min)` tells you how far above the minimum your value is. Dividing by `(max − min)` — the full range — converts that distance into a fraction of the total spread.

#### Step-by-Step Example

Dataset: `200, 300, 400, 600, 1000`

**Step 1 — Find min and max:**
```
Xmin = 200
Xmax = 1000
Range = Xmax − Xmin = 1000 − 200 = 800
```

**Step 2 — Apply the formula to each value:**

| X | Calculation | X' (Min-Max) |
|---:|---|---:|
| 200 | (200−200)/800 | **0.000** |
| 300 | (300−200)/800 | **0.125** |
| 400 | (400−200)/800 | **0.250** |
| 600 | (600−200)/800 | **0.500** |
| 1000 | (1000−200)/800 | **1.000** |

**Notice:** the minimum always becomes 0, the maximum always becomes 1, and everything else is a proportion in between.

---

### 1.3 Z-Score Normalization (Using Standard Deviation)

#### Theory (Easy Words)

Z-score normalization (also called **standardization**) tells you *how many standard deviations away from the mean* a value is. Instead of squeezing into `[0,1]`, values typically land somewhere around `-2` to `+2`, with **0 meaning "exactly average."**

#### Formula

$$Z = \frac{X - \mu}{\sigma}$$

**Breaking it down:**

| Symbol | Meaning | Formula |
|---|---|---|
| $X$ | The original value | — |
| $\mu$ (mu) | The mean (average) of the dataset | $\mu = \dfrac{\sum X}{n}$ |
| $\sigma$ (sigma) | The standard deviation (spread of the data) | $\sigma = \sqrt{\dfrac{\sum (X-\mu)^2}{n}}$ |
| $Z$ | The z-score (how many standard deviations from the mean) | — |

**Logic:** `(X − μ)` measures the distance from the average (can be negative). Dividing by `σ` rescales that distance in units of "typical spread," so datasets with different scales become comparable.

#### Step-by-Step Example

Dataset: `200, 300, 400, 600, 1000`

**Step 1 — Calculate the mean (μ):**
```
μ = (200 + 300 + 400 + 600 + 1000) / 5 = 2500 / 5 = 500
```

**Step 2 — Calculate each deviation from the mean (X − μ):**

| X | X − μ |
|---:|---:|
| 200 | −300 |
| 300 | −200 |
| 400 | −100 |
| 600 | 100 |
| 1000 | 500 |

**Step 3 — Square each deviation, then average (this gives variance):**

| X | (X−μ)² |
|---:|---:|
| 200 | 90,000 |
| 300 | 40,000 |
| 400 | 10,000 |
| 600 | 10,000 |
| 1000 | 250,000 |

```
Sum of squared deviations = 90000+40000+10000+10000+250000 = 400,000
Variance = 400000 / 5 = 80,000
```

**Step 4 — Take the square root of variance to get standard deviation (σ):**
```
σ = √80,000 ≈ 282.843
```

**Step 5 — Apply the z-score formula to each value:**

| X | Calculation | Z (std) |
|---:|---|---:|
| 200 | (200−500)/282.843 | **−1.061** |
| 300 | (300−500)/282.843 | **−0.707** |
| 400 | (400−500)/282.843 | **−0.354** |
| 600 | (600−500)/282.843 | **+0.354** |
| 1000 | (1000−500)/282.843 | **+1.768** |

**Notice:** values below the mean are negative, values above are positive, and `1000` (the outlier) gets pulled to the most extreme z-score.

---

### 1.4 Z-Score Normalization Using Mean Absolute Deviation (MAD)

#### Theory (Easy Words)

This is the *same idea* as z-score normalization, but instead of dividing by the standard deviation (which **squares** deviations and therefore reacts strongly to outliers), we divide by the **Mean Absolute Deviation (MAD)** — the plain average of *absolute* distances from the mean, with no squaring involved.

**Why does this matter?** Squaring a deviation makes big deviations count *much* more (e.g., a deviation of 500 becomes 250,000 when squared, dwarfing everything else). MAD avoids this by just taking the absolute value, making it **more robust to outliers**.

#### Formula

$$MAD = \frac{\sum |X - \mu|}{n}$$

$$Z_{MAD} = \frac{X - \mu}{MAD}$$

**Breaking it down:**

| Symbol | Meaning |
|---|---|
| $\lvert X - \mu \rvert$ | Absolute deviation — distance from the mean, ignoring sign |
| $MAD$ | Average of all the absolute deviations |
| $Z_{MAD}$ | The value's distance from the mean, measured in "MAD units" |

#### Step-by-Step Example

Dataset: `200, 300, 400, 600, 1000` (mean μ = 500, from before)

**Step 1 — Calculate absolute deviations |X − μ| (no squaring):**

| X | \|X − μ\| |
|---:|---:|
| 200 | 300 |
| 300 | 200 |
| 400 | 100 |
| 600 | 100 |
| 1000 | 500 |

**Step 2 — Average the absolute deviations to get MAD:**
```
MAD = (300 + 200 + 100 + 100 + 500) / 5 = 1200 / 5 = 240
```

**Step 3 — Apply the z-score (MAD) formula to each value:**

| X | Calculation | Z (MAD) |
|---:|---|---:|
| 200 | (200−500)/240 | **−1.250** |
| 300 | (300−500)/240 | **−0.833** |
| 400 | (400−500)/240 | **−0.417** |
| 600 | (600−500)/240 | **+0.417** |
| 1000 | (1000−500)/240 | **+2.083** |

---

### 1.5 Side-by-Side Comparison (All Three Methods)

Dataset: `200, 300, 400, 600, 1000`

| X | Min-Max | Z-Score (Std Dev) | Z-Score (MAD) |
|---:|---:|---:|---:|
| 200 | 0.000 | −1.061 | −1.250 |
| 300 | 0.125 | −0.707 | −0.833 |
| 400 | 0.250 | −0.354 | −0.417 |
| 600 | 0.500 | +0.354 | +0.417 |
| 1000 | 1.000 | +1.768 | +2.083 |

**Key observations:**
- **Min-Max** always bounds results to `[0, 1]` — good when you need a fixed, predictable range.
- **Z-Score (Std Dev)** centers data at 0, but standard deviation is **sensitive to outliers** (the value 1000 pulled the std dev up, which slightly *compresses* how extreme its z-score looks).
- **Z-Score (MAD)** also centers at 0, but MAD **doesn't over-react to outliers** — notice `1000` gets an even more extreme score (+2.083 vs +1.768) here, because MAD isn't inflated by squaring that outlier the way std dev is. This makes MAD-based z-scores a better choice when your data has extreme values you don't want to "hide."

| Method | Range | Sensitive to Outliers? | Best Used When |
|---|---|---|---|
| Min-Max | Fixed [0,1] | Yes (very) | You need bounded values, no major outliers |
| Z-Score (Std Dev) | Unbounded (~ -3 to +3) | Yes (moderately) | Data is roughly normal/bell-shaped |
| Z-Score (MAD) | Unbounded | No (robust) | Data has outliers you don't want to under-represent |

---

### 1.6 Applying Normalization to the Height & Weight Dataset

Now let's apply all three techniques to the actual **Training Dataset** we'll use for regression later:

```
Height (cm): 152, 158, 165, 172, 178
Weight (kg): 47, 51, 58, 66, 72
```

**Step 1 — Compute the required statistics for each column:**

| Statistic | Height | Weight |
|---|---:|---:|
| Min | 152 | 47 |
| Max | 178 | 72 |
| Mean (μ) | 165.000 | 58.800 |
| Std Dev (σ) | 9.338 | 9.239 |
| MAD | 8.000 | 8.160 |

**Step 2 — Height: all three normalizations**

| Height | Min-Max | Z (Std) | Z (MAD) |
|---:|---:|---:|---:|
| 152 | 0.000 | −1.392 | −1.625 |
| 158 | 0.231 | −0.750 | −0.875 |
| 165 | 0.500 | 0.000 | 0.000 |
| 172 | 0.769 | +0.750 | +0.875 |
| 178 | 1.000 | +1.392 | +1.625 |

**Step 3 — Weight: all three normalizations**

| Weight | Min-Max | Z (Std) | Z (MAD) |
|---:|---:|---:|---:|
| 47 | 0.00 | −1.277 | −1.446 |
| 51 | 0.16 | −0.844 | −0.956 |
| 58 | 0.44 | −0.087 | −0.098 |
| 66 | 0.76 | +0.779 | +0.882 |
| 72 | 1.00 | +1.429 | +1.618 |

**Step 4 — Apply the same training statistics to the Test Dataset**

> **Important rule:** normalization statistics (min, max, mean, std, MAD) must always be calculated from the **training data only**, then reused (not recalculated) on the test data. This keeps the comparison fair and mirrors real-world deployment, where you don't know future/test data in advance.

Test Heights: `154, 160, 168` — normalized using the **training height stats** above:

| Test Height | Min-Max | Z (Std) | Z (MAD) |
|---:|---:|---:|---:|
| 154 | 0.077 | −1.178 | −1.375 |
| 160 | 0.308 | −0.535 | −0.625 |
| 168 | 0.615 | +0.321 | +0.375 |

Test Weights (actual): `49, 53, 61` — normalized using the **training weight stats** above:

| Test Weight | Min-Max | Z (Std) | Z (MAD) |
|---:|---:|---:|---:|
| 49 | 0.08 | −1.061 | −1.201 |
| 53 | 0.24 | −0.628 | −0.711 |
| 61 | 0.56 | +0.238 | +0.270 |

---

## Part 2: Linear Regression

### 2.1 What is Linear Regression? (Easy Words)

Linear regression finds the **best straight line** that describes the relationship between an input variable (X) and an output variable (Y), so we can **predict Y for new values of X**.

Here, we'll predict **Weight** from **Height**: as height goes up, weight tends to go up too — roughly following a straight-line pattern.

### 2.2 The Line Equation

$$\hat{Y} = b_0 + b_1 X$$

| Symbol | Meaning |
|---|---|
| $\hat{Y}$ | The predicted value of Y (weight) |
| $X$ | The input value (height) |
| $b_1$ | **Slope** — how much Y changes for each 1-unit increase in X |
| $b_0$ | **Intercept** — the predicted Y value when X = 0 |

### 2.3 The Least Squares Formulas

Linear regression chooses $b_0$ and $b_1$ so that the line minimizes the total squared distance between actual points and the line (this method is called **Ordinary Least Squares**).

$$b_1 = \frac{n\sum XY - \sum X \sum Y}{n\sum X^2 - (\sum X)^2}$$

$$b_0 = \bar{Y} - b_1 \bar{X}$$

**Breaking it down:**

| Symbol | Meaning |
|---|---|
| $n$ | Number of data points |
| $\sum X$, $\sum Y$ | Sum of all X values, sum of all Y values |
| $\sum XY$ | Sum of each X multiplied by its matching Y |
| $\sum X^2$ | Sum of each X value squared |
| $\bar{X}, \bar{Y}$ | Mean of X, mean of Y |

**Logic:** the numerator of $b_1$ measures how X and Y move together (covariance-like term); the denominator measures how spread out X is (variance-like term). Slope = "how much they move together" ÷ "how much X varies on its own."

### 2.4 Step-by-Step: Training the Model

**Training Dataset:**
```
Height (X): 152, 158, 165, 172, 178
Weight (Y): 47, 51, 58, 66, 72
```

**Step 1 — Build a table of X, Y, X×Y, and X²:**

| Height (X) | Weight (Y) | X × Y | X² |
|---:|---:|---:|---:|
| 152 | 47 | 7,144 | 23,104 |
| 158 | 51 | 8,058 | 24,964 |
| 165 | 58 | 9,570 | 27,225 |
| 172 | 66 | 11,352 | 29,584 |
| 178 | 72 | 12,816 | 31,684 |

**Step 2 — Sum each column:**
```
n     = 5
ΣX    = 152+158+165+172+178 = 825
ΣY    = 47+51+58+66+72      = 294
ΣXY   = 7144+8058+9570+11352+12816 = 48,940
ΣX²   = 23104+24964+27225+29584+31684 = 136,561
```

**Step 3 — Calculate the slope ($b_1$):**

```
Numerator   = n·ΣXY − ΣX·ΣY
            = (5 × 48,940) − (825 × 294)
            = 244,700 − 242,550
            = 2,150

Denominator = n·ΣX² − (ΣX)²
            = (5 × 136,561) − (825)²
            = 682,805 − 680,625
            = 2,180

b1 = 2,150 / 2,180 = 0.9862  (rounded to 4 decimals)
```

**Step 4 — Calculate the mean of X and Y:**
```
X̄ = ΣX / n = 825 / 5 = 165
Ȳ = ΣY / n = 294 / 5 = 58.8
```

**Step 5 — Calculate the intercept ($b_0$):**
```
b0 = Ȳ − b1·X̄
   = 58.8 − (0.9862 × 165)
   = 58.8 − 162.729
   = −103.929
```

**Step 6 — Write the final regression equation:**

$$\boxed{\hat{Weight} = -103.929 + 0.9862 \times Height}$$

**Sanity check:** plugging in the mean height (165) should give back the mean weight:
```
-103.929 + 0.9862 × 165 = -103.929 + 162.729 = 58.800  ✓ matches Ȳ exactly
```

**Step 7 — Check the fit on the training data itself:**

| Height | Actual Weight | Predicted Weight | Residual (Actual − Predicted) |
|---:|---:|---:|---:|
| 152 | 47 | 45.979 | +1.021 |
| 158 | 51 | 51.896 | −0.896 |
| 165 | 58 | 58.800 | −0.800 |
| 172 | 66 | 65.704 | +0.296 |
| 178 | 72 | 71.621 | +0.379 |

Small residuals confirm the line fits the training data well.

---

### 2.5 Predicting on the Test Dataset

**Test Dataset:**
```
Height (X): 154, 160, 168
Weight (actual): 49, 53, 61
```

**Step 1 — Plug each test height into the regression equation:**

```
Height = 154:
ŷ = -103.929 + 0.9862 × 154 = -103.929 + 151.881 = 47.951

Height = 160:
ŷ = -103.929 + 0.9862 × 160 = -103.929 + 157.798 = 53.869

Height = 168:
ŷ = -103.929 + 0.9862 × 168 = -103.929 + 165.688 = 61.759
```

**Step 2 — Predicted vs Actual table:**

| Test Height | Predicted Weight | Actual Weight |
|---:|---:|---:|
| 154 | 47.951 | 49 |
| 160 | 53.869 | 53 |
| 168 | 61.759 | 61 |

The model tracks the actual test weights closely — a good early sign the regression line generalizes well beyond the training data.

---

### 2.6 Mean Squared Error (MSE) — Theory

#### Easy Words

MSE answers: **"On average, how far off — squared — are our predictions from reality?"** We square each error before averaging so that:

1. Negative and positive errors don't cancel each other out
2. Larger errors are penalized more heavily than small ones

#### Formula

$$MSE = \frac{1}{n}\sum_{i=1}^{n}(Y_i - \hat{Y}_i)^2$$

| Symbol | Meaning |
|---|---|
| $Y_i$ | Actual value |
| $\hat{Y}_i$ | Predicted value |
| $(Y_i - \hat{Y}_i)$ | The error / residual for point $i$ |
| $n$ | Number of test points |

A **lower MSE means a better-fitting model**. MSE is measured in *squared units* of the original variable (here, kg²) — taking its square root gives **RMSE**, which is back in the original units (kg) and easier to interpret.

### 2.7 Step-by-Step MSE Calculation

**Step 1 — Calculate each error (Actual − Predicted):**

| Test Height | Actual (Y) | Predicted (Ŷ) | Error (Y − Ŷ) |
|---:|---:|---:|---:|
| 154 | 49 | 47.951 | +1.049 |
| 160 | 53 | 53.869 | −0.869 |
| 168 | 61 | 61.759 | −0.759 |

**Step 2 — Square each error:**

| Error | Error² |
|---:|---:|
| +1.049 | 1.100 |
| −0.869 | 0.755 |
| −0.759 | 0.576 |

**Step 3 — Sum the squared errors:**
```
Sum = 1.100 + 0.755 + 0.576 = 2.430
```

**Step 4 — Divide by n (number of test points):**
```
MSE = 2.430 / 3 = 0.810
```

$$\boxed{MSE \approx 0.810 \text{ kg}^2}$$

**Bonus — RMSE (Root Mean Squared Error), for interpretability:**
```
RMSE = √MSE = √0.810 ≈ 0.900 kg
```

**Interpretation:** on average, the model's weight predictions are off by roughly **0.90 kg** on the test set — a very tight fit, confirming height is a strong linear predictor of weight in this dataset.

---

## Part 3: Foundations of Clustering

### Machine Learning — Quick Refresher

**Machine Learning (ML)** is a branch of AI where computers learn patterns from data rather than following hardcoded rules.

```
Traditional programming:  Rules + Data → Output
Machine Learning:         Data + Examples → Learning Algorithm → Learned Pattern
```

### Types of Machine Learning

| Type | Meaning | Example Tasks |
|---|---|---|
| **Supervised Learning** | Learns from labeled data (`Input → Correct Output`) | Classification, **Regression** (see Part 2) |
| **Unsupervised Learning** | Learns from unlabeled data; discovers hidden structure | **Clustering**, Dimensionality Reduction |
| **Reinforcement Learning** | Learns via rewards/penalties through trial and error | Robotics, game agents |

**Clustering belongs to Unsupervised Learning** — no labels are given; the algorithm discovers groups on its own. (Note the contrast with **Part 2's Linear Regression**, which is *supervised* — we had the correct/actual weight values to check against.)

### Core Data Concepts

| Term | Meaning | Example |
|---|---|---|
| Dataset | A table of related data | Student records with Age, Marks |
| Instance / Sample / Record | One row / one data point | `(Age=20, Marks=80)` |
| Feature / Attribute | A column describing the data | `Age`, `Marks` |
| Feature Value | The actual value of a feature | `Age = 20` |
| Feature Vector | Numeric representation of a data point | `X = (20, 80)` |

### Math You Need

**Euclidean Distance** (the standard similarity/distance measure):

$$d = \sqrt{(x_2-x_1)^2 + (y_2-y_1)^2}$$

Example: distance between `(1,2)` and `(4,6)`:

```
d = √[(4-1)² + (6-2)²] = √[9 + 16] = √25 = 5
```

**Matrix basics:** rows = data points, columns = features (or, for a membership matrix, columns = clusters).

**Summation (Σ):** adds a sequence of values, e.g. `Σx_i = x_1 + x_2 + ... + x_n`.

**Exponent / power (m):** in FCM, membership values are raised to a fuzziness power `m` (commonly `m=2`) so stronger memberships carry more influence when computing centers.

---

## Part 4: What is Clustering?

**Clustering** groups similar data points together and separates dissimilar ones — without predefined labels.

### Common Applications

- **Customer segmentation** — group customers by age/spending behavior
- **Image segmentation** — group pixels into sky, tree, building, etc.
- **Document organization** — group articles by topic (sports, tech, medical)
- **Medical data analysis** — group patients with similar symptoms

### How Clustering Works (Basic Idea)

1. **Measure similarity** — usually via Euclidean distance
2. **Find groups** — points that are close together get grouped

---

## Part 5: Types of Clustering

| Type | Basic Idea | Example Algorithm | Membership |
|---|---|---|---|
| **Partitioning** | Divide data into a fixed number (K) of groups | K-Means | Hard |
| **Hierarchical** | Build a tree of nested groups (dendrogram) | Agglomerative / Divisive | Hard |
| **Density-Based** | Group based on dense regions; detects noise/outliers | DBSCAN | Hard |
| **Fuzzy Clustering** | Allow partial/overlapping membership | Fuzzy C-Means | Soft |

### Hierarchical Clustering — Two Approaches

- **Agglomerative:** starts with individual points → merges into small groups → merges into large groups
- **Divisive:** starts with one big cluster → splits into smaller ones

**Pros:** shows relationships between groups; no need to fix K upfront.
**Cons:** slow on large datasets; merge/split decisions usually can't be undone.

### Density-Based Clustering (e.g., DBSCAN)

Groups based on how "crowded" a region is, not just distance to a center.

**Pros:** finds irregularly shaped clusters and detects outliers/noise.
**Cons:** parameter tuning is hard; struggles when densities vary a lot.

---

## Part 6: Hard vs Fuzzy Clustering

| Feature | Hard Clustering | Fuzzy Clustering |
|---|---|---|
| Membership | Only 0 or 1 | Between 0 and 1 |
| Cluster assignment | One cluster only | Multiple clusters possible |
| Boundary | Sharp | Flexible |
| Uncertainty | Cannot represent | Can represent |
| Example algorithm | K-Means | Fuzzy C-Means |
| Best suited for | Clearly separated data | Overlapping data |

**Mathematical difference:**

- Hard clustering: $u_{ij} \in \{0, 1\}$
- Fuzzy clustering: $0 \le u_{ij} \le 1$

**Example — a 45-year-old person, age-group clustering:**

```
Hard:   Young=0, Middle-aged=1, Old=0
Fuzzy:  Young=0.1, Middle-aged=0.7, Old=0.2
```

**Membership sum rule (fuzzy):** for every data point, memberships across all clusters must sum to 1.

```
0.8 + 0.2 = 1   ✅ valid
0.8 + 0.7 = 1.5 ❌ invalid
```

---

## Part 7: K-Means Clustering

### Definition

**K-Means** is an unsupervised algorithm that divides data into **K** clusters based on similarity, using **hard** (0/1) membership.

- **K** = number of clusters
- **Means** = the cluster center is the mean (average) position of its points, called the **centroid**

### Where K-Means Sits

```
Machine Learning → Unsupervised Learning → Clustering → Partitioning Clustering → K-Means
```

### K-Means Algorithm Step-by-Step

1. **Choose K** — number of clusters
2. **Initialize centroids** — pick K starting center points
3. **Calculate distance** — Euclidean distance from every point to every centroid
4. **Assign each point** to its nearest centroid
5. **Update centroids** — recompute as the mean of all points in each cluster
6. **Repeat** steps 3–5 until assignments/centroids stop changing (**convergence**)

### Objective Function

K-Means minimizes the total squared distance between points and their assigned center:

$$J = \sum_{i=1}^{n} \lVert x_i - c_j \rVert^2$$

### K-Means Worked Example (K=3)

**Dataset (8 points):**

| Point | X | Y |
|---|---|---|
| A1 | 2 | 10 |
| A2 | 2 | 5 |
| A3 | 8 | 4 |
| B1 | 5 | 8 |
| B2 | 7 | 5 |
| B3 | 6 | 4 |
| C1 | 1 | 2 |
| C2 | 4 | 9 |

**Initial centers:** `C1 = A1 = (2,10)`, `C2 = B1 = (5,8)`, `C3 = C1 = (1,2)`

**Iteration 1 — distances & assignment:**

| Point | Dist→C1(2,10) | Dist→C2(5,8) | Dist→C3(1,2) | Assigned |
|---|---:|---:|---:|---|
| A1 (2,10) | 0 | 3.606 | 8.062 | C1 |
| A2 (2,5) | 5.000 | 4.243 | 3.162 | C3 |
| A3 (8,4) | 8.485 | 5.000 | 7.280 | C2 |
| B1 (5,8) | 3.606 | 0 | 7.211 | C2 |
| B2 (7,5) | 7.071 | 3.162 | 6.708 | C2 |
| B3 (6,4) | 7.211 | 4.123 | 5.385 | C2 |
| C1 (1,2) | 8.062 | 7.211 | 0 | C3 |
| C2 (4,9) | 2.236 | 1.414 | 7.616 | C2 |

**New centroids after iteration 1:**

| Cluster | New Centroid |
|---|---|
| Cluster 1 (A1) | (2, 10) |
| Cluster 2 (A3,B1,B2,B3,C2) | (6, 6) |
| Cluster 3 (A2,C1) | (1.5, 3.5) |

**Iteration 2 — reassignment using new centers `C1=(2,10)`, `C2=(6,6)`, `C3=(1.5,3.5)`:**

| Point | To C1 | To C2 | To C3 | New Cluster |
|---|---:|---:|---:|---|
| A1 (2,10) | 0 | 5.657 | 6.519 | C1 |
| A2 (2,5) | 5.000 | 4.123 | 1.581 | C3 |
| A3 (8,4) | 8.485 | 2.828 | 6.519 | C2 |
| B1 (5,8) | 3.606 | 2.236 | 5.148 | C2 |
| B2 (7,5) | 7.071 | 1.414 | 5.701 | C2 |
| B3 (6,4) | 7.211 | 2.000 | 4.528 | C2 |
| C1 (1,2) | 8.062 | 6.403 | 1.581 | C3 |
| C2 (4,9) | 2.236 | 3.162 | 5.701 | C1 |

**Updated centroids:**

| Cluster | Members | Centroid |
|---|---|---|
| Cluster 1 | A1, C2 | (3, 9.5) |
| Cluster 2 | A3, B1, B2, B3 | (6.5, 5.25) |
| Cluster 3 | A2, C1 | (1.5, 3.5) |

Further iterations produce no further changes → **converged**. This is the final result.

### Advantages of K-Means

- Simple to understand and implement
- Fast and scalable to large datasets
- Very effective when clusters are clearly separated

### Disadvantages of K-Means

- Must choose K in advance
- Sensitive to initial centroid placement
- Sensitive to outliers
- Performs poorly on overlapping data

### Choosing K — Elbow Method

Run K-Means for several values of K and plot the error; the point where error stops dropping sharply ("the elbow") is a good choice for K.

| K | Error |
|---|---:|
| 1 | 500 |
| 2 | 250 |
| 3 | 120 |
| 4 | 115 |
| 5 | 110 |

Here, K=3 is a reasonable "elbow" choice.

### When to Use K-Means

✅ Clusters are clearly separated
✅ Dataset is large
✅ Speed matters
✅ Hard (all-or-nothing) grouping is acceptable

---

## Part 8: Fuzzy C-Means (FCM)

### Definition

**Fuzzy C-Means (FCM)** is an unsupervised clustering algorithm that assigns every data point a **degree of membership** to each cluster, instead of forcing it into a single cluster.

- **Fuzzy** → membership is a value in `[0, 1]`, not just 0 or 1
- **C** → number of clusters
- **Means** → cluster centers computed as a **weighted average**

### Key Terms

| Term | Meaning |
|---|---|
| Membership value $u_{ij}$ | Degree to which point $i$ belongs to cluster $j$ |
| Membership matrix $U$ | Matrix of all membership values (rows = points, columns = clusters) |
| Fuzziness parameter $m$ | Controls how "soft" clustering is (commonly $m=2$) |
| Cluster center $C_j$ | Weighted-average position of a cluster |

**Effect of `m`:**
- Small `m` → memberships become more extreme (closer to hard clustering)
- Large `m` → memberships become more evenly spread ("softer")

### Core Formulas

**Cluster center (weighted average):**

$$C_j = \frac{\sum_{i=1}^{n} (u_{ij})^m \, x_i}{\sum_{i=1}^{n} (u_{ij})^m}$$

**Membership update:**

$$u_{ij} = \frac{1}{\sum_{k=1}^{c} \left( \dfrac{d_{ij}}{d_{ik}} \right)^{\frac{2}{m-1}}}$$

**Objective function (minimized by the algorithm):**

$$J_m = \sum_{i=1}^{n} \sum_{j=1}^{c} u_{ij}^{m} \, d_{ij}^{2}$$

Where: `n` = number of points, `c` = number of clusters, `d_ij` = distance from point `i` to center `j`.

**Membership rules:**
- $0 \le u_{ij} \le 1$ for every entry
- For each data point: $\sum_{j=1}^{c} u_{ij} = 1$

### FCM Algorithm Step-by-Step

```
Choose number of clusters (C) and fuzziness (m)
            ↓
Initialize membership matrix (U) — random values, each row sums to 1
            ↓
Compute cluster centers (weighted average using u^m)
            ↓
Compute distances (each point to each center)
            ↓
Update memberships (closer → higher membership)
            ↓
Check convergence (|U_new − U_old| < ε)
            ↓
Repeat if not yet stable → Final clusters
```

**Memory trick:** `M → C → D → U → Repeat`
(**M**embership init → **C**enters → **D**istances → **U**pdate memberships → repeat)

### FCM Worked Example

**Dataset (5 points) with initial memberships, `m = 2`, `C = 2`:**

| Instance | X | Y | C1 (init) | C2 (init) |
|---|---|---|---:|---:|
| 1 | 1 | 3 | 0.2 | 0.8 |
| 2 | 2 | 4 | 0.3 | 0.7 |
| 3 | 3 | 2 | 0.5 | 0.5 |
| 4 | 5 | 5 | 0.4 | 0.6 |
| 5 | 4 | 6 | 0.6 | 0.4 |

**Step 1 — square the memberships ($u^2$, since $m=2$):**

| Instance | $u_{i1}$ | $u_{i1}^2$ | $u_{i2}$ | $u_{i2}^2$ |
|---|---:|---:|---:|---:|
| 1 | 0.2 | 0.04 | 0.8 | 0.64 |
| 2 | 0.3 | 0.09 | 0.7 | 0.49 |
| 3 | 0.5 | 0.25 | 0.5 | 0.25 |
| 4 | 0.4 | 0.16 | 0.6 | 0.36 |
| 5 | 0.6 | 0.36 | 0.4 | 0.16 |

**Step 2 — compute new cluster centers (weighted average):**

$$C_1 = \left(\frac{3.21}{0.90}, \frac{3.94}{0.90}\right) = (3.567,\ 4.378)$$

$$C_2 = \left(\frac{4.81}{1.90}, \frac{7.14}{1.90}\right) = (2.532,\ 3.758)$$

**Step 3 — distance of each point to each new center:**

| Instance | Point | Dist → C1 | Dist → C2 |
|---|---|---:|---:|
| 1 | (1,3) | 2.913 | 1.709 |
| 2 | (2,4) | 1.601 | 0.289 |
| 3 | (3,2) | 2.402 | 1.788 |
| 4 | (5,5) | 1.615 | 3.092 |
| 5 | (4,6) | 1.632 | 2.736 |

**Step 4 — update memberships** (for 2 clusters: $u_{i1} = \dfrac{1}{1+(d_{i1}/d_{i2})^2}$, and $u_{i2}=1-u_{i1}$):

| Instance | C1 (new) | C2 (new) |
|---|---:|---:|
| 1 | 0.256 | 0.744 |
| 2 | 0.032 | 0.968 |
| 3 | 0.356 | 0.644 |
| 4 | 0.785 | 0.215 |
| 5 | 0.738 | 0.262 |

**Step 5 — hard assignment (highest membership wins, for interpretation only):**

| Instance | C1 | C2 | Assigned |
|---|---:|---:|---|
| 1 | 0.256 | 0.744 | Cluster 2 |
| 2 | 0.032 | 0.968 | Cluster 2 |
| 3 | 0.356 | 0.644 | Cluster 2 |
| 4 | 0.785 | 0.215 | Cluster 1 |
| 5 | 0.738 | 0.262 | Cluster 1 |

**Observation:** the assignment for Instance 3 flipped from "equal/ambiguous" to a clear Cluster 2 lean after recalculating centers — this is FCM refining its answer through iteration.

> **Note:** keep several decimal places during intermediate calculations (don't round early) — rounding can shift the final membership values slightly. The formulas and procedure above are what matter for exams; exact decimals may vary a bit with precision used.

### Advantages of FCM

- Represents uncertainty naturally
- Handles overlapping clusters well
- Provides richer information than hard clustering

### Disadvantages of FCM

- Slower than K-Means (updates memberships for every cluster)
- Sensitive to the initial membership matrix
- Requires choosing the number of clusters beforehand
- Can converge to a local optimum, not necessarily the global best

### Real-World Applications of FCM

- Medical image segmentation (e.g., separating tissue types in MRI)
- Customer segmentation (customers fitting multiple profiles)
- Pattern recognition & computer vision
- Remote sensing (land cover classification)
- Document clustering, bioinformatics

---

## Part 9: K-Means vs FCM — Comparison

| Feature | K-Means | Fuzzy C-Means |
|---|---|---|
| Learning type | Unsupervised | Unsupervised |
| Cluster type | Hard | Soft |
| Membership | 0 or 1 | 0 to 1 |
| Point belongs to | One cluster only | Multiple clusters |
| Center calculation | Simple average | Weighted average |
| Uses membership matrix? | No | Yes |
| Handles uncertainty? | No | Yes |
| Handles overlapping data? | Poorly | Well |
| Speed | Faster | Slower |
| Complexity | Simple | More complex |

**Example — a customer between "Premium" and "Regular":**

```
K-Means:  Premium = 1, Regular = 0
FCM:      Premium = 0.65, Regular = 0.35
```

---

## Part 10: Exam Revision Notes

### Quick Definitions

> **Min-Max Normalization:** rescales a value based on its position between the dataset's minimum and maximum, producing a result in `[0, 1]`.

> **Z-Score Normalization:** rescales a value based on how many standard deviations it is from the mean.

> **Z-Score (MAD) Normalization:** same as z-score, but uses mean absolute deviation instead of standard deviation for a more outlier-resistant spread measure.

> **Linear Regression:** a supervised technique that fits a straight line $\hat{Y}=b_0+b_1X$ to minimize the sum of squared errors between actual and predicted values.

> **Mean Squared Error (MSE):** the average of squared differences between actual and predicted values; lower is better.

> **K-Means:** A hard clustering algorithm that partitions data into K clusters by assigning each point to the nearest centroid and iteratively updating centroids as the mean of assigned points.

> **Fuzzy C-Means:** A soft clustering algorithm in which each data point belongs to every cluster with a membership value between 0 and 1, and the memberships for each data point sum to 1.

### Common Exam Questions

1. Explain min-max normalization and z-score normalization, and give the formula for each.
2. Why would you use MAD instead of standard deviation for z-score normalization?
3. Derive/explain the least squares formulas for linear regression ($b_0$, $b_1$).
4. Given a training dataset, fit a linear regression line and predict values for new/test inputs.
5. Explain Mean Squared Error and why errors are squared instead of just summed.
6. Explain the K-Means algorithm step-by-step.
7. What is a centroid? How is it computed?
8. Define Fuzzy C-Means and explain the membership matrix.
9. What is the fuzziness parameter `m`, and what does it control?
10. Write and explain the cluster center formula and membership update formula for FCM.
11. Compare K-Means and FCM (table format is a safe bet).
12. Solve a numerical problem: normalization, regression + MSE, or one/more iterations of K-Means/FCM.
13. Explain the Elbow Method for choosing K.

### Memory Tricks

- **Normalization choice:** *Min-Max = bounded range. Z-Score = "how many spreads from average." MAD = z-score, but outlier-proof.*
- **Regression line:** *Slope = "how much X and Y move together" ÷ "how much X varies alone."*
- **MSE:** *Square it so errors can't cancel, then average it.*
- **FCM workflow:** `M → C → D → U → Repeat` (Membership init → Centers → Distances → Update → repeat)
- **Cluster center formula:** *Center = Weighted Average of Data Points*
- **Membership formula:** *Closer → Higher Membership, Farther → Lower Membership*
- **K-Means core loop:** *Assign → Average → Repeat*

---

## What to Learn Next

1. **Data Normalization & Standardization** *(covered above — foundation for almost everything else)*
2. **Linear Regression** *(covered above — simplest supervised learning model)*
3. **Multiple Linear Regression** (predicting from more than one feature at once)
4. **Logistic Regression** (for classification instead of continuous prediction)
5. **K-Means Clustering** *(covered above)*
6. **Hierarchical Clustering** (Agglomerative / Divisive)
7. **DBSCAN** (density-based clustering)
8. **Fuzzy C-Means** *(covered above)*
9. **Gaussian Mixture Models (GMM)** and the **Expectation-Maximization (EM)** algorithm
10. **Cluster validity indices** — Silhouette Score, Dunn Index, Davies–Bouldin Index
11. **Advanced fuzzy clustering variants** — Possibilistic C-Means, Gustafson–Kessel

---

*Compiled as structured exam/reference notes for Advanced Data Mining and Machine Learning coursework.*
