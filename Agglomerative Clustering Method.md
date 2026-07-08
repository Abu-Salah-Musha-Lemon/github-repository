# Agglomerative Clustering Method

## Definition

**Agglomerative Clustering** is a **hierarchical clustering** algorithm that follows a **bottom-up approach**. It starts by treating **each data point as an individual cluster** and repeatedly merges the two closest (most similar) clusters based on a **distance metric** and a **linkage criterion** until either:

- All data points are grouped into a single cluster.
- The desired number of clusters is obtained.

The complete clustering process is represented using a **dendrogram**, which shows the hierarchy of cluster merges.

---
### Single-Line Definition

> **Agglomerative Clustering is a bottom-up hierarchical clustering algorithm that starts with each data point as a separate cluster and repeatedly merges the closest clusters until the desired number of clusters or a single cluster is formed.**

Or, if you want an even shorter **exam-friendly** version:

> **Agglomerative Clustering is a hierarchical clustering technique that builds clusters by successively merging the closest data points or clusters in a bottom-up manner.**

Or a **one-sentence (1-mark) definition**:

> **Agglomerative Clustering is a bottom-up hierarchical clustering method in which each data point starts as an individual cluster and the closest clusters are repeatedly merged.**
---

# Key Idea

- **Type:** Hierarchical Clustering
- **Approach:** Bottom-up
- **Starts With:** One cluster for each data point
- **Ends With:** One cluster or the required number of clusters

---

# Algorithm

1. Treat every data point as a separate cluster.
2. Compute the distance between every pair of clusters.
3. Merge the two closest clusters.
4. Update the distance matrix using a linkage method.
5. Repeat Steps 3–4 until:
   - only one cluster remains, or
   - the desired number of clusters is reached.

---

# Mathematical Example

Suppose we have four one-dimensional data points.

| Point | Value |
|------|------:|
| A | 2 |
| B | 4 |
| C | 10 |
| D | 12 |

Initially,

```
{A} {B} {C} {D}
```

---

## Step 1: Calculate Distance Matrix

Using **Euclidean Distance**

\[
d(x,y)=|x-y|
\]

Distances are

\[
d(A,B)=|2-4|=2
\]

\[
d(A,C)=|2-10|=8
\]

\[
d(A,D)=|2-12|=10
\]

\[
d(B,C)=|4-10|=6
\]

\[
d(B,D)=|4-12|=8
\]

\[
d(C,D)=|10-12|=2
\]

Distance Matrix

| | A | B | C | D |
|---|---:|---:|---:|---:|
| **A** |0|2|8|10|
| **B** |2|0|6|8|
| **C** |8|6|0|2|
| **D** |10|8|2|0|

---

## Step 2: Merge Closest Clusters

The minimum distance is

\[
d(A,B)=2
\]

and

\[
d(C,D)=2
\]

Merge **A** and **B** first.

Clusters become

```
{AB} {C} {D}
```

---

## Step 3: Update Distances (Single Linkage)

Distance between cluster **AB** and **C**

\[
d(AB,C)=\min(d(A,C),d(B,C))
\]

\[
=\min(8,6)=6
\]

Distance between **AB** and **D**

\[
d(AB,D)=\min(10,8)=8
\]

Updated Distance Matrix

| | AB | C | D |
|---|---:|---:|---:|
| **AB** |0|6|8|
| **C** |6|0|2|
| **D** |8|2|0|

---

## Step 4: Merge C and D

Smallest distance

\[
d(C,D)=2
\]

Clusters become

```
{AB} {CD}
```

---

## Step 5: Final Merge

Using Single Linkage,

\[
d(AB,CD)
=
\min
(d(A,C),d(A,D),d(B,C),d(B,D))
\]

\[
=\min(8,10,6,8)=6
\]

Merge the remaining clusters

```
{ABCD}
```

The clustering process is complete.

---

# Simple Example

Suppose there are five objects.

```
A  B  C  D  E
```

Initially

```
{A} {B} {C} {D} {E}
```

Merge A and B

```
{AB} {C} {D} {E}
```

Merge D and E

```
{AB} {C} {DE}
```

Merge C with DE

```
{AB} {CDE}
```

Finally

```
{ABCDE}
```

---

# Dendrogram

```
             ABCD
            /    \
          AB      CD
         /  \    /  \
        A    B  C    D
```

A **dendrogram** is a tree-like diagram showing

- the order in which clusters merge,
- the hierarchy of clusters,
- the distance at which merging occurs.

The height of each branch represents the distance between merged clusters.

---

# Distance Measures

Agglomerative Clustering can use different distance metrics.

## 1. Euclidean Distance

Most common distance metric.

\[
d(x,y)=
\sqrt{\sum_{i=1}^{n}(x_i-y_i)^2}
\]

