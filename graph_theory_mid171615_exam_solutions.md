# Comprehensive Solutions to CSE Graph Theory Examination Questions

**Course Code:** CSE-5306  
**Course Name:** Special Topics Related to Computer Science (Graph Theory)  
**Institution:** Jagannath University, Department of Computer Science & Engineering  

---

## 1. Fundamental Concepts & Theoretical Definitions

### 1.1 What is Graph Theory?
**Graph Theory** is a branch of discrete mathematics and computer science that studies graphs—mathematical structures used to model pairwise relations between objects. A graph $G = (V, E)$ consists of:
*   **$V$ (Vertices/Nodes):** A set of points or entities.
*   **$E$ (Edges/Links):** A set of lines connecting pairs of vertices.

### 1.2 Application Areas of Graph Theory
1. **Network Routing:** Packet routing algorithms in telecommunication networks (e.g., OSFP, BGP).
2. **Social Network Analysis:** Mapping relationships, community detection, and influence flow.
3. **Transportation & Navigation:** Finding optimal delivery or travel paths using GPS applications.
4. **Compiler Design:** Control Flow Graphs (CFG) and register allocation.
5. **Chemical Bond Modeling:** Atoms are modeled as vertices, and covalent/ionic bonds are modeled as weighted or multi-edges.

---

### 1.3 Chemical Bond Modeling
In chemistry, graph theory represents molecular structures (molecular graphs):
* **Vertices:** Represent individual atoms (e.g., Carbon, Hydrogen).
* **Edges:** Represent chemical bonds between atoms.
* **Edge Weights / Multi-edges:** Represent bond types (single, double, or triple bonds).

**Example (Ethene $C_2H_4$):**
```
  H       H
   \     /
    C = C
   /     \
  H       H
```

---

### 1.4 Short Definitions
* **Degree of a Vertex ($deg(v)$):** The total number of edges connected to a vertex $v$.
* **In-degree ($deg^-(v)$):** The number of incoming edges directed towards vertex $v$ in a directed graph.
* **Out-degree ($deg^+(v)$):** The number of outgoing edges leaving vertex $v$ in a directed graph.
* **Isolated Vertex:** A vertex with degree $0$ ($deg(v) = 0$).
* **Pendant Vertex:** A vertex with degree $1$ ($deg(v) = 1$).
* **Connected Graph:** A graph where a path exists between every pair of vertices.
* **Complete Graph ($K_n$):** A simple undirected graph with $n$ vertices where every pair of distinct vertices is connected by a unique edge. Total edges $E = \frac{n(n-1)}{2}$.
* **Wheel Graph ($W_n$):** A graph formed by connecting a central hub vertex to all $n$ vertices of a cycle graph $C_n$. Total vertices $= n + 1$.
* **Pseudograph:** A graph that permits self-loops (edges from a node to itself) and parallel/multiple edges.
* **Hypercube ($Q_n$):** An $n$-dimensional cube graph. It has $V = 2^n$ vertices and $E = n \cdot 2^{n-1}$ edges.
* **Partial Ordering:** A binary relation $\le$ on a set that is **reflexive** ($a \le a$), **antisymmetric** ($a \le b \land b \le a \implies a = b$), and **transitive** ($a \le b \land b \le c \implies a \le c$).

---

## 2. Depth-First Search (DFS) & Edge Classification

### 2.1 DFS Algorithm Overview
Depth-First Search (DFS) traverses a graph by going deeper along each path before backtracking. For each vertex $u$, DFS maintains two timestamps:
1. **$d[u]$ (Discovery Time):** The counter value when node $u$ is first discovered.
2. **$f[u]$ (Finishing Time):** The counter value when node $u$'s adjacency list has been fully explored.

### 2.2 Classification of Edges
* **Tree Edge:** An edge $(u, v)$ where $v$ is discovered for the first time during the traversal from $u$.
* **Back Edge:** An edge $(u, v)$ connecting $u$ to an ancestor $v$ in the DFS tree (indicates a cycle).
* **Forward Edge:** A non-tree edge $(u, v)$ connecting $u$ to a descendant $v$ in the DFS tree.
* **Cross Edge:** Any other edge $(u, v)$ connecting vertices that are neither ancestors nor descendants.

---

### 2.3 DFS Worked Example (Image 1 Graph)

**Graph Structure:**

```
          [9/12] S -------------> D [10/13] ---------> F [15/16]
          ^  \                   / ^                 / |
         /    \                 /  |                /  |
        /      v               v   |               v   v
    [11/14] A -> B -----------> C   +------------ E -> G
               [2/13]         [5/6]             [3/8]  [4/7]
```

#### Traversal Order starting from Node A:

