# Vanguard UI Redesign — A/B Test & Product Analytics

A collaborative product analytics project evaluating whether a redesigned digital investment platform improved the customer journey compared with the existing interface.

The project combines data cleaning, customer journey reconstruction, KPI development, statistical hypothesis testing and Tableau visualization to assess both the statistical and practical impact of the redesign.

---

## Project Overview

Vanguard introduced a redesigned digital experience and conducted an A/B test to evaluate its performance:

* **Control group:** existing interface
* **Test group:** redesigned interface

The objective was not simply to determine whether the Test group performed differently, but to assess whether the redesign produced a statistically reliable and practically meaningful improvement.

The analysis focused on:

* Completion rate
* Process friction
* Backtracking behavior
* Repeated steps
* Completion time
* Events required to complete the process

---

## Business Questions

The project addressed the following questions:

1. Did the redesigned interface increase the proportion of users who completed the process?
2. Was the improvement statistically significant?
3. Did the increase exceed a minimum practical threshold of five percentage points?
4. Did the redesign reduce friction and abandonment?
5. Did users complete the process more efficiently?
6. Did the new interface reduce backtracking and repeated interactions?
7. Based on the complete set of results, should the redesigned experience be implemented?

---

## Dataset

The analysis combined three main types of data:

* **Customer profiles:** demographic and account-related information
* **Experiment assignments:** identification of Control and Test users
* **Digital interaction logs:** timestamped user activity across the different process steps

The interaction data was transformed from event-level records into session- and user-level metrics suitable for funnel analysis and statistical testing.

---

## Analysis Workflow

### 1. Data Cleaning and Preparation

The raw files were inspected, cleaned and standardized before analysis.

The main preparation steps included:

* Handling missing and inconsistent values
* Standardizing column names and data types
* Combining the digital interaction files
* Connecting customer records with experiment assignments
* Ordering events chronologically
* Reconstructing individual user journeys
* Creating analysis-ready datasets for EDA and A/B testing

### 2. Customer Journey Reconstruction

Each interaction was assigned to a stage of the digital process:

```text
Start → Step 1 → Step 2 → Step 3 → Confirm
```

The reconstructed journeys made it possible to identify:

* Successful completions
* Abandonment
* Backward navigation
* Repeated steps
* Number of events per session
* Time required to complete the process

### 3. KPI Development

The following KPIs were created:

| KPI                          | Definition                                                      |
| ---------------------------- | --------------------------------------------------------------- |
| Completion Rate              | Percentage of started journeys that reached confirmation        |
| Friction Rate                | Percentage of journeys showing abandonment or navigation issues |
| Backtracking Rate            | Percentage of journeys in which users moved to an earlier step  |
| Repeated Steps Rate          | Percentage of journeys containing repeated interactions         |
| Median Completion Time       | Median time required to reach confirmation                      |
| Median Events per Completion | Median number of interactions required to complete              |

### 4. Statistical Testing

Different statistical tests were selected according to the type of KPI:

* **Two-proportion z-tests** for completion, friction, backtracking and repeated-step rates
* **Mann–Whitney U tests** for completion time and event-count comparisons

A significance level of **α = 0.05** was used.

The completion-rate analysis also included a practical business threshold:

> The Test group needed to improve completion by more than five percentage points, not merely produce a statistically detectable difference.

---

## Main Results

### Completion Rate

| Group   | Completion Rate |
| ------- | --------------: |
| Control |          48.26% |
| Test    |          54.07% |

The redesigned interface increased completion by **5.81 percentage points**.

The result was statistically significant:

```text
p < 0.0001
```

The improvement also exceeded the predefined five-percentage-point practical threshold:

```text
p = 0.0202
```

This indicates that the Test group achieved both a statistically reliable and practically meaningful improvement in the main success metric.

### Friction Rate

| Group   | Friction Rate |
| ------- | ------------: |
| Control |        69.38% |
| Test    |        68.05% |

The Test group reduced the broad friction rate by approximately **1.32 percentage points**.

The difference was statistically significant:

```text
p = 0.0002
```

However, the reduction was relatively small and appears to have been driven mainly by lower abandonment rather than by a consistently smoother navigation path.

### Backtracking

| Group   | Backtracking Rate |
| ------- | ----------------: |
| Control |            20.57% |
| Test    |            29.77% |

Backtracking increased by approximately **9.20 percentage points** in the Test group.

The redesign therefore did not improve this metric. The result suggests that more Test users returned to earlier stages of the process.

### Repeated Steps

| Group   | Repeated Steps Rate |
| ------- | ------------------: |
| Control |              37.80% |
| Test    |              47.35% |

Repeated steps increased by approximately **9.55 percentage points** in the Test group.

This may indicate uncertainty, unclear navigation or additional interaction with certain parts of the redesigned process.

### Completion Time

| Group   | Median Completion Time |
| ------- | ---------------------: |
| Control |           4.52 minutes |
| Test    |           3.95 minutes |

Users who completed the process in the Test group did so approximately **0.57 minutes faster**.

