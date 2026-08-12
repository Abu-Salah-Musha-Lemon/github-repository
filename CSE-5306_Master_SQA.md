# Software Quality Assurance & Testing (CSE-5306) — Model Answers

**Course:** M.Sc. in CSE (Professional), 3rd Semester Final Examination-2026 (17B), Jagannath University
**Reference:** Pressman, *Software Engineering: A Practitioner's Approach* (7th ed.)
**Total marks:** 60 (Answer any five of seven questions)

---

## Table of Contents
- [Question 1](#question-1)
- [Question 2](#question-2)
- [Question 3](#question-3)
- [Question 4](#question-4)
- [Question 5](#question-5)
- [Question 6](#question-6)
- [Question 7](#question-7)

---

## Question 1

### (a) What are the review metrics of FTR? Calculate the error density for a requirement model that contains 30 UML diagrams and the review uncovers 40 minor and 2 major errors. [5]

**Answer:**

A Formal Technical Review (FTR) is tracked using a set of review metrics that let a project team judge the effectiveness of its own review process over time. The commonly collected FTR metrics are:

- **Preparation time** — effort each reviewer spends studying the work product before the meeting.
- **Review (meeting) time** — total effort spent in the review meeting itself.
- **Product size** — size of the work product being reviewed (LOC, pages, number of diagrams/use-cases, function points, etc.).
- **Number of participants** (reviewers).
- **Number of minor errors found** — cosmetic or small technical issues.
- **Number of major errors found** — issues that would cause a fault/failure if left uncorrected.
- **Total errors found** = minor errors + major errors.
- **Error density** = Total errors found ÷ Product size — the key metric used to compare review effectiveness across work products and to decide whether a work product needs re-review.

**Calculation:**
```
Total errors  = minor errors + major errors = 40 + 2 = 42
Product size  = 30 UML diagrams
Error density = Total errors / Product size = 42 / 30 = 1.4 errors per UML diagram
```

So the requirement model has an error density of **1.4 errors per diagram**. This figure would then be compared with the project's/organisation's historical average error density to decide whether the requirement model is of acceptable quality or needs rework and a re-review.

### (b) What is SQA? Write down the difference between availability and reliability. [3]

**Answer:**

**Software Quality Assurance (SQA)** is a planned and systematic set of activities that ensures software processes and work products conform to established standards, procedures, and requirements. It provides management with the visibility needed to judge the quality of the product being built and includes activities such as applying technical methods, conducting formal technical reviews, performing software testing, enforcing standards, controlling change, measuring quality, and record-keeping/reporting.

| Aspect | Reliability | Availability |
|---|---|---|
| Definition | The probability that software will operate without failure under given conditions for a specified period of time. | The probability that a program is operating according to requirements at a given point in time. |
| Focus | Failure-free operation over a duration (MTTF-based). | Being "up and usable" at a specific instant (accounts for downtime/repair). |
| Formula | R(t) = e^(−λt), based on mean-time-to-failure (MTTF). | Availability = MTTF / (MTTF + MTTR) × 100% |
| Affected by | Failure rate only. | Both failure rate and mean-time-to-repair (MTTR). |

### (c) Can a program be correct yet unreliable? [2]

**Answer:**

Yes. Correctness and reliability are not the same thing. A program is **correct** if it satisfies its specification exactly — its output matches what the specification says it should produce for the inputs defined in that specification. **Reliability**, on the other hand, is about failure-free operation in actual use over time.

A program can be perfectly correct with respect to a specification and still be unreliable if the specification itself is incomplete, ambiguous, or does not anticipate the way users really exercise the software (unexpected inputs, timing, environment, hardware faults, etc.). In such cases the program behaves exactly as specified, yet still fails frequently from the user's point of view — hence it is **correct but unreliable**.

---

## Question 2

### (a) Define Cyclomatic Complexity. Determine the cyclomatic complexity of the given pseudo-code and draw its Control Flow Graph (CFG). [6]

**Answer:**

**Cyclomatic complexity** is a software metric (developed by Thomas McCabe) that provides a quantitative measure of the logical complexity of a program by counting the number of independent paths through its control flow graph. It is computed in one of three equivalent ways:

- V(G) = E − N + 2, where E = number of edges and N = number of nodes in the flow graph.
- V(G) = P + 1, where P = number of predicate (decision) nodes in the flow graph.
- V(G) = number of regions of the flow graph (when drawn as a planar graph).

**Flow graph nodes for the given pseudo-code:**

| Node | Statement |
|---|---|
| 1 | Start / Read x, y |
| 2 | IF (x > y) — predicate |
| 3 | IF (x > 0) — predicate |
| 4 | Print 'A' |
| 5 | Print 'B' |
| 6 | IF (y > 0) — predicate |
| 7 | Print 'C' |
| 8 | Print 'D' |
| 9 | Print 'End' |
| 10 | Stop |

The graph has **N = 10** nodes and **E = 12** edges (1→2, 2→3, 2→6, 3→4, 3→5, 6→7, 6→8, 4→9, 5→9, 7→9, 8→9, 9→10), and **P = 3** predicate nodes (nodes 2, 3, 6).

```
V(G) = E − N + 2 = 12 − 10 + 2 = 4
V(G) = P + 1     = 3 + 1       = 4      ✓ (both methods agree)
```

**Cyclomatic complexity V(G) = 4.** This means there are 4 linearly independent paths that form a basis set for the program:

- Path 1: 1-2-3-4-9-10 (x > y and x > 0 → Print A)
- Path 2: 1-2-3-5-9-10 (x > y and x ≤ 0 → Print B)
- Path 3: 1-2-6-7-9-10 (x ≤ y and y > 0 → Print C)
- Path 4: 1-2-6-8-9-10 (x ≤ y and y ≤ 0 → Print D)

**Control Flow Graph (CFG):**

```
                    ┌─────────────┐
                    │ 1. Start    │
                    │ Read x, y   │
                    └──────┬──────┘
                           │
                    ┌──────▼──────┐
                    │ 2. x > y ?  │
                    └──┬───────┬──┘
                    T  │       │  F
              ┌────────▼──┐ ┌─▼──────────┐
              │ 3. x > 0 ? │ │ 6. y > 0 ? │
              └─┬───────┬─┘ └─┬────────┬─┘
              T │       │ F T │        │ F
          ┌─────▼┐   ┌──▼────▼┐   ┌────▼─┐
          │4:PrintA│ │5:PrintB│ │7:PrintC│ │8:PrintD│
          └─────┬┘   └──┬─────┘   └────┬─┘ └───┬────┘
                └────────┴──────┬───────┴───────┘
                                 │
                          ┌──────▼──────┐
                          │ 9. Print End│
                          └──────┬──────┘
                                 │
                          ┌──────▼──────┐
                          │  10. Stop   │
                          └─────────────┘
```
*(See `SQA_Testing_Model_Answers.docx` for the rendered graphic version of this diagram.)*

### (b) Explain how Basis Path Testing utilizes cyclomatic complexity to generate independent test paths. [6]

**Answer:**

Basis path testing is a white-box test-design technique (also by McCabe) that uses cyclomatic complexity to derive a minimal, non-redundant set of test cases that guarantees every statement in a program is executed at least once. The procedure is:

1. **Draw the flow graph** — translate the code/design into nodes (sequential statement groups) and edges (flow of control).
2. **Compute V(G)** — using E − N + 2 or P + 1. This number tells the tester exactly how many independent paths must be tested — no more, no fewer.
3. **Determine the basis set of independent paths** — a set of V(G) paths such that each new path introduces at least one new edge not covered by previous paths. This basis set is the minimum number of paths that, together, traverse every edge in the graph at least once.
4. **Prepare test cases** — for each independent path in the basis set, choose input data that forces execution to follow exactly that path, and derive the expected result.
5. **Execute and verify** — run each test case and confirm that the observed path and output match the expected path and output.

Because V(G) equals the exact number of paths needed for full statement/branch coverage of the graph's basis set, cyclomatic complexity acts as both an upper bound on the number of test cases required and a quality/risk indicator — modules with high V(G) are structurally more complex, harder to test exhaustively, and statistically more error-prone, so they are prioritised for review and testing effort. For the pseudo-code above, V(G) = 4 means exactly 4 test cases (one per path shown earlier) form the basis set and together guarantee every node and edge is exercised at least once.

---

## Question 3

### (a) What are the overall strategies of software testing? [3]

**Answer:**

Pressman describes software testing as following a spiral that moves outward from small-scale to large-scale testing, generally in four strategic stages:

- **Unit testing** — concentrates on the smallest testable unit of the design (a module/class/function), verifying internal logic, interfaces, boundary conditions, and error handling in isolation, usually with the aid of drivers and stubs.
- **Integration testing** — focuses on the construction of the program structure while conducting tests to uncover errors associated with interfacing between modules (data passed across an interface, module combination side effects). Approaches include top-down, bottom-up, sandwich/hybrid, and "big bang" integration.
- **Validation testing** — provides assurance that the software meets all functional, behavioural, and performance requirements established in the requirements specification; typically culminates in alpha and beta testing with end users.
- **System testing** — verifies that all elements (software, hardware, people, databases) mesh properly and that overall system function/performance is achieved; includes recovery, security, stress, and performance testing.

As testing moves through these stages, scope broadens from a single component to the fully integrated system, and testing shifts from a white-box (structural) view to an increasingly black-box (behavioural) view.

### (b) Write down the difference between verification and validation. [3]

**Answer:**

| Aspect | Verification | Validation |
|---|---|---|
| Question answered | "Are we building the product right?" | "Are we building the right product?" |
| Focus | Checks conformance to specification/design at each phase (internal consistency). | Checks the finished product against actual customer/user requirements and needs. |
| Activities used | Reviews, walkthroughs, inspections, static analysis. | Actual execution/testing of the software (unit, integration, system, acceptance testing). |
| When performed | Throughout development, at the end of each phase. | Mainly after a build/increment is available, before delivery. |
| Type of check | Human-driven, largely static. | Machine/execution-driven, largely dynamic. |

### (c) What is integration testing? What are the steps of top-down integration? [6]

**Answer:**

**Integration testing** is a systematic technique for constructing the software architecture by combining unit-tested modules and testing the combination, with the specific objective of uncovering errors associated with the interfacing between modules — e.g. data lost across an interface, sub-functions that adversely affect each other when combined, imprecise interfacing, and global data-structure problems.

**Top-down integration steps:**

1. The main (top-level) control module is used as the test driver, and stubs are substituted for all modules directly subordinate to it.
2. Depending on the integration approach chosen (depth-first or breadth-first), subordinate stubs are replaced one at a time with the actual modules.
3. Tests are conducted as each individual module is integrated, to verify the newly integrated module and its interface with the modules above it.
4. On completion of each set of tests, another stub is replaced with the real module (regression tests may be re-run to ensure no new errors were introduced).
5. The process continues, integrating and testing module by module, until the full program structure is built and tested.

---

## Question 4

### (a) Which errors tend to be serious — client-side errors or server-side errors? Why? [4]

**Answer:**

**Server-side errors** tend to be the more serious of the two. This is because the server typically hosts the business logic, transaction processing, and access to persistent data (databases). A server-side fault can corrupt data, break a transaction for many concurrent users at once, expose security vulnerabilities, and take the whole WebApp down for every client simultaneously — the impact scales with the number of users hitting that server.

Client-side errors (e.g., a rendering glitch in one browser, a broken script on one page) are usually confined to the individual user's session/browser and are comparatively easier to detect, isolate, and work around (e.g., by switching browsers), so their impact is generally narrower and less severe than a server-side failure.

### (b) Describe the layers of interaction between a database and a WebApp. [4]

**Answer:**

A WebApp typically interacts with a database through a layered (tiered) architecture:

- **Presentation/Client layer** — the browser/UI where the user enters data or requests information; sends HTTP requests and renders HTML/CSS/JS responses.
- **Web/Application server layer** — hosts the WebApp's business logic (scripts, controllers, APIs); receives client requests, applies business rules, and formulates queries.
- **Middleware / data-access layer** — connectors, ORM frameworks, or driver APIs (e.g., JDBC/ODBC) that translate application calls into database queries and manage connections, pooling, and transactions.
- **Database server layer** — the DBMS itself, which stores, retrieves, and manages persistent data, enforces integrity constraints, and returns query results back up through the same layers to the client.

Each layer boundary is a potential source of interface errors, so WebApp testing must verify data integrity and correct behaviour as data passes across every layer boundary, not just within a single layer.

### (c) What are the testing strategies for WebApps? [4]

**Answer:**

- **Content testing** — checks for errors in text, graphics, and links (syntactic, semantic, or navigation errors) and validates content against the information architecture.
- **Interface testing** — verifies GUI/interface elements (forms, buttons, navigation menus) work correctly across the WebApp and comply with interface design conventions.
- **Navigation testing** — ensures every navigation path/mechanism (menus, links, redirects) functions correctly and every page/content object is reachable.
- **Component testing** — tests individual functional units of the WebApp (forms, search functions, database access, computational components) in isolation.
- **Configuration testing** — checks the WebApp's behaviour across different server configurations, operating systems, and browsers/browser versions.
- **Security testing** — attempts to exploit vulnerabilities in the WebApp, its data, or its configuration to verify security controls work as intended.
- **Performance testing** — includes load testing and stress testing to evaluate response time, throughput, and behaviour under normal and peak traffic conditions.

---

## Question 5

### (a) What is Halstead complexity? Find the Halstead complexity of the given code. [5]

**Answer:**

**Halstead complexity** (Halstead's software science) is a set of measures that estimate program complexity, size, and effort directly from the source code, based only on the counted number of operators and operands. The base counts are:

- n1 = number of distinct (unique) operators
- n2 = number of distinct (unique) operands
- N1 = total number of operator occurrences
- N2 = total number of operand occurrences

**Identifying operators and operands in the given program:**

| Operators (n1 = 14) | Count | Operands (n2 = 7) | Count |
|---|---|---|---|
| `int` | 2 | `a` | 4 |
| `main` | 1 | `b` | 4 |
| `(` | 4 | `sum` | 3 |
| `)` | 4 | `"Enter two integers: "` | 1 |
| `{` | 1 | `"%d %d"` | 1 |
| `}` | 1 | `"%d + %d = %d"` | 1 |
| `,` | 7 | `0` | 1 |
| `;` | 6 | | |
| `printf` | 2 | | |
| `scanf` | 1 | | |
| `&` | 2 | | |
| `=` | 1 | | |
| `+` | 1 | | |
| `return` | 1 | | |

So **N1 = 34** and **N2 = 15**. Now compute the Halstead measures:

```
Vocabulary        n  = n1 + n2 = 14 + 7 = 21
Program length     N  = N1 + N2 = 34 + 15 = 49
Volume             V  = N × log2(n) = 49 × log2(21) ≈ 49 × 4.39 ≈ 215.2
Difficulty         D  = (n1/2) × (N2/n2) = (14/2) × (15/7) = 7 × 2.14 ≈ 15.0
Effort             E  = D × V ≈ 15.0 × 215.2 ≈ 3228
Time to program     T  = E / 18 ≈ 3228 / 18 ≈ 179 seconds ≈ 3 minutes
Delivered bugs      B  = V / 3000 ≈ 215.2 / 3000 ≈ 0.07 bugs
```

*Note: exact figures can shift slightly depending on whether the tester chooses to count paired tokens such as `()` or `{}` as one operator or two — the method shown above (splitting each token) is the standard convention; the key deliverable in an exam is the correct **method** (n1, n2, N1, N2 → V, D, E, T, B), not a single "exact" number.*

### (b) Describe alpha testing and beta testing. What benefits can be derived from smoke testing? [6]

**Answer:**

**Alpha testing** is conducted at the developer's site by a representative set of end users, in a controlled environment, with the developer present to record errors and usage problems as they occur. Because the developer is "looking over the shoulder" of the user, problems are found and fixed quickly, but the environment is not fully representative of real-world use.

**Beta testing** is conducted at one or more end-user (customer) sites, without the developer present. The customer records and reports all problems encountered during beta testing to the developer at regular intervals. Because the software is exercised in an actual, uncontrolled operating environment, beta testing exposes errors that neither the developer nor the alpha testers were likely to find.

**Smoke testing** is an integration approach in which each newly available build (a set of integrated modules) is tested with a broad but shallow set of tests designed to expose "showstopper" errors that are likely to hold up further progress. Benefits derived from smoke testing include:

- **Integration risk is minimised** — components/subsystems are tested and integrated early and continuously, rather than in one "big bang" at the end.
- The **quality of the final, fully-integrated product is improved** because major defects are caught early.
- **Error diagnosis and correction are simplified** — since only recently added components could have introduced a newly discovered failure.
- **Progress is easier to assess** — daily/frequent successful builds give management a concrete, measurable indicator of project progress.

---

## Question 6

### (a) Describe McCall's quality factors. [6]

**Answer:**

McCall's quality model organises software quality into three broad perspectives — product operation, product revision, and product transition — and defines eleven quality factors under them:

**Product Operation (how well it operates):**
- **Correctness** — the extent to which a program satisfies its specification and fulfils the customer's mission objectives.
- **Reliability** — the extent to which a program performs its intended function with the required precision, without failure.
- **Efficiency** — the amount of computing resources and code required by a program to perform its function.
- **Integrity** — the extent to which access to software or data by unauthorised persons can be controlled.
- **Usability** — the effort required to learn, operate, prepare input for, and interpret output from a program.

**Product Revision (how well it can be changed):**
- **Maintainability** — the effort required to locate and fix an error in the program.
- **Flexibility** — the effort required to modify an operational program.
- **Testability** — the effort required to test a program to ensure it performs its intended function.

**Product Transition (how well it adapts to new environments):**
- **Portability** — the effort required to transfer a program from one hardware/software environment to another.
- **Reusability** — the extent to which a program (or parts of it) can be reused in other applications.
- **Interoperability** — the effort required to couple one system with another.

Direct measurement of these factors is difficult, so McCall defines each in terms of measurable software metrics (e.g., complexity, modularity, self-documentation), and the factors themselves influence one another — improving one (e.g., efficiency) can degrade another (e.g., portability or maintainability), so quality management is ultimately about balancing trade-offs among these factors.

### (b) Error amplification / propagation problem [6]

**Answer:**

**(i) No reviews conducted:**

| Phase | Errors carried in (amplified) | New errors introduced | Total present |
|---|---|---|---|
| Requirements | — | 30 | 30 |
| Design | 30 × 2 = 60 | 30 | 90 |
| Code | 90 × 2 = 180 | 40 | 220 |

With 220 total errors present at the start of testing, and no reviews conducted, errors are removed only by testing:

```
Unit testing (30%):        220 × 0.30 = 66 found   → remaining = 220 − 66  = 154
Integration testing (30%): 154 × 0.30 = 46.2 found → remaining = 154 − 46.2 = 107.8
Validation testing (50%):  107.8 × 0.50 = 53.9 found → remaining = 107.8 − 53.9 = 53.9
```

**≈ 54 errors are released to the field.**

**(ii) Requirements, design and code reviews conducted, each 80% effective:**

| Phase | Errors entering phase | Errors present in phase | Caught by review (80%) | Escapes phase |
|---|---|---|---|---|
| Requirements | — | 30 | 30 × 0.8 = 24 | 6 |
| Design | 6 × 2 = 12 (+30 new) | 42 | 42 × 0.8 = 33.6 | 8.4 |
| Code | 8.4 × 2 = 16.8 (+40 new) | 56.8 | 56.8 × 0.8 = 45.44 | 11.36 |

Only 11.36 errors now enter testing:

```
Unit testing (30%):        11.36 × 0.30 = 3.41 found  → remaining ≈ 7.95
Integration testing (30%): 7.95 × 0.30 = 2.39 found   → remaining ≈ 5.57
Validation testing (50%):  5.57 × 0.50 = 2.78 found   → remaining ≈ 2.78
```

**≈ 3 errors are released to the field.**

*This dramatic drop (from ≈54 down to ≈3 field-released errors) is exactly the point Pressman makes with this kind of example: conducting effective reviews at the requirements, design, and code stages catches errors close to where they are introduced, before they can be amplified by later phases — making reviews one of the highest-leverage quality-assurance activities available.*

---

## Question 7

### (a) What is Risk-Based Testing? Describe its process. [4]

**Answer:**

**Risk-based testing (RBT)** is a testing strategy that prioritises test design and execution according to the level of risk associated with different parts of the software — features or components that carry higher probability of failure and/or higher impact of failure receive more, and earlier, testing attention than low-risk areas. It allows limited testing time/resources to be allocated where they matter most.

**Typical risk-based testing process:**

1. **Risk identification** — list the features, components, or requirements and the ways each could fail (technical risks, business risks).
2. **Risk assessment/analysis** — estimate, for each identified risk, its probability of occurrence and impact/severity if it does occur.
3. **Risk prioritisation** — rank items by risk exposure (probability × impact) to build a risk table, ordering items from highest to lowest risk.
4. **Test planning** — allocate testing effort, depth, and test-case count proportional to each item's risk ranking; design more rigorous tests for high-risk items.
5. **Test execution** — execute tests starting with the highest-risk items first, so that the most damaging defects are found as early as possible.
6. **Monitoring and reassessment** — as testing proceeds and new information emerges, risks are re-evaluated and the test plan adjusted accordingly.

### (b) A project contains 250 modules; 8% are defective. Automated testing detects 85% of defects. Calculate expected defective, detected, and undetected modules. [4]

**Answer:**

```
Total modules             = 250
Defective modules         = 250 × 8%  = 250 × 0.08 = 20 modules
Detected defective mods   = 20 × 85% = 20 × 0.85  = 17 modules
Undetected defective mods = 20 − 17            = 3 modules
```

So the project is expected to have **20 defective modules**, of which automated testing detects **17**, leaving **3 defective modules undetected** (escaping into later stages or production).

### (c) Explain how risk-based testing improves testing efficiency. [4]

**Answer:**

- **Focused effort** — testing time and resources are concentrated on the components most likely to fail and/or most damaging if they fail, instead of being spread evenly (and thus thinly) across the whole system.
- **Earlier discovery of critical defects** — high-risk areas are tested first, so the most severe defects surface early, when they are cheaper and easier to fix.
- **Better use of limited time** — under tight schedules, RBT ensures that even if not everything can be tested exhaustively, the areas that matter most are covered, maximising defect detection per unit of testing effort.
- **Objective prioritisation** — a documented risk table gives the team and stakeholders a transparent, defensible basis for deciding what to test first, what to test less, and what (low-risk) areas can be deferred or skipped.
- **Reduced overall project risk** — by systematically addressing the highest-risk items first, the probability of a serious, late-discovered failure reaching production is significantly reduced.

---

*— End of Answers —*
