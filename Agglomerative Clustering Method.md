# Agglomerative Clustering Method

## Definition

**Agglomerative Clustering** is a **hierarchical clustering** algorithm that follows a **bottom-up approach**. It starts by treating **each data point as an individual cluster** and repeatedly merges the two closest (most similar) clusters based on a **distance metric** and a **linkage criterion** until either:

* all data points are grouped into a single cluster, or
* the desired number of clusters is obtained.

The entire clustering process is represented using a **dendrogram**, which shows the hierarchy and order of cluster merges.

---

# Key Idea

* **Type:** Hierarchical Clustering
* **Approach:** Bottom-up
* **Starts with:** One cluster for each data point
* **Ends with:** One large cluster or the required number of clusters

---

# How Agglomerative Clustering Works (Algorithm)

### Step 1

Treat every data point as a separate cluster.

```
{A} {B} {C} {D}
```

### Step 2

Calculate the distance between every pair of clusters using a distance metric such as:

* Euclidean Distance
* Manhattan Distance
* Cosine Distance
* Minkowski Distance

---

### Step 3

Merge the two closest clusters.

---

### Step 4

Update the distance matrix using a linkage method.

---

### Step 5

Repeat Steps 3 and 4 until:

* all points become one cluster, or
* the required number of clusters is reached.

---

# Mathematical Example

Suppose we have four one-dimensional data points.

| Point | Value |
| ----- | ----: |
| A     |     2 |
| B     |     4 |
| C     |    10 |
| D     |    12 |

Initially,

```
{A} {B} {C} {D}
```

---

## Step 1: Compute Distance Matrix

Using **Euclidean Distance**

[
d(x,y)=|x-y|
]

Distances:

[
d(A,B)=|2-4|=2
]

[
d(A,C)=|2-10|=8
]

[
d(A,D)=|2-12|=10
]

[
d(B,C)=|4-10|=6
]

[
d(B,D)=|4-12|=8
]

[
d(C,D)=|10-12|=2
]

Distance Matrix

|       |  A |  B |  C |  D |
| ----- | -: | -: | -: | -: |
| **A** |  0 |  2 |  8 | 10 |
| **B** |  2 |  0 |  6 |  8 |
| **C** |  8 |  6 |  0 |  2 |
| **D** | 10 |  8 |  2 |  0 |

---

## Step 2: Merge the Closest Clusters

The smallest distance is

[
d(A,B)=2
]

and

[
d(C,D)=2
]

Suppose we merge **A and B** first.

Clusters become

```
{AB} {C} {D}
```

---

## Step 3: Update Distances (Single Linkage)

Distance between **AB** and **C**

[
d(AB,C)=\min(d(A,C),d(B,C))
]

[
=\min(8,6)=6
]

Distance between **AB** and **D**

[
d(AB,D)=\min(10,8)=8
]

Updated Distance Matrix

|        | AB |  C |  D |
| ------ | -: | -: | -: |
| **AB** |  0 |  6 |  8 |
| **C**  |  6 |  0 |  2 |
| **D**  |  8 |  2 |  0 |

---

## Step 4: Merge C and D

Smallest distance

[
d(C,D)=2
]

Clusters become

```
{AB} {CD}
```

---

## Step 5: Final Merge

Using **Single Linkage**

[
d(AB,CD)
========

\min
\left(
d(A,C),
d(A,D),
d(B,C),
d(B,D)
\right)
]

# [

\min(8,10,6,8)=6
]

Merge the remaining clusters.

```
{ABCD}
```

The clustering process is complete.

---

# Simple Example

Suppose there are five students represented by

```
A  B  C  D  E
```

Initially

```
{A} {B} {C} {D} {E}
```

Merge closest clusters

```
{AB} {C} {D} {E}
```

Next merge

```
{AB} {C} {DE}
```

Next merge

```
{AB} {CDE}
```

Finally

```
{ABCDE}
```

This illustrates how clusters gradually grow from individual points.

---

# Dendrogram

```
             ABCD
            /    \
          AB      CD
         /  \    /  \
        A    B  C    D
```

A **dendrogram** is a tree-like diagram showing:

* which clusters merge
* the order of merging
* the distance at which they merge

The height of each merge indicates the distance between clusters.

---

# Distance Measures

Agglomerative clustering can use different distance metrics.

### 1. Euclidean Distance

Most common.

[
d(x,y)=\sqrt{\sum_{i=1}^{n}(x_i-y_i)^2}
]

---

### 2. Manhattan Distance

[
d(x,y)=\sum |x_i-y_i|
]

---

### 3. Cosine Distance

Measures the angle between vectors.

Useful for text mining and document clustering.

---

### 4. Minkowski Distance

A generalized distance measure.

---

# Linkage Methods

After merging clusters, we must compute the distance between the new cluster and the remaining clusters.

This is called the **linkage method**.

---

