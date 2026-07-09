# K-Nearest Neighbors (KNN) Classification

## Problem Statement

A new fruit has the following features:

- **Weight:** 155
- **Texture:** 1
- **k:** 3
- **Distance Metric:** Euclidean Distance

### Training Dataset

| Point | Weight | Texture | Label |
|:----:|------:|:-------:|:------|
| 1 | 150 | 1 | Apple |
| 2 | 170 | 1 | Apple |
| 3 | 140 | 0 | Orange |
| 4 | 130 | 0 | Orange |
| 5 | 160 | 1 | Apple |
| 6 | 120 | 0 | Orange |

---

# Step 1 — KNN Overview

**K-Nearest Neighbors (KNN)** is a supervised machine learning algorithm that classifies a new data point by finding the **k closest training samples**.

For this problem:

- **k = 3**
- Compute the Euclidean distance from the new fruit to every training point.
- Select the **3 nearest neighbors**.
- Predict the class using **majority voting**.

---

# Step 2 — Euclidean Distance Formula

The Euclidean distance between two points is

```math
d=\sqrt{(x_2-x_1)^2+(y_2-y_1)^2}
```

where

- **x** = Weight
- **y** = Texture

The new fruit is

```text
(155, 1)
```

---

# Step 3 — Distance Calculations

## Point 1 (150, 1) — Apple

Weight Difference

```text
155 − 150 = 5
```

Texture Difference

```text
1 − 1 = 0
```

Distance

```math
d=\sqrt{5^2+0^2}
=\sqrt{25}
=5.00
```

---

## Point 2 (170, 1) — Apple

Weight Difference

```text
170 − 155 = 15
```

Texture Difference

```text
1 − 1 = 0
```

Distance

```math
d=\sqrt{15^2+0^2}
=\sqrt{225}
=15.00
```

---

## Point 3 (140, 0) — Orange

Weight Difference

```text
155 − 140 = 15
```

Texture Difference

```text
1 − 0 = 1
```

Distance

```math
d=\sqrt{15^2+1^2}
=\sqrt{226}
\approx15.03
```

---

## Point 4 (130, 0) — Orange

Weight Difference

```text
155 − 130 = 25
```

Texture Difference

```text
1 − 0 = 1
```

Distance

```math
d=\sqrt{25^2+1^2}
=\sqrt{626}
\approx25.02
```

---

## Point 5 (160, 1) — Apple

Weight Difference

```text
160 − 155 = 5
```

Texture Difference

```text
1 − 1 = 0
```

Distance

```math
d=\sqrt{5^2+0^2}
=\sqrt{25}
=5.00
```

---

## Point 6 (120, 0) — Orange

Weight Difference

```text
155 − 120 = 35
```

Texture Difference

```text
1 − 0 = 1
```

Distance

```math
d=\sqrt{35^2+1^2}
=\sqrt{1226}
\approx35.01
```

---

# Step 4 — Sort by Distance

| Rank | Point | Label | Distance |
|----:|:-----:|:------|---------:|
| 1 | Point 1 | Apple | 5.00 |
| 2 | Point 5 | Apple | 5.00 |
| 3 | Point 2 | Apple | 15.00 |
| 4 | Point 3 | Orange | 15.03 |
| 5 | Point 4 | Orange | 25.02 |
| 6 | Point 6 | Orange | 35.01 |

---

# Step 5 — Select the 3 Nearest Neighbors

| Neighbor | Label |
|:--------:|:------|
| Point 1 | Apple |
| Point 5 | Apple |
| Point 2 | Apple |

---

# Step 6 — Majority Voting

| Class | Votes |
|:------|------:|
| Apple | **3** |
| Orange | **0** |

Since **Apple** receives the majority vote, the new fruit is classified as **Apple**.

---

# Final Prediction

> **Predicted Class: Apple ✅**

---

# Summary

| Item | Value |
|------|-------|
| New Fruit | (155, 1) |
| Algorithm | K-Nearest Neighbors (KNN) |
| Distance Metric | Euclidean Distance |
| k | 3 |
| Nearest Neighbors | Apple, Apple, Apple |
| Final Prediction | **Apple** ✅ |

---

**Conclusion:**  
Using the Euclidean distance metric with **k = 3**, the three closest neighbors are all **Apple**. Therefore, the KNN classifier predicts that the new fruit belongs to the **Apple** class.
