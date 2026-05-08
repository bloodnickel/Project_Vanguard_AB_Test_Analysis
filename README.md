# Vanguard Digital Challenge Analysis

## Overview
This project analyzes the impact of a redesigned digital investment platform interface for Vanguard through an A/B testing framework.

The objective of the analysis is to determine whether the new modernized user interface improves user performance and overall user experience compared to the existing platform.

The project focuses on:
- User journey analysis
- Completion behavior
- Friction detection
- KPI measurement
- A/B testing evaluation
- Data visualization and presentation

---

# Business Context

Vanguard is a global investment management company that provides digital tools for managing investments.

This project evaluates whether the redesigned mobile experience performs better than the current interface by analyzing:
- Completion Rate
- User Experience
- Navigation Friction
- User Efficiency

---

# Experiment Setup

## A/B Test Structure
- **Control Group** → Current interface
- **Test Group** → Redesigned interface

## Scope
The analysis includes users who started the investment process.

## Core Metrics
- Completion
- Friction
- Backtracking behavior
- Repeated steps
- Median completion time

## KPI Definitions

| KPI | Description |
|------|-------------|
| Completion Rate | Percentage of started sessions reaching confirmation |
| Friction Rate | Percentage of sessions with navigation issues |
| Efficiency | Median completion time |
| Backtracking | Users navigating backward during the flow |
| Repeated Steps | Users repeating the same step multiple times |

---

# Repository Structure

```bash
├── 1.1_Clean_Files/
│   └── Cleaned and processed datasets
│
├── 1.2_Merged_Files_For_EDA/
│   └── Final merged datasets for exploratory analysis and A/B testing
│
├── 1.3_KPI_AB_Testing_Outputs/
│   └── KPI calculations and A/B testing outputs
│
├── 1_Source_Files/
│   └── Raw source datasets
│
├── 2_Python_Notebook/
│   └── Main notebooks for EDA and statistical analysis
│
├── 3_Visualizations/
│   └── Graphs and charts used for insights and presentation
│
├── 4_to be named/
│   └── Additional project assets
│
├── 5_Presentation/
│   └── Final presentation slides
│
├── testkpi.ipynb
│   └── KPI experimentation notebook
│
└── .gitignore
```

---

# Tools & Technologies

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Jupyter Notebook
- Statistical A/B Testing
- Data Visualization

---

# Analysis Workflow

## 1. Data Cleaning
- Removed inconsistencies
- Standardized formats
- Prepared user session flows

## 2. Exploratory Data Analysis (EDA)
- User behavior analysis
- Funnel exploration
- Navigation pattern analysis

## 3. KPI Development
Measured:
- Completion rates
- Friction metrics
- Backtracking
- Repeated interactions
- Efficiency timing

## 4. A/B Testing
Compared:
- Control vs Test groups
- Statistical significance
- User experience improvements

## 5. Visualization & Presentation
Created business-oriented visual insights for stakeholder presentation.

---

# Key Questions

- Does the redesigned interface improve completion rates?
- Does the new experience reduce friction?
- Are users navigating more efficiently?
- Does the redesign reduce backtracking and repeated steps?

---

# Example Insights

Potential findings explored during the analysis:
- Higher completion rates in the redesigned flow
- Reduced friction during navigation
- Faster median completion times
- Improved user journey consistency

---

# How to Run

## Clone Repository

```bash
git clone <your-repository-url>
cd <repository-name>
```

## Install Dependencies

```bash
pip install -r requirements.txt
```

## Launch Jupyter Notebook

```bash
jupyter notebook
```

---

# Suggested Requirements

```txt
pandas
numpy
matplotlib
seaborn
jupyter
scipy
statsmodels
```

---

# Future Improvements

- Dashboard integration
- Automated KPI reporting
- Machine learning behavior prediction
- Real-time experiment tracking
- Enhanced user segmentation

---

# Project Type

Data Analytics | Product Analytics | A/B Testing |

---

# Author

Johannes, Pollob, Husseim, Mykyta

---

# Additional resources 

Presentation : https://docs.google.com/presentation/d/1HxvQvZCR1xTOd56i2DrDFUhel9XdO_IzgNuGxG7GhQ4/edit?slide=id.g3dc56ae57e6_0_98#slide=id.g3dc56ae57e6_0_98

Tableau Dashboard:

KPI:  https://public.tableau.com/app/profile/husseim.stuck/viz/VisualizationsBootcamp/Dashboard1?publish=yes

Client KPI:  https://public.tableau.com/app/profile/husseim.stuck/viz/ClientKPI/Dashboard1?publish=yes

Completion/Friction:  https://public.tableau.com/app/profile/mykyta.riabchynskyi/viz/Book555_17780734185880/Dashboard2?publish=yes

Kanban:  https://trello.com/invite/b/69fb6114c784560b1731f115/ATTI59d93f6913fb65515cee5baadf2616673F006D66/vanguard-a-b-testing
