# Customer Churn Prediction & Retention Intelligence

> **Can customer data help a business identify customers at risk of leaving?**

**Project:** AfriConnect Telecom (fictional)
**Author:** Emmanuel Olawumi
**Stack:** Python | Jupyter Notebook | Python Standard Library
**Stage:** Version 1 — Python Foundations
**Dataset:** Synthetic customer data (10,000 records)

---

## What This Is

A Python-based churn risk analysis project built on a 10,000-customer synthetic telecom dataset.

I started with a 20-customer learning exercise, then scaled it to explore what happens when the same analytical thinking is applied to a much larger dataset.

The goal was never just to calculate a churn percentage.

The goal was to build a complete analytical workflow:

Business Problem → Data Generation → Data Investigation → Data Cleaning
→ Churn Analysis → Risk Scoring → Business Recommendations


This is Version 1. It is built entirely with Python's standard library — no pandas, no numpy, no machine learning yet.

---

## The Story

### Starting Small

The original exercise contained 20 customers.

The purpose was simple: understand the logic of churn analysis before applying it at scale.

That prototype taught me how to:
- Structure customer data
- Count churned vs retained customers
- Calculate churn rate
- Compare groups
- Build basic risk logic

But 20 customers cannot represent a real business population.

So I scaled it.

---

### The Random Data Experiment

I generated 10,000 customer records using Python's `random` module.

Every variable was generated independently:
- Satisfaction was random
- Complaints was random
- Tenure was random
- Churn was random

I ran the analysis.

**No meaningful relationships appeared.**

The numbers were almost identical between churned and retained customers.

That was not a failure.

That was the lesson.

> **Random data does not produce real patterns. If you want meaningful insight, you need meaningful data generation.**

---

### The Controlled Data Experiment

I rebuilt the dataset — but this time, churn probability was influenced by three factors:

- **Satisfaction** — Lower satisfaction → higher churn probability
- **Complaints** — More complaints → higher churn probability
- **Inactivity** — Longer inactivity → higher churn probability

I used different probability bands for high-risk, moderate-risk, and lower-risk combinations.

This produced a dataset where patterns could actually be investigated.

**Important:** These relationships were intentionally designed for learning purposes. They were not discovered from real telecom customers.

That distinction matters.

---

## Project Workflow

Business Problem
↓
20-Customer Prototype
↓
Scale to 10,000 Customers
↓
Random Data Experiment
↓
No Meaningful Relationship Found
↓
Controlled Synthetic Data
↓
Data Quality Investigation
↓
Data Cleaning
↓
Customer & Churn Analysis
↓
Feature Engineering
↓
Rule-Based Risk Scoring
↓
Retention Recommendations


---

## Key Findings

| Metric | Result |
|--------|-------:|
| Total customers | 9,999 |
| Churned customers | 5,507 |
| Retained customers | 4,492 |
| Churn rate | 55.08% |
| Retention rate | 44.92% |
| High-risk customers (rule-based) | 5,792 (57.93%) |

### Churned vs Retained

| Metric | Churned | Retained |
|--------|--------:|---------:|
| Average satisfaction | 2.79 | 3.23 |
| Average complaints | 3.20 | 2.80 |
| Average tenure | 36.25 months | 36.60 months |
| Average inactivity | 31.46 days | 28.54 days |

Three variables clearly differentiate churned customers:

1. **Satisfaction** — Churned customers are less satisfied
2. **Complaints** — Churned customers complain more
3. **Inactivity** — Churned customers are more inactive

Because the relationships were deliberately built into the dataset, these findings describe patterns within this simulation — not universal telecom truths.

---

## What's in the Notebook

The notebook walks through the complete analytical process:

| Section | Content |
|---------|---------|
| 1 | Project Introduction |
| 2 | Understanding the Logic (20 Customers) |
| 3 | Scaling to 10,000 Customers |
| 4 | Data Dictionary |
| 5 | Data Quality Investigation |
| 6 | Data Cleaning |
| 7 | Customer Analysis |
| 8 | Churn Analysis |
| 9 | Risk Logic & Scoring |
| 10 | Feature Engineering |
| 11 | Final Summary Report |