## 1. Single Linkage (Nearest Neighbor)

Uses the **minimum distance** between two clusters.

[
d(A,B)=
\min(d(x,y))
]

where

[
x\in A,\qquad y\in B
]

### Characteristics

* Forms long chain-like clusters
* Sensitive to noise
* Good for irregular-shaped clusters

---

## 2. Complete Linkage (Farthest Neighbor)

Uses the **maximum distance**.

[
d(A,B)=
\max(d(x,y))
]

### Characteristics

* Produces compact clusters
* Less affected by chaining
* Sensitive to outliers

---

## 3. Average Linkage

Uses the average distance between all pairs.

[
d(A,B)
======

\frac{1}{|A||B|}
\sum_{x\in A}
\sum_{y\in B}
d(x,y)
]

### Characteristics

* Balanced approach
* More stable than single linkage

---

## 4. Ward's Linkage

Chooses the merge that results in the **smallest increase in within-cluster variance (SSE)**.

### Characteristics

* Produces clusters of similar size
* Often gives the best clustering result
* Most commonly used in practice

---

# Time Complexity

* Distance matrix calculation:

[
O(n^2)
]

* Overall complexity:

[
O(n^3)
]

Memory complexity:

[
O(n^2)
]

Therefore, Agglomerative Clustering is suitable for **small and medium-sized datasets**, but not very large datasets.

---

# Stopping Criteria

The algorithm stops when:

* only one cluster remains, or
* the desired number of clusters is reached, or
* the dendrogram is cut at a chosen height.

---

# Advantages

* Easy to understand and implement.
* No need to specify initial cluster centers.
* Produces a dendrogram for visualization.
* Works well for small and medium-sized datasets.
* Can identify clusters of different shapes.
* Does not require assumptions about data distribution.

---

# Disadvantages

* Computationally expensive for large datasets.
* Requires large memory.
* Sensitive to noise and outliers.
* Once clusters are merged, they cannot be split.
* Results depend on the choice of linkage method and distance metric.

---

# Applications

Agglomerative clustering is widely used in:

* Customer segmentation
* Document clustering
* Image segmentation
* Gene expression analysis
* Medical diagnosis
* Social network analysis
* Market research
* Recommendation systems
* Pattern recognition

---

# Real-Life Example

Imagine a teacher wants to group students based on their exam marks.

Initially,

```
Student1
Student2
Student3
Student4
Student5
```

Each student forms a separate cluster.

The teacher repeatedly groups the two students with the most similar marks until all similar students are grouped together.

This is exactly how Agglomerative Clustering works.

---

# Summary Table

| Feature           | Agglomerative Clustering                  |
| ----------------- | ----------------------------------------- |
| Type              | Hierarchical Clustering                   |
| Approach          | Bottom-up                                 |
| Starts With       | Each data point as a separate cluster     |
| Ends With         | One cluster or desired number of clusters |
| Distance Measures | Euclidean, Manhattan, Cosine, Minkowski   |
| Linkage Methods   | Single, Complete, Average, Ward           |
| Output            | Hierarchical clusters and a dendrogram    |
| Time Complexity   | (O(n^3))                                  |
| Space Complexity  | (O(n^2))                                  |
| Best For          | Small to medium-sized datasets            |

---

# Exam Definition (2–3 Marks)

**Agglomerative Clustering** is a **bottom-up hierarchical clustering algorithm** that starts with each data point as an individual cluster and repeatedly merges the two closest clusters using a distance metric and a linkage criterion until the desired number of clusters or a single cluster remains. The complete merging process is represented by a **dendrogram**, which shows the hierarchy of cluster formation.

---

# Viva/Interview Questions

**1. Why is it called a bottom-up approach?**
Because it starts with individual data points and gradually merges them into larger clusters.

**2. What is the output of Agglomerative Clustering?**
A hierarchy of clusters represented by a **dendrogram**.

**3. Does Agglomerative Clustering require the number of clusters beforehand?**
No. You can build the full hierarchy first and then choose the desired number of clusters by cutting the dendrogram.

**4. What is the difference between Agglomerative and Divisive Clustering?**

| Agglomerative                     | Divisive                      |
| --------------------------------- | ----------------------------- |
| Bottom-up                         | Top-down                      |
| Starts with single-point clusters | Starts with one large cluster |
| Merges clusters                   | Splits clusters               |
| More commonly used                | Less commonly used            |

**5. Which linkage method is most commonly used?**
**Ward's linkage**, because it often produces compact and well-balanced clusters.

**6. What is a dendrogram?**
A tree-like diagram that shows the order and distance at which clusters are merged, helping determine the optimal number of clusters.

This combined version includes the complete **definition, algorithm, mathematical example, linkage methods, dendrogram, complexity, advantages, disadvantages, applications, comparison, summary, and exam-oriented questions**, making it suitable for both university exams and interview preparation.
