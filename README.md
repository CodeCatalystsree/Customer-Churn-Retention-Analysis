# Customer-Churn-Retention-Analysis
# Customer Churn & Retention Analysis

## Project Overview

This project analyzes customer churn and retention patterns using
the IBM Telco Customer Churn dataset.

The objective is to identify customer segments associated with
higher churn, analyze customer and revenue characteristics, and
derive actionable retention insights.

## Dataset

The dataset contains 7,043 customer records and 21 variables,
including:

- Customer demographics
- Tenure
- Contract type
- Internet service
- Payment method
- Monthly charges
- Total charges
- Churn status

## Analysis Completed

### Churn Distribution

- Total customers: 7,043
- Churned customers: 1,869
- Retained customers: 5,174
- Overall churn rate: 26.54%

### Contract Analysis

Observed churn rates:

| Contract | Churn Rate |
|---|---:|
| Month-to-month | 42.71% |
| One year | 11.27% |
| Two year | 2.83% |

Month-to-month customers show the highest observed churn rate.

### Tenure Analysis

| Tenure | Churn Rate |
|---|---:|
| 0–6 months | 52.94% |
| 7–12 months | 35.89% |
| 13–24 months | 28.71% |
| 25–48 months | 20.39% |
| 49–72 months | 9.51% |

Early-tenure customers show substantially higher observed churn.

### Payment Method Analysis

| Payment Method | Churn Rate |
|---|---:|
| Electronic check | 45.29% |
| Mailed check | 19.11% |
| Bank transfer (automatic) | 16.71% |
| Credit card (automatic) | 15.24% |

Electronic check customers have the highest observed churn rate.

### Internet Service Analysis

| Internet Service | Churn Rate |
|---|---:|
| Fiber optic | 41.89% |
| DSL | 18.96% |
| No internet service | 7.40% |

Fiber-optic customers show the highest observed churn rate.

### Combined Segmentation

Combining contract type and internet service revealed:

| Contract | Internet Service | Churn Rate |
|---|---|---:|
| Month-to-month | Fiber optic | 54.61% |
| Month-to-month | DSL | 32.22% |
| Month-to-month | No internet | 18.89% |
| One year | Fiber optic | 19.29% |
| Two year | Fiber optic | 7.23% |

The month-to-month + fiber-optic segment has the highest observed
churn rate among the analyzed combinations.

## Data Cleaning

`TotalCharges` was initially stored as a string/object column.

Investigation identified 11 blank values. All 11 corresponding
customers had zero months of tenure and had not churned.

The column was converted to numeric format and these values were
treated as zero rather than removing the records.

## Revenue Analysis

Total historical customer charges:

- Total charges: 16,056,168.70
- Charges associated with churned customers: 2,862,926.90
- Churned-customer share: 17.83%

This represents historical charges associated with churned
customers and should not be interpreted as forecasted future
revenue loss.

## High-Value Customer Analysis

Customers at or above the 75th percentile of `TotalCharges` were
classified as high-value based on historical charges.

- High-value threshold: 3,786.60
- High-value churned customers: 255
- High-value customer churn rate: 14.48%

## Monthly Charges Analysis

Average monthly charges:

- Retained customers: 61.27
- Churned customers: 74.44

Using the 75th percentile of `MonthlyCharges`:

- High monthly-charge threshold: 89.85
- High monthly-charge churned customers: 580
- High monthly-charge customer churn rate: 32.75%

## Technologies

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- SQL
- Power BI
- Jupyter Notebook
- Git
- GitHub

## Project Structure

```text
Customer-Churn-Retention-Analysis/
├── data/
│   └── WA_Fn-UseC_-Telco-Customer-Churn.csv
├── notebooks/
│   └── customer_churn_analysis.ipynb
├── sql/
├── powerbi/
├── visuals/
├── README.md
└── .gitignore