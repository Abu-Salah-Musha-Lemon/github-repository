# Chi-Square Test to Identify the Most Significant Feature

## Given Dataset

| Age Group | Gender | Smoker | Health Status |
|-----------|--------|---------|---------------|
| Young | Male | Yes | Good |
| Middle | Female | No | Good |
| Young | Female | Yes | Poor |
| Elderly | Male | No | Poor |
| Middle | Male | Yes | Good |

**Target Variable:** Health Status

The goal is to determine which feature (**Age Group**, **Gender**, or **Smoker**) has the strongest relationship with the target variable (**Health Status**) using the **Chi-Square Test of Independence**.

---

# Step 1: Chi-Square Formula

The Chi-Square statistic is calculated using the following formula:

$$
\chi^2=\sum \frac{(O-E)^2}{E}
$$

Where:

- \(O\) = Observed Frequency
- \(E\) = Expected Frequency

The expected frequency is calculated as:

$$
E=\frac{(\text{Row Total})\times(\text{Column Total})}{\text{Grand Total}}
$$

---

# Step 2: Feature 1 — Smoker

## Contingency Table

| Smoker | Good | Poor | Total |
|---------|------|------|-------|
| Yes | 2 | 1 | 3 |
| No | 1 | 1 | 2 |
| **Total** | **3** | **2** | **5** |

### Calculate Expected Frequencies

For **Yes–Good**

$$
E=\frac{3\times3}{5}=1.8
$$

For **Yes–Poor**

$$
E=\frac{3\times2}{5}=1.2
$$

For **No–Good**

$$
E=\frac{2\times3}{5}=1.2
$$

For **No–Poor**

$$
E=\frac{2\times2}{5}=0.8
$$

### Expected Frequency Table

| Smoker | Good | Poor |
|---------|------|------|
| Yes | 1.8 | 1.2 |
| No | 1.2 | 0.8 |

### Chi-Square Calculation

$$
\chi^2=
\frac{(2-1.8)^2}{1.8}
+\frac{(1-1.2)^2}{1.2}
+\frac{(1-1.2)^2}{1.2}
+\frac{(1-0.8)^2}{0.8}
$$

$$
=0.022+0.033+0.033+0.050
$$

$$
\boxed{\chi^2=0.138}
$$

---

# Step 3: Feature 2 — Gender

## Contingency Table

| Gender | Good | Poor | Total |
|---------|------|------|-------|
| Male | 2 | 1 | 3 |
| Female | 1 | 1 | 2 |
| **Total** | **3** | **2** | **5** |

### Expected Frequencies

| Gender | Good | Poor |
|---------|------|------|
| Male | 1.8 | 1.2 |
| Female | 1.2 | 0.8 |

### Chi-Square Calculation

$$
\chi^2=
\frac{(2-1.8)^2}{1.8}
+\frac{(1-1.2)^2}{1.2}
+\frac{(1-1.2)^2}{1.2}
+\frac{(1-0.8)^2}{0.8}
$$

$$
=0.022+0.033+0.033+0.050
$$

$$
\boxed{\chi^2=0.138}
$$

---

# Step 4: Feature 3 — Age Group

## Contingency Table

| Age Group | Good | Poor | Total |
|------------|------|------|-------|
| Young | 1 | 1 | 2 |
| Middle | 2 | 0 | 2 |
| Elderly | 0 | 1 | 1 |
| **Total** | **3** | **2** | **5** |

### Calculate Expected Frequencies

For **Young**

$$
E_{\text{Good}}=\frac{2\times3}{5}=1.2
$$

$$
E_{\text{Poor}}=\frac{2\times2}{5}=0.8
$$

For **Middle**

$$
E_{\text{Good}}=1.2,\qquad
E_{\text{Poor}}=0.8
$$

For **Elderly**

$$
E_{\text{Good}}=0.6,\qquad
E_{\text{Poor}}=0.4
$$

### Expected Frequency Table

| Age Group | Good | Poor |
|------------|------|------|
| Young | 1.2 | 0.8 |
| Middle | 1.2 | 0.8 |
| Elderly | 0.6 | 0.4 |

### Chi-Square Calculation

$$
\chi^2=
\frac{(1-1.2)^2}{1.2}
+\frac{(1-0.8)^2}{0.8}
+\frac{(2-1.2)^2}{1.2}
+\frac{(0-0.8)^2}{0.8}
+\frac{(0-0.6)^2}{0.6}
+\frac{(1-0.4)^2}{0.4}
$$

$$
=0.033+0.050+0.533+0.800+0.600+0.900
$$

$$
\boxed{\chi^2=2.916}
$$

---

# Step 5: Comparison of Chi-Square Values

| Feature | Chi-Square Value |
|----------|-----------------:|
| **Age Group** | **2.916** |
| **Gender** | **0.138** |
| **Smoker** | **0.138** |

---

# Step 6: Interpretation

The **Chi-Square Test** measures the strength of association between a feature and the target variable.

A **higher Chi-Square value** indicates a stronger relationship between the feature and the target variable.

From the calculations:

- **Age Group = 2.916**
- **Gender = 0.138**
- **Smoker = 0.138**

Since **Age Group** has the highest Chi-Square value, it has the strongest association with **Health Status**.

---

# Final Answer

The most significant feature is **Age Group** because it has the highest Chi-Square statistic.

$$
\boxed{\textbf{Most Significant Feature = Age Group}}
$$

**Conclusion:**

Age Group has the strongest relationship with **Health Status** among the three features and is therefore the most informative feature for predicting the target variable.
