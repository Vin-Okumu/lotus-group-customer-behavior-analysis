<h1 align = "Center">
Lotus Group Customer Behavior Analysis

<h3 align = "Center">
Project Understanding and Problem Definition
</h3>

</h1>

# Project Context

Lotus Group is a retail business operating across Egypt and that its dataset contains customer, transaction, product, store, employee, date and returns information.

The key change from our earlier Power BI project is the analytical focus.

**Previous project:** *Business intelligence*

- Understand historical performance through descriptive analysis, KPIs and interactive dashboards.

**Current project:** *Customer analytics and machine learning*

- Understand historical purchasing behavior, identify meaningful customer patterns, and develop models to predict future customer outcomes.


> What we already have, *descriptive analysis*, explains what has happened, whereas 

> What we are doing now, *predictive modeling*, uses information available at a given point in time to estimate what may happen next.

## Business Problem Statement

Lotus Group operates across multiple retail locations in Egypt and maintains data on customers, transactions, products, stores and product returns. Although these records provide information about historical business activity, the business needs a more structured understanding of its customers' purchasing behavior and future value.

The analytical challenge is to transform these raw, potentially inconsistent datasets into a reliable customer-level analytical dataset that can reveal purchasing patterns and support predictive modeling.

The project will investigate whether historical customer behavior can be used to predict repeat purchasing and future customer spending, providing insights that could support customer retention, marketing prioritization and revenue planning.

Because the dataset is synthetic, the findings will demonstrate analytical methods and potential business applications rather than establish facts about actual retail customers in Egypt.

### General Objective

To analyze customer purchasing behavior and develop classification and regression models that predict future purchasing activity and customer spending using Lotus Group's historical retail data.

### Specific Objectives

1. Assess and clean the raw datasets to establish reliable, consistent and analytically useful customer and transaction records.

2. Investigate customer purchasing patterns, including purchase frequency, spending behavior, product preferences, seasonality and returns.

3. Engineer customer-level features that summarize historical purchasing behavior without incorporating information from future outcomes.

4. Develop a classification model to predict whether a customer will make a qualifying purchase within the next 90 days.

5. Develop a regression model to predict customer spending during the next 90 days.

6. Evaluate model performance against appropriate baselines and interpret the results in terms of potential business applications.

7. Develop evidence-based recommendations for customer retention, marketing prioritization and revenue planning.

## Research Questions

|No.	|Research question	|Analytical approach|
----|----|----|
|1	|How do customers differ in purchasing frequency, spending and product preferences?	|Exploratory data analysis and RFM analysis|
|2	|Which customer characteristics and historical purchasing patterns are associated with repeat purchasing?	|Statistical analysis and classification|
|3	|To what extent can historical purchasing behavior predict whether a customer will purchase again within 90 days?	|Classification|
|4	|To what extent can historical purchasing behavior predict customer spending over the next 90 days?	|Regression|
|5	|Which historical customer features contribute most to the predictions?	|Model interpretation|
|6	|How could the findings support customer retention and marketing prioritization?	|Business interpretation|

One distinction is important: *our predictive models may identify useful associations, but they will not automatically establish that a particular behavior causes a customer to purchase or stop purchasing.*

### Target Variable Definition

**Target A: Repeat-purchase classification**

**Problem type:** Binary classification

- **Business question:** Will a customer make at least one qualifying purchase during the 90 days following a defined observation date?

|Target value	|Definition|
|----|----|
|1	|At least one qualifying purchase occurs in the next 90 days.|
|0	|No qualifying purchase occurs in the next 90 days.|

The exact rules for qualifying purchases - including treatment of cancelled orders and other order statuses - will be established after inspecting the data.

**Target B: Future customer spending**

**Problem type:** Regression

**Business question:** How much qualifying purchase revenue will a customer generate during the following 90 days?

**Target:** The sum of the customer's qualifying order revenue during the future window.

We must first determine whether the appropriate measure is gross sales, discounted sales, or net spending after returns. We must define this consistently before calculating the target.

Both models will have to use the same observation date and future window wherever practical. This will let us compare their findings and maintain a coherent project design.

- For example, if a customer has made five orders before the observation date, those orders may inform the model's features. Orders occurring after that date determine the targets. Those future orders must never be used as predictors.

### Measure of Success

We won't want to decide that a model is successful simply because it achieves a high accuracy score or produces a small prediction error. We need criteria appropriate to each task.

|Component	|Evaluation criteria|
|----|----|
|Data preparation	|Key integrity, documented cleaning decisions, valid data types and consistent business rules|
|Customer behavior analysis	|Reproducible metrics and interpretable findings that answer the research questions|
|Classification	|Precision, recall, F1-score, ROC-AUC and a confusion matrix; compare against a simple baseline|
|Regression	|MAE, RMSE and \(R^2\); compare against a baseline prediction|
|Validation	|Chronological evaluation using only information available before the target period|
|Business usefulness	|Clear explanation of what predictions can support and where they may be unreliable|

We want to establish numerical performance benchmarks after examining the dataset and evaluating baseline models. 

- For instance, if repeat purchases are very common, a classifier could achieve high accuracy simply by predicting that nearly everyone will purchase again. 

    - Accuracy alone would therefore be misleading.

- Likewise, a regression model should be evaluated on customers and periods not used to train it.

### Project Scope and Deliverables

The initial project scope includes:

- Data inventory and quality assessment.

- Data cleaning and integration across the nine tables.

- Exploratory customer behavior analysis and RFM metrics.

- Customer-level feature engineering.

- One primary classification model and one primary regression model, with baseline and alternative models for comparison.

- Model evaluation, interpretation, limitations and business recommendations.

- Reproducible code and documentation suitable for a data science portfolio.

We want to leave advanced techniques, deployment and additional predictive targets out of the initial scope unless the data or our findings provide a compelling reason to expand it.