The difference was statistically significant:

```text
p < 0.0001
```

### Events per Completed Journey

Both groups required a median of:

```text
5 events
```

The redesign did not reduce the number of interactions required to complete the process.

---

## Business Interpretation

The redesigned interface produced a clear improvement in the primary business outcome:

* More users completed the process.
* The completion-rate increase exceeded the predefined practical threshold.
* Successful Test users completed the journey faster.
* Overall friction decreased slightly.

However, the redesign did not improve every aspect of the experience:

* Backtracking increased.
* Repeated steps increased.
* The number of events required for completion remained unchanged.

The evidence therefore supports a **conditional implementation**, rather than an unqualified conclusion that the new interface was better in every respect.

### Recommendation

The redesign could be adopted because it improved completion and reduced completion time, but the steps associated with backward navigation and repeated interactions should be investigated and refined.

A sensible next step would be to:

1. Identify the specific stages generating the additional backtracking.
2. Review navigation labels, instructions and calls to action in those stages.
3. Conduct usability testing to understand why users repeat or revisit steps.
4. Run a follow-up experiment after implementing targeted improvements.
5. Monitor whether the higher completion rate remains stable over time and across customer segments.

---

## My Contribution

This was a collaborative project completed during the Ironhack Data Analytics Bootcamp.

My responsibilities included:

* Coordinating the different project workstreams
* Organizing tasks and aligning the contributions of the team
* Helping ensure that the separate analyses formed a coherent final project
* Contributing directly to data cleaning and preparation
* Conducting the statistical hypothesis testing
* Interpreting statistical results in relation to the business objectives
* Supporting the integration of the findings into the final recommendation and presentation

---

## Repository Structure

```text
Project_Vanguard_AB_Test_Analysis/
│
├── 1_Source_Files/
│   └── Raw customer, experiment and digital interaction datasets
│
├── 1.1_Clean_Files/
│   └── Cleaned and standardized datasets
│
├── 1.2_Merged_Files_For_EDA/
│   └── Combined datasets prepared for exploratory analysis
│
├── 1.3_KPI_AB_Testing_Outputs/
│   └── Final KPI and statistical-testing results
│
├── 2_Python_Notebook/
│   ├── Contruction_Of_The_Final_DF.ipynb
│   ├── KPI_AB_Testing_Analysis.ipynb
│   ├── Johannes.ipynb
│   └── Individual exploratory notebooks
│
├── 3_Visualizations/
│   └── Charts and visual outputs
│
├── 4_Presentation/
│   └── Final classroom presentation
│
├── Project_ Vanguard A_B Test Analysis.pdf
│   └── Exported project presentation
│
├── README.md
└── .gitignore
```

---

## Tools and Technologies

* Python
* Pandas
* NumPy
* SciPy
* Statsmodels
* Matplotlib
* Seaborn
* Jupyter Notebook
* Tableau
* Git and GitHub
* Trello

---

## How to Explore the Project

### 1. Clone the repository

```bash
git clone https://github.com/JohannesVidal/Project_Vanguard_AB_Test_Analysis.git
cd Project_Vanguard_AB_Test_Analysis
```

### 2. Install the main dependencies

```bash
pip install pandas numpy scipy statsmodels matplotlib seaborn jupyter
```

### 3. Launch Jupyter Notebook

```bash
jupyter notebook
```

### 4. Recommended notebook order

1. `2_Python_Notebook/Contruction_Of_The_Final_DF.ipynb`
2. `2_Python_Notebook/KPI_AB_Testing_Analysis.ipynb`

The remaining notebooks contain individual exploratory work produced by members of the project team.

---

## Dashboards and Presentation

### Tableau dashboards

* [General KPI Dashboard](https://public.tableau.com/app/profile/husseim.stuck/viz/VisualizationsBootcamp/Dashboard1?publish=yes)
* [Customer KPI Dashboard](https://public.tableau.com/app/profile/husseim.stuck/viz/ClientKPI/Dashboard1?publish=yes)
* [Completion and Friction Dashboard](https://public.tableau.com/app/profile/mykyta.riabchynskyi/viz/Book555_17780734185880/Dashboard2?publish=yes)

### Presentation

* [Project Presentation](https://docs.google.com/presentation/d/1HxvQvZCR1xTOd56i2DrDFUhel9XdO_IzgNuGxG7GhQ4/edit)

### Project Management

* [Team Trello Board](https://trello.com/invite/b/69fb6114c784560b1731f115/ATTI59d93f6913fb65515cee5baadf2616673F006D66/vanguard-a-b-testing)

---

## Team

Collaborative project developed by:

* Johannes Vidal
* Pollob
* Husseim
* Mykyta

Completed as part of the **Ironhack Data Analytics Bootcamp**.

---

## Key Takeaway

The experiment illustrates why an A/B test should not be judged using a single metric.

The redesigned interface increased completion and helped successful users finish faster, but it also generated more backward navigation and repeated steps. Combining statistical significance, practical thresholds and user-behavior metrics produced a more balanced and actionable business recommendation.
