# Fuzzy C-Means (FCM) Clustering: A Step-by-Step Manual Guide

An intuitive, step-by-step numerical walkthrough of **one iteration of the Fuzzy C-Means (FCM)** clustering algorithm. This repository serves as a practical reference for understanding how soft clustering, membership updates, and centroid shifts work mathematically using a small 2D dataset with a fuzziness parameter $m = 2$.

---

## 📌 Introduction to Fuzzy C-Means

Fuzzy C-Means (FCM) is an unsupervised machine learning clustering algorithm where **each data point belongs to every cluster with a certain degree of membership**, rather than belonging exclusively to a single cluster.

### Hard vs. Soft Clustering
* **K-Means (Hard Clustering):** A data point belongs to *exactly one* cluster (e.g., Membership $= 1$ or $0$).
* **FCM (Soft/Fuzzy Clustering):** A data point can partially belong to multiple clusters (e.g., $70\%$ Cluster A, $30\%$ Cluster B).

> **Example:** Consider a student who excels equally in Mathematics and Physics. 
> * **K-Means** forces the student into one department: `Student → Mathematics`.
> * **FCM** distributes their profile: `Student → 0.70 Mathematics, 0.30 Physics`.

---

## 📊 The Dataset & Initial States

We use a sample dataset consisting of 5 instances in a 2-D space ($X, Y$) with predefined initial membership values for 2 clusters ($c = 2$).

| Instance | X | Y | Cluster 1 Membership ($u_{i1}$) | Cluster 2 Membership ($u_{i2}$) |
| :---: | :---: | :---: | :---: | :---: |
| **1** | 1 | 3 | 0.2 | 0.8 |
| **2** | 2 | 4 | 0.3 | 0.7 |
| **3** | 3 | 2 | 0.5 | 0.5 |
| **4** | 5 | 5 | 0.4 | 0.6 |
| **5** | 4 | 6 | 0.6 | 0.4 |

### Fundamental FCM Constraint
For any instance $i$, the sum of its memberships across all clusters must equal 1:
$$u_{i1} + u_{i2} = 1$$

---

## 🛠️ Step-by-Step Iteration Execution ($m=2$)

### Step 1: Set the Fuzziness Parameter
We choose the standard fuzziness exponent:
$$m = 2$$
* $m = 1$ converges towards hard K-Means.
* Higher values of $m$ make the boundaries fuzzier. $m = 2$ is the industry standard.

### Step 2: Calculate Squared Memberships ($u_{ij}^m$)
Because $m = 2$, we calculate $u_{ij}^2$ for all data entries:

| Instance | $u_{i1}$ | $u_{i1}^2$ | $u_{i2}$ | $u_{i2}^2$ |
| :---: | :---: | :---: | :---: | :---: |
| **1** | 0.2 | 0.04 | 0.8 | 0.64 |
| **2** | 0.3 | 0.09 | 0.7 | 0.49 |
| **3** | 0.5 | 0.25 | 0.5 | 0.25 |
| **4** | 0.4 | 0.16 | 0.6 | 0.36 |
| **5** | 0.6 | 0.36 | 0.4 | 0.16 |

### Step 3: Compute New Cluster Centers
The centroid $v_j$ is a weighted average of coordinates, calculated as:
$$v_j = \left( \frac{\sum_{i=1}^{n} u_{ij}^m X_i}{\sum_{i=1}^{n} u_{ij}^m}, \frac{\sum_{i=1}^{n} u_{ij}^m Y_i}{\sum_{i=1}^{n} u_{ij}^m} \right)$$

#### 🔹 Cluster 1 Center ($v_1$)
* **Denominator:** $0.04 + 0.09 + 0.25 + 0.16 + 0.36 = 0.90$
* **X-coordinate:** $\frac{(0.04 \times 1) + (0.09 \times 2) + (0.25 \times 3) + (0.16 \times 5) + (0.36 \times 4)}{0.90} = \frac{3.21}{0.90} \approx 3.5667$
* **Y-coordinate:** $\frac{(0.04 \times 3) + (0.09 \times 4) + (0.25 \times 2) + (0.16 \times 5) + (0.36 \times 6)}{0.90} = \frac{3.94}{0.90} \approx 4.3778$

$$v_1 = (3.5667, 4.3778)$$

