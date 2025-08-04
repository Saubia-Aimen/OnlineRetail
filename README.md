
# Customer Segmentation and Lifetime Value (CLV) Prediction for an Online Retailer

## Project Overview

This project analyzes a transactional dataset from a UK-based online retailer to identify distinct customer segments and predict their future lifetime value. The primary goal is to provide the business with actionable insights for developing targeted, data-driven marketing strategies to improve customer retention and maximize profitability.

## Key Questions
This analysis seeks to answer the following key business questions:
1.  Who are our most valuable customers?
2.  Which customers are at risk of churning?
3.  What are the distinct purchasing behaviors of our customers?
4.  What is the predicted lifetime value for each customer over the next 12 months?

## Data Source
The dataset used is the **Online Retail Data Set** from the UCI Machine Learning Repository. It contains transactional data for all purchases made between 12/01/2010 and 12/09/2011.

- **Source:** [UCI Machine Learning Repository: Online Retail Data Set](https://archive.ics.uci.edu/ml/datasets/online+retail)

## Tech Stack
- **Programming Language:** Python 3.8
- **Libraries:** Pandas, Matplotlib, Seaborn, Lifetimes, Jupyter Notebook

## Methodology

The project follows a structured data analysis workflow:

1.  **Data Cleaning & Preprocessing:**
    - Handled missing `CustomerID` values.
    - Removed canceled transactions (returns).
    - Converted data types for accurate calculations (`InvoiceDate` to datetime).
    - Engineered a `TotalPrice` feature from `Quantity` and `UnitPrice`.

2.  **RFM Segmentation:**
    - Calculated **Recency**, **Frequency**, and **Monetary (RFM)** values for each customer.
    - Grouped customers into distinct segments (e.g., "Champions," "At Risk," "Loyal Customers," "Hibernating") based on their RFM scores.

3.  **Predictive Modeling (CLV):**
    - Utilized the **`lifetimes`** library to model customer purchasing behavior.
    - Fitted a **Beta-Geometric/Negative Binomial Distribution (BG/NBD)** model to predict the number of future purchases.
    - Fitted a **Gamma-Gamma** model to predict the average monetary value of future purchases.
    - Combined these models to calculate the predicted **Customer Lifetime Value (CLV)** for each customer over a 12-month period.

## Key Findings & Visualizations

### 1. Customer Segment Distribution
The analysis revealed a significant portion of customers fall into "Hibernating" or "At Risk" categories, presenting both a challenge and an opportunity for targeted re-engagement campaigns. "Champions" and "Loyal Customers" make up a smaller but highly valuable portion of the customer base.

![Customer Segment Distribution](images/segment_distribution.png)
*(Note: Replace `images/segment_distribution.png` with the actual path to your saved chart image)*

### 2. Predicted Lifetime Value by Segment
The predictive models confirmed the validity of the RFM segmentation. The "Champions" segment has a significantly higher average predicted CLV, validating that our most recent and frequent high-spenders are indeed the most valuable in the long run.

![CLV by Segment](images/clv_by_segment.png)
*(Note: Replace `images/clv_by_segment.png` with the actual path to your saved chart image)*

## Business Recommendations

Based on the analysis, the following actions are recommended:

* **🏆 For Champions:** Implement a loyalty program with exclusive perks and early access to new products. The goal is to retain these high-value customers and turn them into brand advocates.
* **💔 For At Risk Customers:** Launch a targeted "we miss you" email campaign with a personalized discount based on their past purchase history. This proactive step is crucial to re-engage them before they churn.
* **🌱 For Promising/New Customers:** Nurture them with an onboarding email series that showcases the brand's value and offers an incentive for their second purchase to increase buying frequency.

## How to Run This Project

1.  Clone this repository:
    ```bash
    git clone [https://github.com/](https://github.com/)[Your-GitHub-Username]/[Your-Repo-Name].git
    ```
2.  Install the required dependencies. It is recommended to use a virtual environment.
    ```bash
    pip install -r requirements.txt
    ```
    *(To create the `requirements.txt` file, run `pip freeze > requirements.txt` in your terminal)*

3.  Launch the Jupyter Notebook:
    ```bash
    jupyter notebook Customer_Segmentation_and_CLV.ipynb
    ```

---

**Author:** [Your Name]

**Contact:** [Your LinkedIn Profile URL] or [Your Email]