**The notebook is the work. This README is the summary.**

---

## Data Quality

The project deliberately included controlled data-quality issues to simulate real-world problems:

- Missing satisfaction values
- Negative charges
- Negative usage values
- Invalid age values
- Invalid satisfaction scores
- Invalid churn values
- Duplicate customer IDs
- Invalid regions
- Negative tenure

The purpose was not just to clean data.

It was to practice the process of:

> **Inspect → Identify → Decide → Clean → Validate**

Data analysis does not begin with calculating insights.

It begins with understanding whether the data can be trusted.

---

## Risk Scoring

The current version uses a **rule-based risk scoring system**.

Each customer receives points based on:

| Variable | Condition | Points |
|----------|-----------|--------|
| Satisfaction | ≤ 2 | +3 |
| Satisfaction | = 3 | +2 |
| Complaints | ≥ 4 | +3 |
| Complaints | 2–3 | +2 |
| Last Activity | ≥ 20 days | +3 |
| Last Activity | 10–19 days | +2 |

**Risk Levels:**

| Score | Level |
|-------|-------|
| 0–2 | Low |
| 3–5 | Medium |
| 6–9 | High |

The project also engineers additional features:

- Tenure_Group
- Spending_Group
- Engagement_Level
- Service_Risk_Level

This demonstrates how an analyst moves from raw customer information to a structured framework for prioritizing customers.

---

## From Analysis to Action

The goal is not just to say *"these customers are high risk."*

The more useful question is: **"What could the business do with that information?"**

Potential actions based on the observed patterns:

1. **Prioritize high-risk customers** — Customers showing low satisfaction, frequent complaints, and inactivity could be prioritized for further investigation
2. **Investigate service friction** — Higher complaints among churned customers suggest service experience deserves closer attention
3. **Re-engage inactive customers** — Extended inactivity may signal disengagement before departure
4. **Improve customer experience** — Low satisfaction appears alongside higher churn in this dataset

These are analytical recommendations and hypotheses for further testing — not guaranteed outcomes.

---

## Limitations

This project is transparent about what it can and cannot demonstrate.

### 1. Synthetic Dataset
Generated using Python's `random` module. Does not represent real AfriConnect customers. Controlled relationships were intentionally designed for learning.

### 2. No Real-World Validation
Findings have not been tested against real customer data. They should not be generalized to the telecom industry.

### 3. Rule-Based System, Not Machine Learning
Manually defined rules. Not a machine learning model. No statistically validated churn probabilities.

### 4. No Predictive Model Validation
No train/test split, confusion matrix, precision, recall, F1-score, or ROC-AUC. These come in the ML stage.

### 5. Thresholds Are Project Assumptions
Satisfaction, complaint, and inactivity thresholds were chosen for this project. Not universal standards.

### 6. Limited Variables
Real churn is influenced by competitor activity, pricing changes, economic conditions, contract changes, and many other factors not represented here.

### 7. Synthetic Churn Distribution
The 55.08% churn rate is a consequence of the controlled generation approach. Not a realistic telecom benchmark.

---

## What This Project Is Not

- Not a real telecom customer analysis
- Not a production churn system
- Not a validated machine learning model
- Not a causal analysis
- Not evidence that these variables universally cause churn

It is a **learning and portfolio project** demonstrating the analytical process from business problem to data-driven insight.

---

## Tools Used

**Current Version:**
- Python
- Jupyter Notebook
- Python standard library (`random`)

**Planned Upgrades:**
- NumPy, Pandas
- Matplotlib, Seaborn
- Scikit-learn
- Model evaluation
- Dashboarding

The idea is not to throw away Version 1.

It is to **upgrade the same business problem as my skills improve.**

---

## Project Evolution