---

## 2. Manhattan Distance

\[
d(x,y)=
\sum |x_i-y_i|
\]

---

## 3. Cosine Distance

Measures the angle between two vectors.

Mostly used in document and text clustering.

---

## 4. Minkowski Distance

A generalized distance metric.

---

# Linkage Methods

After merging clusters, the distance between the new cluster and other clusters must be updated.

This is called the **linkage method**.

---

## 1. Single Linkage

Uses the **minimum distance**.

\[
d(A,B)=
\min(d(x,y))
\]

where

\[
x\in A,\qquad y\in B
\]

### Characteristics

- Nearest Neighbor
- Produces chain-like clusters
- Sensitive to noise

---

## 2. Complete Linkage

Uses the **maximum distance**.

\[
d(A,B)=
\max(d(x,y))
\]

### Characteristics

- Farthest Neighbor
- Produces compact clusters
- Less chaining effect

---

## 3. Average Linkage

Uses the average distance between all pairs.

\[
d(A,B)
=
\frac{1}{|A||B|}
\sum_{x\in A}
\sum_{y\in B}
d(x,y)
\]

### Characteristics

- Balanced clustering
- More stable than Single Linkage

---

## 4. Ward's Linkage

Chooses the merge that causes the **smallest increase in within-cluster variance (SSE).**

### Characteristics

- Produces compact clusters
- Most commonly used
- Good for spherical clusters

---

# Time and Space Complexity

| Complexity | Value |
|------------|--------|
| Time Complexity | **O(n³)** |
| Space Complexity | **O(n²)** |

Agglomerative Clustering is suitable for **small and medium-sized datasets**.

---

# Stopping Criteria

The algorithm stops when

- only one cluster remains,
- the desired number of clusters is obtained, or
- the dendrogram is cut at a selected height.

---

# Advantages

- Easy to understand and implement.
- No need to specify initial cluster centers.
- Produces a dendrogram.
- Works well for small and medium datasets.
- Can detect clusters of different shapes.
- No assumption about data distribution.

---

# Disadvantages

- Computationally expensive.
- Requires large memory.
- Sensitive to outliers.
- Merging cannot be undone.
- Depends on linkage method.

---

# Applications

- Customer Segmentation
- Document Clustering
- Image Segmentation
- Gene Expression Analysis
- Medical Diagnosis
- Social Network Analysis
- Recommendation Systems
- Market Research
- Pattern Recognition

---

# Real-Life Example

Suppose a teacher wants to group students according to their marks.

Initially

```
Student1
Student2
Student3
Student4
Student5
```

Each student forms an individual cluster.

The teacher repeatedly groups students having similar marks until all similar students are grouped together.

This is exactly how Agglomerative Clustering works.

---

# Agglomerative vs Divisive Clustering

| Agglomerative | Divisive |
|--------------|----------|
| Bottom-up | Top-down |
| Starts with individual clusters | Starts with one large cluster |
| Merges clusters | Splits clusters |
| More commonly used | Less commonly used |

---

# Summary

| Feature | Agglomerative Clustering |
|---------|---------------------------|
| Type | Hierarchical Clustering |
| Approach | Bottom-up |
| Starts With | Each data point as a separate cluster |
| Ends With | One cluster or desired number of clusters |
| Distance Measures | Euclidean, Manhattan, Cosine, Minkowski |
| Linkage Methods | Single, Complete, Average, Ward |
| Output | Hierarchical clusters and a dendrogram |
| Time Complexity | O(n³) |
| Space Complexity | O(n²) |
| Best For | Small and medium-sized datasets |

---

# Exam Definition

> **Agglomerative Clustering** is a **bottom-up hierarchical clustering algorithm** that starts with each data point as an individual cluster and repeatedly merges the two closest clusters using a distance metric and a linkage criterion until the desired number of clusters or a single cluster remains. The complete clustering process is represented by a **dendrogram**, which illustrates the hierarchy of cluster formation.

---

# Viva / Interview Questions

### 1. Why is Agglomerative Clustering called a bottom-up approach?

Because it starts with individual data points and gradually merges them into larger clusters.

---

### 2. What is the output of Agglomerative Clustering?

A hierarchy of clusters represented by a **dendrogram**.

---

### 3. Does Agglomerative Clustering require the number of clusters beforehand?

No. The full hierarchy is built first, and the desired number of clusters can be obtained by cutting the dendrogram.

---

### 4. Which linkage method is most commonly used?

**Ward's Linkage**, because it usually produces compact and balanced clusters.

---

### 5. What is a dendrogram?

A dendrogram is a tree-like diagram that shows the sequence and distance of cluster merges.

---

### 6. When should Agglomerative Clustering be used?

It is best suited for **small to medium-sized datasets** where hierarchical relationships among data points are important.
