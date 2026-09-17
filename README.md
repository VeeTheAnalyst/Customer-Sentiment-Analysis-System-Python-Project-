# Customer-Sentiment-Analysis-System-Python-Project-
Python customer sentiment analysis using CSV data, rule-based sentiment classification, and customer risk scoring.
# Customer Sentiment Analysis System

### Turning Customer Feedback into Business Intelligence

A Python-based customer sentiment analysis project developed as part of a **Python Study Group (Team H)** project.

The project analyzes customer feedback to identify sentiment patterns, customer pain points, delivery and resolution issues, and customers who may be at higher risk of dissatisfaction.

> **Note:** This project uses a small synthetic dataset created for educational and portfolio purposes. It does not represent actual customers or transactions.

---

## Project Overview

AfriCart receives customer feedback through multiple channels across four African markets: **Nigeria, Ghana, Kenya, and South Africa**.

## Project Objective

The objective of this project was to transform unstructured customer feedback into structured business insights that could help answer questions such as:

* Are customers satisfied?
* What are customers complaining about?
* Which countries have the highest negative feedback?
* Which communication channels receive the most complaints?
* Are delivery problems associated with negative sentiment?
* Are unresolved complaints associated with negative feedback?
* Which customer issues require attention?

---

## Business Problem

Customer feedback can contain valuable information about customer experience, but unstructured comments can be difficult to analyze manually.

This project uses Python to process customer feedback and extract meaningful patterns that can support evidence-based business decisions.

---

## Dataset

The dataset contains **30 customer feedback records** with **12 columns**.

### Dataset Characteristics

| Category           | Details                              |
| ------------------ | ------------------------------------ |
| Records            | 30                                   |
| Columns            | 12                                   |
| Countries          | Nigeria, Ghana, Kenya, South Africa  |
| Channels           | Website, App, WhatsApp, Social Media |
| Product Categories | Electronics, Fashion, Groceries      |

### Main Variables

* Feedback ID
* Customer ID
* Date
* Country
* Channel
* Product Category
* Rating
* Delivery Days
* Expected Delivery Days
* Resolution Status
* Resolution Days
* Feedback Text

---

## Tools & Technologies

* **Python**
* Python built-in `csv` module
* Lists
* Variables
* Loops
* Conditional statements
* Functions
* Basic data cleaning
* Rule-based sentiment analysis

> Pandas was not used in this project.

---

## Data Cleaning

Before performing the analysis, several data-quality steps were carried out:

* Converted feedback text to lowercase
* Removed unnecessary whitespace using `.strip()`
* Converted numerical fields from strings to integers
* Checked country and channel values for consistent capitalization
* Identified missing values in the Date column

The missing dates were noted but did not affect the sentiment analysis or risk-scoring calculations.

---

## Sentiment Analysis Methodology

A simple **rule-based sentiment classifier** was developed using keyword matching.

### Positive Keywords

`excellent`, `great`, `good`, `fast`, `helpful`, `love`, `loved`, `quick`

### Negative Keywords

`bad`, `poor`, `late`, `slow`, `failed`, `disappointing`, `disappointed`, `terrible`

### Classification Logic

1. Convert the feedback text to lowercase.
2. Count positive keywords.
3. Count negative keywords.
4. If positive keywords > negative keywords → **Positive**
5. If negative keywords > positive keywords → **Negative**
6. If both counts are equal → **Neutral**

---

## Customer Risk Scoring

A weighted risk-scoring model was also used to identify customers who may require additional attention.

### Risk Factors

| Factor                             | Score |
| ---------------------------------- | ----: |
| 1-star rating                      |    25 |
| 2–3-star rating                    |    15 |
| Severe delivery delay (>5 days)    |    20 |
| Moderate delivery delay (3–5 days) |    10 |
| Unresolved complaint aging         |    20 |
| Unresolved complaint — new         |    10 |

### Risk Classification

| Score | Risk Level  |
| ----: | ----------- |
|  0–19 | Low Risk    |
| 20–39 | Medium Risk |
| 40–59 | High Risk   |
|   60+ | Critical    |

---

## Key Findings

### Overall Sentiment

* **50% Positive**
* **40% Negative**
* **10% Neutral**

### Customer Rating

The average customer rating was **3.27/5**.

### Delivery

Delivery was the most common complaint category, appearing in **50% of the feedback records**.

Severe delivery delays were associated with negative sentiment in the dataset.

### Resolution Status

All **11 unresolved complaints** were classified as negative, while resolved complaints had a much lower negative rate.

### Channel Analysis

Social Media recorded a **100% negative rate** in the sample, while WhatsApp recorded **0% negative feedback**.

### Country Analysis

* Ghana: **57.1% negative**
* Nigeria: **54.5% negative**
* Kenya: **14.3% negative**
* South Africa: **20.0% negative**

