# K-Nearest Neighbors (KNN) Classification

## Given Data

A new fruit has:

- **Weight = 155**
- **Texture = 1**
- **k = 3**
- **Distance Measure = Euclidean Distance**

### Training Dataset

| Point | Weight | Texture | Label |
|------:|-------:|--------:|--------|
| 1 | 150 | 1 | Apple |
| 2 | 170 | 1 | Apple |
| 3 | 140 | 0 | Orange |
| 4 | 130 | 0 | Orange |
| 5 | 160 | 1 | Apple |
| 6 | 120 | 0 | Orange |

---

# Step 1: What is KNN?

**K-Nearest Neighbors (KNN)** is a classification algorithm that predicts the class of a new data point by looking at the **k closest training points**.

For this problem:

- **k = 3**
- Find the **3 nearest neighbors**
- The majority class among these neighbors becomes the prediction.

---

# Step 2: Euclidean Distance Formula

The Euclidean distance between two points is

\[
d=\sqrt{(x_2-x_1)^2+(y_2-y_1)^2}
\]

where:

- \(x\) = Weight
- \(y\) = Texture

The new fruit is located at:

\[
(155,\;1)
\]

---

## Distance to Point 1 (150, 1)

**Label:** Apple

Weight difference:

\[
155-150=5
\]

Texture difference:

\[
1-1=0
\]

Distance:

\[
\sqrt{5^2+0^2}
=\sqrt{25}
=5.00
\]

---

## Distance to Point 5 (160, 1)

**Label:** Apple

Weight difference:

\[
160-155=5
\]

Texture difference:

\[
1-1=0
\]

Distance:

\[
\sqrt{5^2+0^2}
=\sqrt{25}
=5.00
\]

---

## Distance to Point 2 (170, 1)

**Label:** Apple

Weight difference:

\[
170-155=15
\]

Texture difference:

\[
1-1=0
\]

Distance:

\[
\sqrt{15^2+0^2}
=\sqrt{225}
=15.00
\]

---

## Distance to Point 3 (140, 0)

**Label:** Orange

Weight difference:

\[
155-140=15
\]

Texture difference:

\[
1-0=1
\]

Distance:

\[
\sqrt{15^2+1^2}
=\sqrt{225+1}
=\sqrt{226}
\approx 15.03
\]

---

## Distance to Point 4 (130, 0)

**Label:** Orange

Weight difference:

\[
155-130=25
\]

Texture difference:

\[
1-0=1
\]

Distance:

\[
\sqrt{25^2+1^2}
=\sqrt{625+1}
=\sqrt{626}
\approx 25.02
\]

---

## Distance to Point 6 (120, 0)

**Label:** Orange

Weight difference:

\[
155-120=35
\]

Texture difference:

\[
1-0=1
\]

Distance:

\[
\sqrt{35^2+1^2}
=\sqrt{1225+1}
=\sqrt{1226}
\approx 35.01
\]

---

# Step 3: Sort the Distances

| Rank | Point | Label | Distance |
|-----:|------:|--------|---------:|
| 1 | Point 1 | Apple | 5.00 |
| 2 | Point 5 | Apple | 5.00 |
| 3 | Point 2 | Apple | 15.00 |
| 4 | Point 3 | Orange | 15.03 |
| 5 | Point 4 | Orange | 25.02 |
| 6 | Point 6 | Orange | 35.01 |

---

# Step 4: Select the 3 Nearest Neighbors

| Point | Label |
|------:|--------|
| 1 | Apple |
| 5 | Apple |
| 2 | Apple |

---

# Step 5: Majority Voting

Count the labels among the three nearest neighbors:

- **Apple = 3**
- **Orange = 0**

Since **Apple** has the majority vote, the new fruit is classified as an **Apple**.

---

# Final Answer

## **Predicted Class: Apple ✅**

### Reason

The three nearest neighbors are all labeled **Apple**, so the KNN algorithm predicts that the new fruit belongs to the **Apple** class.

---

# Summary

- **New Fruit:** (155, 1)
- **Distance Metric:** Euclidean Distance
- **k:** 3
- **Nearest Neighbors:** Apple, Apple, Apple
- **Predicted Class:** **Apple** ✅
