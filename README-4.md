# Customer Churn Investigation | Exploratory Data Analysis (EDA)

**Arrowstack Data Science Internship — Task 1**  
**Project Type:** Comprehensive Exploratory Data Analysis  
**Tools:** Python, Pandas, NumPy, Matplotlib, Seaborn, Google Colab

## 1. Project Overview

This project presents a comprehensive Exploratory Data Analysis (EDA) of telecommunications customer churn using Python. The goal is to investigate customer characteristics associated with churn, identify notable retention patterns, and develop evidence-based business recommendations.

The project focuses on exploratory and descriptive analysis rather than predictive modeling or causal inference.

## 2. Business Problem

Customer churn is an important concern for subscription-based businesses. Understanding how observed churn differs across customer groups can help retention teams identify areas for further investigation and test more targeted strategies.

### Key Business Questions

1. What proportion of customers are classified as churned?
2. How does observed churn vary by contract type?
3. How do churn patterns differ across customer tenure groups?
4. How do monthly charges differ between churned and retained customers?
5. Which internet-service and payment-method categories show higher observed churn?
6. How does churn differ when tenure and contract type are considered together?

## 3. Dataset

This project uses the **Telco Customer Churn** dataset, based on IBM sample telecommunications customer data and available on Kaggle.

**Dataset source:** [Telco Customer Churn — Kaggle (BlastChar)](https://www.kaggle.com/datasets/blastchar/telco-customer-churn)

| Attribute | Description |
|---|---|
| Dataset | Telco Customer Churn |
| Records | 7,043 customer records |
| Variables | 21 columns |
| Primary outcome | `Churn` (`Yes` / `No`) |
| Analysis type | Exploratory Data Analysis |

The dataset includes customer demographics, subscriptions, billing information, payment methods, and churn status. A complete 21-variable data dictionary is included in the analysis notebook.

### Selected Variables

| Variable | Meaning |
|---|---|
| `customerID` | Unique customer identifier |
| `tenure` | Months the customer has been with the company |
| `Contract` | Month-to-month, one-year, or two-year contract |
| `MonthlyCharges` | Monthly customer charge |
| `TotalCharges` | Total recorded charges |
| `InternetService` | Internet service category |
| `PaymentMethod` | Customer payment method |
| `Churn` | Whether the customer is classified as churned |

## 4. Tools and Technologies

| Tool | Purpose |
|---|---|
| Python | Programming and analysis |
| Pandas | Loading, cleaning, aggregating and exploring data |
| NumPy | Numerical operations and validation |
| Matplotlib | Data visualization |
| Seaborn | Statistical charts |
| Google Colab | Notebook environment |

## 5. Analytical Workflow

1. **Data understanding:** Inspect data structure, types, descriptive statistics, and business questions.
2. **Data dictionary:** Document variables and their analytical roles.
3. **Data cleaning:** Examine missing values, inconsistent types, and duplicates.
4. **Univariate EDA:** Explore tenure, charges, contract types, and churn distributions.
5. **Bivariate EDA:** Compare churn across contract, tenure, payment method, and monthly charges.
6. **Advanced EDA:** Explore tenure–contract combinations and internet-service categories.
7. **Validation:** Verify totals, missing values, duplicates, and consistency across group analyses.
8. **Reporting:** Document findings, limitations, and practical next steps.

## 6. Key Findings

| Analysis | Finding |
|---|---|
| Overall churn | 1,869 of 7,043 customers (26.54%) are classified as churned |
| Contract type | Month-to-month customers have approximately 42% observed churn |
| Tenure | Shorter-tenure customers generally show higher observed churn |
| Monthly charges | Churned customers have higher median charges than retained customers |
| Internet service | Fiber-optic customers show approximately 42% observed churn |
| Payment method | Electronic-check customers show approximately 40% observed churn |

### Tenure and Contract Segmentation

Among customers holding month-to-month contracts, the observed churn proportions were:

| Tenure group | Observed churn |
|---|---:|
| 0–6 months | 55.2% |
| 7–12 months | 42.0% |
| 13–24 months | 37.7% |
| 25–48 months | 32.9% |
| 49+ months | 26.0% |

**Interpretation:** Newer customers with month-to-month contracts may be a useful group for further retention investigation. These are descriptive associations; they do not establish that a particular contract type or tenure causes churn.

## 7. Data Cleaning and Validation

The original `TotalCharges` column was stored as an object type and included **11 blank values**. All 11 affected records belonged to customers with zero months of tenure.

For this EDA, those entries were assigned zero under a **documented assumption** that no charges had yet accumulated. This assumption was not independently verified against billing records. The column was converted to `float64`.

| Validation check | Result |
|---|---:|
| Customer records | 7,043 |
| Churned customers | 1,869 |
| Missing cells remaining | 0 |
| Exact duplicate rows | 0 |
| Unique customer IDs | 7,043 |
| Observed churn proportion | 26.54% |
| Implemented consistency checks | Passed |

The notebook contains the cleaning code and validation checks so reviewers can inspect the process.

## 8. Business Recommendations

The results suggest several **areas to investigate and test**, rather than interventions proven to work:

1. **Improve early customer engagement:** Review onboarding and support experiences of newer customers.
2. **Evaluate contract incentives:** Test whether suitable loyalty benefits or contract offers improve retention.
3. **Investigate fiber-optic experiences:** Examine pricing, technical support, service quality and customer feedback.
4. **Review electronic-check experiences:** Investigate payment convenience, billing concerns, and other customer characteristics.
5. **Pilot targeted interventions:** Use controlled testing and measure outcomes before wider implementation.

## 9. How to Reproduce the Analysis

1. Download the original CSV from the [Kaggle dataset page](https://www.kaggle.com/datasets/blastchar/telco-customer-churn).
2. Open `01_customer_churn_eda.ipynb` in [Google Colab](https://colab.research.google.com/).
3. Run the notebook from the beginning.
4. When the file-upload prompt appears, select the original Telco Customer Churn CSV.
5. Review data-cleaning outputs, charts, validation results, and business interpretations.

The notebook cleans the raw dataset during execution; the cleaned dataset does not need to be uploaded separately.

## 10. Repository Structure

```text
telco-customer-churn-eda/
├── 01_customer_churn_eda.ipynb
└── README.md
```

Optional additions, if created, include `figures/` for exported visualizations and `requirements.txt` for dependencies.

## 11. Limitations

- This is exploratory analysis, not a causal study or a predictive model.
- Customer characteristics can overlap, so a difference between groups may have more than one explanation.
- Some small subgroups have unstable rates; the tenure–contract heatmap masks groups with fewer than 30 customers.
- The observation period of the churn outcome is not established here; **26.54% should not be described as a monthly or annual churn rate**.
- The reasons for cancellation and customer satisfaction were not directly measured.
- Assigning zero to blank `TotalCharges` values is an assumption recorded for reproducibility.

## 12. Conclusion

The analysis identifies notable differences in observed churn across customer segments, particularly among newer customers with month-to-month contracts. Rather than implementing a single retention intervention for everyone, a business could use these results to prioritize further research and test targeted programs.

Additional evidence and controlled evaluation are needed to determine which actions, if any, improve retention.

## 13. Project Author

**[Your Name]**  
Data Science Intern — Arrowstack, Batch 2026

## 14. Acknowledgements

Dataset: IBM sample telecommunications customer data, accessed via the [Telco Customer Churn Kaggle listing](https://www.kaggle.com/datasets/blastchar/telco-customer-churn).