| Node | Discovery Time ($d$) | Finishing Time ($f$) | Timestamp Notation ($d/f$) |
| :---: | :---: | :---: | :---: |
| **A** | 1 | 16 | $1/16$ |
| **B** | 2 | 15 | $2/15$ |
| **S** | 3 | 14 | $3/14$ |
| **D** | 4 | 13 | $4/13$ |
| **C** | 5 | 6 | $5/6$ |
| **E** | 7 | 12 | $7/12$ |
| **G** | 8 | 9 | $8/9$ |
| **F** | 10 | 11 | $10/11$ |

#### Edge Classification:
* **Tree Edges:** $(A, B)$, $(B, S)$, $(S, D)$, $(D, C)$, $(D, E)$, $(E, G)$, $(E, F)$
* **Forward Edges:** $(A, S)$, $(F, G)$
* **Back Edges:** None
* **Cross Edges:** $(B, C)$, $(S, E)$

---

## 3. Topological Sorting

### 3.1 Definition
Topological sort is a linear ordering of vertices in a Directed Acyclic Graph (DAG) such that for every directed edge $u \to v$, vertex $u$ comes before vertex $v$ in the ordering.

---

### 3.2 Problem Solution: Morning Getting Dressed Schedule

**Task Dependencies:**
* `undershorts` $\to$ `pants`, `shoes`
* `pants` $\to$ `belt`, `shoes`
* `shirt` $\to$ `belt`, `tie`
* `socks` $\to$ `shoes`
* `belt` $\to$ `jacket`
* `tie` $\to$ `jacket`
* `watch` (independent)

```
[undershorts] ----> [pants] ----> [belt] ----> [jacket]
      |               |             ^              ^
      v               v             |              |
   [shoes] <------- [socks]      [shirt] --------> [tie]

                            [watch]
```

#### Step-by-Step Resolution:
1. Vertices with in-degree $0$: `undershorts`, `socks`, `shirt`, `watch`.
2. Process `watch`, `socks`, `undershorts`.
3. Process `pants`, `shirt`.
4. Process `tie`, `belt`.
5. Process `shoes`, `jacket`.

#### Valid Topological Order:
$$\text{watch} \longrightarrow \text{socks} \longrightarrow \text{undershorts} \longrightarrow \text{pants} \longrightarrow \text{shirt} \longrightarrow \text{tie} \longrightarrow \text{belt} \longrightarrow \text{shoes} \longrightarrow \text{jacket}$$

---

### 3.3 Problem Solution: CSE Course Prerequisite Enrollment

**Prerequisite Graph:**

```
[Computer Fundamentals] ---> [Structure Programming] ---> [OOP-C++] ---> [OOP-JAVA] ---> [DBMS] ---> [Software Engineering]
[Basic Electronics] ---> [Discrete Mathematics] ---> [Microprocessor] ---> [Architecture]
```

#### Topological Order of Courses:
1. Computer Fundamentals
2. Structure Programming
3. Basic Electronics
4. Discrete Mathematics
5. OOP-C++
6. Microprocessor
7. OOP-JAVA
8. Architecture
9. DBMS
10. Software Engineering

---

## 4. Minimum Spanning Tree (MST) - Kruskal's Algorithm

### 4.1 Definition
A Minimum Spanning Tree (MST) of an edge-weighted connected graph is a spanning tree whose total edge weight is minimized.

### 4.2 Kruskal's Algorithm Steps
1. Sort all edges in non-decreasing order of weight.
2. Initialize an empty tree.
3. Iterate through sorted edges and add an edge if it does not form a cycle with already selected edges.
4. Stop when $V - 1$ edges are added.

---

### 4.3 Detailed Execution for Cable Connection Network (Image 1)

```
        10          F --- 6 --- C
    A -------- B   / \         / \
   / \        /|  /   \ 7     / 9 \
  5   5      7 | 6     \     /     D
 /     \    /  |/       \   /     /
H ---3--- G ---5--- E ---10--    25
```

#### Sorted Edge List:

| Rank | Edge | Weight | Action | Explanation |
| :---: | :---: | :---: | :---: | :---: |
| 1 | $(G, H)$ | 3 | **Selected** | Connects $G$ and $H$ |
| 2 | $(A, H)$ | 5 | **Selected** | Connects $A$ to $H$ |
| 3 | $(A, B)$ | 5 | **Selected** | Connects $B$ to $A$ |
| 4 | $(B, D)$ | 5 | **Selected** | Connects $D$ to $B$ |
| 5 | $(G, E)$ | 5 | **Selected** | Connects $E$ to $G$ |
| 6 | $(F, C)$ | 6 | **Selected** | Connects $F$ and $C$ |
| 7 | $(F, G)$ | 6 | **Selected** | Connects component $\{F, C\}$ to main tree |
| 8 | $(B, F)$ | 7 | **Rejected** | Forms cycle $B-A-H-G-F-B$ |
| 9 | $(B, C)$ | 7 | **Rejected** | Forms cycle $B-F-C$ |
| 10 | $(C, D)$ | 9 | **Rejected** | Forms cycle $C-F-G-E\dots$ |
| 11 | $(A, F)$ | 10 | **Rejected** | Forms cycle |
| 12 | $(B, E)$ | 10 | **Rejected** | Forms cycle |
| 13 | $(D, E)$ | 25 | **Rejected** | Forms cycle |

