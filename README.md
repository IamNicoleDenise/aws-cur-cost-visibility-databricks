# AWS Cost & Tagging Visibility with Databricks SQL

![SQL](https://img.shields.io/badge/SQL-4479A1?style=flat-square)
![Databricks](https://img.shields.io/badge/Databricks_SQL-FF3621?style=flat-square&logo=databricks&logoColor=white)
![AWS CUR](https://img.shields.io/badge/AWS_CUR_(Parquet)-232F3E?style=flat-square)
![Dashboard](https://img.shields.io/badge/Dashboard_Design-555555?style=flat-square)

A cost governance dashboard built directly on the AWS Cost and Usage Report (CUR) in Databricks SQL. No third-party tools: raw billing data, SQL, and a dashboard that shows where money goes and where attribution breaks down.

📄 **Full case study:** [AWS Cost & Tagging Visibility with Databricks SQL](https://iamnicolecoleman.com/portfolio/finops-case-study-aws-cost-optimization-dashboard-built-in-databricks/)

## Skills demonstrated

| Skill | Where it shows up |
|---|---|
| SQL aggregation & modeling | Rolling CUR line items up by month, service, region, department, and usage type |
| Semi-structured data | Parsing usage types (BoxUsage, DiscountedUsage) and extracting tag keys for allocation |
| Data quality analysis | Measuring tag compliance and untagged spend by service |
| Dashboard design | 11 widgets built for both quick reviews and deeper dives |
| Cost-aware engineering | Testing queries in notebooks first to save Databricks compute credits |

## Data

Three months of AWS CUR data (Oct–Dec 2018) in Parquet format.

## What the dashboard covers

- Total cost and monthly spend trend (run rate, anomalies)
- Tag compliance and untagged spend, total and by service
- Cost by region and department allocation via tags
- RI spend and utilization, idle EC2 spend
- Unit cost by usage type
- Daily anomaly tracking
- Maturity tracker scoring Tagging, Allocation, and Optimization (Crawl / Walk / Run)

## Findings

- Spend was stable across the 3-month window
- AWS Glue was the top cost driver
- RI utilization was only 31%
- Over 90% of resources were untagged
- Spend concentrated in us-east-1

## Trade-offs I worked through

- **Blended vs. unblended cost:** RI analysis needed blended cost to be accurate
- **2018 dataset:** no Savings Plans, so RIs were the only commitment lever
- **Formatting:** dashboard tiles needed manual setup for currency and percent values

## Recommended next steps

Enforce tags at launch (owner, env, dept), use tags for showback/chargeback, revisit commitment coverage, and add forecasting and budget KPIs.

---

**Nicole Coleman** · [LinkedIn](https://www.linkedin.com/in/nicoledcoleman/) · [Portfolio](https://iamnicolecoleman.com)