#### 🔹 Cluster 2 Center ($v_2$)
* **Denominator:** $0.64 + 0.49 + 0.25 + 0.36 + 0.16 = 1.90$
* **X-coordinate:** $\frac{(0.64 \times 1) + (0.49 \times 2) + (0.25 \times 3) + (0.36 \times 5) + (0.16 \times 4)}{1.90} = \frac{4.81}{1.90} \approx 2.5316$
* **Y-coordinate:** $\frac{(0.64 \times 3) + (0.49 \times 4) + (0.25 \times 2) + (0.36 \times 5) + (0.16 \times 6)}{1.90} = \frac{7.14}{1.90} \approx 3.7579$

$$v_2 = (2.5316, 3.7579)$$

### Step 4: Calculate Euclidean Distances
We measure the distance $d_{ij}$ from each point $i$ to both updated cluster centers $v_j$:
$$d_{ij} = \sqrt{(X_i - v_{jx})^2 + (Y_i - v_{jy})^2}$$

| Instance | Distance to Cluster 1 ($d_{i1}$) | Distance to Cluster 2 ($d_{i2}$) |
| :---: | :---: | :---: |
| **1** | 2.913 | 1.689 |
| **2** | 1.634 | 0.579 |
| **3** | 2.469 | 1.798 |
| **4** | 1.553 | 2.748 |
| **5** | 1.649 | 2.749 |

### Step 5: Update Membership Values
Using the textbook formula for membership adjustments:
$$u_{ij} = \frac{1}{\sum_{k=1}^{c} \left( \frac{d_{ij}}{d_{ik}} \right)^{\frac{2}{m-1}}}$$

For $m = 2$, the exponent simplifies to $\frac{2}{2-1} = 2$, yielding:
$$u_{ij} = \frac{1}{\sum_{k=1}^{c} \left( \frac{d_{ij}}{d_{ik}} \right)^2}$$

#### **Example Calculation for Instance 1:**
* $u_{11} = \frac{1}{1 + \left(\frac{2.913}{1.689}\right)^2} = \frac{1}{1 + 2.974} \approx 0.252$
* $u_{12} = 1 - 0.252 = 0.748$

#### **Comprehensive Updated Membership Matrix:**
| Instance | New Cluster 1 ($u_{i1}$) | New Cluster 2 ($u_{i2}$) |
| :---: | :---: | :---: |
| **1** | 0.252 | 0.748 |
| **2** | 0.111 | 0.889 |
| **3** | 0.347 | 0.653 |
| **4** | 0.758 | 0.242 |
| **5** | 0.735 | 0.265 |

---

## 📈 Optimization Metric: The Objective Function

The primary goal of FCM is to iteratively minimize the total clustering cost or Objective Function ($J_m$):
$$J_m = \sum_{i=1}^{n} \sum_{j=1}^{c} u_{ij}^m d_{ij}^2$$

A lower value indicates that points with stronger membership structures are strategically positioned closer to their respective centroids.

---

## 📋 Formula Guide & Verification Notes

When cross-referencing literature or working through math assignments, keep these structural rules in mind:

### 1. Alternative Inverse-Distance Formula Notation
Some documents represent the updates as an inverse-distance relation:
$$u_{ij} = \frac{\left(\frac{1}{d_{ij}}\right)^{\frac{2}{m-1}}}{\sum_{k=1}^{c} \left(\frac{1}{d_{ik}}\right)^{\frac{2}{m-1}}}$$
This is mathematically equivalent to the textbook version. Simply verify that if your text drops the factor of $2$ in the exponent (using $\frac{1}{m-1}$), the distance variable $d_{ij}$ is likely explicitly pre-defined as a *squared* Euclidean distance rather than standard Euclidean metric space.

### 2. Guarding Against Floating-Point Cascading Errors
* **Intermediate Steps:** Always maintain **at least 4 decimal places** when logging Euclidean distances and squares. 
* **Final Answers:** Rounding to 3 or 4 decimal places should occur *only* during the final structural resolution of your matrix vectors. Prematurely trimming decimals to 2 places ($2.45 \rightarrow 2.4$) introduces compounded error variations across subsequent steps.

---

## 🎯 Summary Results (End of Iteration 1)

* **Updated Center 1 ($v_1$):** `(3.5667, 4.3778)`
* **Updated Center 2 ($v_2$):** `(2.5316, 3.7579)`

The system will now pass these new values as input matrices for **Iteration 2**. The loop repeats recursively until $\lVert U^{(k+1)} - U^{(k)} \rVert < \varepsilon$, where $\varepsilon$ represents your termination error delta tolerance threshold.