#### Minimum Spanning Tree Edges:
$$\text{MST Edges} = \{(G,H), (A,H), (A,B), (B,D), (G,E), (F,C), (F,G)\}$$

#### Total Minimum Cable Weight:
$$\text{Total Weight} = 3 + 5 + 5 + 5 + 5 + 6 + 6 = \mathbf{35}$$

---

## 5. All-Pairs Shortest Path & Single-Source Shortest Path

### 5.1 Concept Overview
* **Single-Source Shortest Path (SSSP):** Finds the shortest paths from a single starting vertex to all other vertices (solved via Dijkstra's Algorithm in $O(E \log V)$ time).
* **All-Pairs Shortest Path (APSP):** Finds the shortest path between every pair of vertices in the graph (solved via Floyd-Warshall Algorithm in $O(V^3)$ time).

---

### 5.2 Shortest Delivery Route from Node A

```
        (A)
       /   \
      5     3
     /       \
   (C)---6---(B)
    | \     / |
    4  3   1  4
    |   \ /   |
   (E)---4---(D)
```

#### Distance Calculation from Node A:

* Path to **B**: $A \to B$  
  $$\text{Distance} = 3$$

* Path to **C**: $A \to C$  
  $$\text{Distance} = 5$$

* Path to **E**: $A \to B \to E$  
  $$\text{Distance} = 3 + 1 = 4$$

* Path to **D**: $A \to B \to E \to D$  
  $$\text{Distance} = 3 + 1 + 4 = 8$$

---

## 6. Graph Representations

### 6.1 Adjacency Matrix Representation
An adjacency matrix $M$ for a graph with $n$ vertices is an $n \times n$ matrix where:
$$M[i][j] = \begin{cases} 1 & \text{if there is an edge from vertex } i \text{ to vertex } j \\ 0 & \text{otherwise} \end{cases}$$

Given Matrix:
$$M = \begin{pmatrix}
 & \mathbf{X} & \mathbf{Y} & \mathbf{Z} & \mathbf{W} & \mathbf{T} \\
\mathbf{X} & 1 & 1 & 0 & 0 & 1 \\
\mathbf{Y} & 0 & 1 & 0 & 0 & 1 \\
\mathbf{Z} & 0 & 0 & 0 & 0 & 1 \\
\mathbf{W} & 1 & 1 & 1 & 0 & 0 \\
\mathbf{T} & 1 & 1 & 1 & 0 & 0
\end{pmatrix}$$

#### Direct Node Connections:
* **Node X:** Self-loop $(X \to X)$, directed edges to $Y$ and $T$.
* **Node Y:** Self-loop $(Y \to Y)$, directed edge to $T$.
* **Node Z:** Directed edge to $T$.
* **Node W:** Directed edges to $X$, $Y$, and $Z$.
* **Node T:** Directed edges to $X$, $Y$, and $Z$.

---

### 6.2 Adjacency List Representation
An adjacency list represents a graph as an array of linked lists, where each index contains a list of vertices reachable from that vertex.

**Flight Schedule Adjacency List:**
* **Dhaka** $\longrightarrow$ Chittagong, Sylhet, Rajshahi
* **Chittagong** $\longrightarrow$ Dhaka, Barisal
* **Sylhet** $\longrightarrow$ Chittagong, Khulna
* **Rajshahi** $\longrightarrow$ Khulna, Dhaka
* **Khulna** $\longrightarrow$ Barisal
* **Barisal** $\longrightarrow$ $\emptyset$ (sink node)

---

## 7. Special Graph Structures

### 7.1 Complete Graph $K_5$
Vertices $= 5$, Total Edges $= \frac{5 \times 4}{2} = 10$.

```
       (1)
      / | \
    (5) |  (2)
   / \  |  / \
  /   \ | /   \
(4)----(3)----(2)
```

### 7.2 Wheel Graph $W_5$
Vertices $= 6$ (1 Hub + 5 Cycle nodes), Edges $= 10$.

```
        (C)
      / /|\ \
    (1)(2)(3)(4)
     \  | |  /
       \(5)/
```

### 7.3 Hypercube Graph $Q_3$
Vertices $= 2^3 = 8$, Edges $= 3 \cdot 2^{3-1} = 12$.

```
   (011)-------(111)
   / |         / |
(001)-------(101)|
  | (010)----|--(110)
  | /        | /
(000)-------(100)
```