### Customer Risk

**5 out of 30 customers (16.7%)** were classified as High or Critical Risk based on the project’s weighted risk model.

---

## Business Insights

The analysis identified two major areas associated with negative customer sentiment:

**1. Delivery problems**

Delivery issues were the largest complaint category in the dataset.

**2. Unresolved complaints**

Unresolved complaints showed a strong association with negative sentiment in this sample.

Other areas identified included social-media complaints, payment failures, and customers with combinations of low ratings, unresolved complaints, and delivery delays.

---

## Project Recommendations

Based on the analysis, the project recommended:

* Addressing unresolved complaints quickly
* Investigating severe delivery delays
* Reviewing customer complaints received through Social Media
* Reviewing operations in Ghana and Nigeria
* Improving payment-failure handling
* Studying the practices associated with the positive WhatsApp feedback
* Maintaining fast complaint-resolution times
* Following up with High/Critical Risk customers

---

## Project Screenshots

<img width="1777" height="752" alt="Screenshot 2026-09-17 192222" src="https://github.com/user-attachments/assets/196dd12d-6bb4-4829-a737-c1e10a559179" />
<img width="1781" height="772" alt="Screenshot 2026-09-17 192338" src="https://github.com/user-attachments/assets/96ead46f-0019-4344-9845-8505c06929ce" />
<img width="1720" height="744" alt="Screenshot 2026-09-17 192519" src="https://github.com/user-attachments/assets/2cf1c672-a2e9-44c4-a865-b24e7d79d568" />
<img width="1761" height="755" alt="Screenshot 2026-09-17 192654" src="https://github.com/user-attachments/assets/615858e6-db7b-4059-943d-d37a58052910" />
<img width="1782" height="763" alt="Screenshot 2026-09-17 192815" src="https://github.com/user-attachments/assets/ac30b564-6a37-458a-887e-3f1228e265fb" />
<img width="1764" height="748" alt="Screenshot 2026-09-17 193022" src="https://github.com/user-attachments/assets/bf51942e-a005-4917-984f-6ad84263a48a" />
<img width="1785" height="746" alt="Screenshot 2026-09-17 193228" src="https://github.com/user-attachments/assets/bed55a0f-66d0-44eb-badf-a9cf53eaf89e" />
<img width="1779" height="726" alt="Screenshot 2026-09-17 193352" src="https://github.com/user-attachments/assets/e073d368-1ade-4c15-b720-63e3af3b1400" />
<img width="1777" height="865" alt="Screenshot 2026-09-17 193516" src="https://github.com/user-attachments/assets/904e6913-2d28-4b61-be7a-a4746d3938f4" />

----

## Project Limitations

This project has several limitations:

* The sentiment classifier is rule-based and does not use advanced NLP.
* Keyword matching cannot reliably interpret sarcasm, negation, context, or mixed sentiment.
* The dataset contains only 30 synthetic records.
* The risk-score weights were based on judgement rather than statistical modelling.
* Missing dates limited time-series analysis.
* Correlation in the dataset does not prove causation.

---

## Skills Demonstrated

* Python Programming
* Data Cleaning
* Data Analysis
* Functions
* Loops and Conditional Logic
* CSV Data Handling
* Rule-Based Sentiment Analysis
* Customer Feedback Analysis
* Business Intelligence
* Business Problem Solving
* Analytical Thinking

---

## Conclusion

This project demonstrates how Python can be used to transform raw customer feedback into structured insights that help identify customer sentiment, operational pain points, and potential customer-risk areas.

The project provided practical experience in **Python programming, data analysis, data cleaning, business problem-solving, and communicating analytical findings**.

---

## Project Structure

Customer-Sentiment-Analysis-System/

│ ├── customer_sentiment_analysis.py # Main Analysis Script
│ ├── customer_feedback.csv # Dataset
│ └── README.md
│ ├── data-cleaning.png 
│ ├── sentiment-analysis.png 
│ ├── analysis-results.png 
│ ├── screenshots/ │ ├── python-code.png 

---

## Author
**Nnadiukwu Glory Vivian**
Junior Data Analyst
**Email:** gloryvivian2000@gmail.com
**LinkedIn:**

## Team

**Python Study Group — Team H**

* Mustapha Emmanuel Oladeji — Junior Data Analyst(Team Captain)
* Nnadiukwu Glory Vivian — Junior Data Analyst(Team Member)
* Ekashili Kechukwu Promise — Junior Data Analyst(Team Member)
* Ehilawa Blessing Mmesoma — Junior Data Analyst(Team Member) 

---

## My Contribution

My contribution to this project included working on the Python-based customer sentiment analysis system, including data processing, analysis functions, sentiment and resolution analysis, and interpreting the resulting customer-feedback insights.