VERSION 1
Python Foundations
↓
VERSION 2
NumPy + Pandas
↓
VERSION 3
EDA + Visualization
↓
VERSION 4
Machine Learning
↓
VERSION 5
Churn Probability + Retention Intelligence
↓
FUTURE
Dashboard / Monitoring / Advanced Segmentation


The current repository represents the early stage of that journey.

---

## Repository Structure

customer-churn-prediction/
│
├── README.md
│
├── notebooks/
│ └── customer_churn_analysis.ipynb
│
└── images/
├── project_workflow.png
├── random_vs_controlled.png
├── churn_analysis.png
├── risk_scoring.png
└── business_recommendations.png


---

## Screenshots & Visuals

The images below are intended to highlight the analytical story — not reproduce every output from the notebook.

### Project Workflow

![Project Workflow](images/project_workflow.png)

*The end-to-end analytical process: from business problem to retention recommendations.*

---

### Random vs Controlled Data Experiment

![Random vs Controlled Data](images/random_vs_controlled.png)

*The first experiment (random data) produced no meaningful relationships. The second experiment (controlled data) revealed clear patterns between satisfaction, complaints, inactivity, and churn.*

---

### Churn Analysis

![Churn Analysis](images/churn_analysis.png)

*Comparison of churned vs retained customers across satisfaction, complaints, tenure, and inactivity.*

---

### Risk Scoring

![Risk Scoring](images/risk_scoring.png)

*Distribution of customers across Low, Medium, and High risk categories based on the rule-based scoring system.*

---

### Business Recommendations

![Business Recommendations](images/business_recommendations.png)

*Four evidence-based retention recommendations connecting analytical findings to business action.*

---

## How to Run

```bash
# Clone the repository
git clone https://github.com/emmy0la/customer-churn-prediction.git

# Navigate to the project
cd customer-churn-prediction

# Launch Jupyter
jupyter notebook

# Open: notebooks/customer_churn_analysis.ipynb

```

## What I Learned

- Data analysis starts with understanding the business problem

- More data does not automatically mean better insights

- Random data can produce random-looking relationships

- Data generation assumptions matter

- Data quality needs to be investigated before analysis

- Cleaning requires decisions, not just code

- Comparing groups can reveal useful patterns

- Rule-based analysis is a useful starting point

- Feature engineering adds analytical depth

- Business recommendations should connect evidence to action

- Limitations should be communicated, not hidden

- A portfolio project should tell a story, not just display code

Most importantly:

  The goal is not to chase tools. The goal is to learn how to think with data.

## Future Improvements

1. Rebuild with NumPy and Pandas

2. Make dataset generation reproducible

3. Add exploratory visualizations

4. Perform statistical analysis

5. Build a machine learning churn model

6. Evaluate model performance (precision, recall, F1)

7. Generate churn probabilities

8. Compare model-based risk with rule-based risk

9. Add time-based customer behaviour

10. Build customer segments

11. Develop a churn monitoring dashboard

  The long-term goal:

  **Customer Data → Analysis → Rule-Based Risk → Machine Learning → Churn Probability → Retention Intelligence**

## Final Reflection

I started this project with a small dataset and a simple Python exercise.

Then I made it bigger.

The first attempt taught me that random data does not magically create insight.

The second attempt taught me that when relationships are designed into data, the analysis can reveal them — but that does not make them real-world truths.

That distinction is part of the learning.

This project is less about claiming I've solved churn and more about demonstrating how I'm learning to approach a business problem:

Understand → Question → Analyze → Acknowledge → Communicate → Improve.

This is Version 1.

The notebook may end here for now. The project does not.

Disclaimer
This project is created strictly for educational and portfolio purposes.

AfriConnect Telecom is a fictional company. The dataset is synthetic. The relationships were designed for analytical learning.

No real customer information was used.

Author
Emmanuel Olawumi

Aspiring Data Analyst | Python | SQL | Excel | Data Analytics

GitHub: github.com/emmy0la

The notebook is the work.
The README is the front door.
The next version is the upgrade.





