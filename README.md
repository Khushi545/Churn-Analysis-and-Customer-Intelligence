
# 📉 Churn Analysis & Customer Intelligence — OTT Subscription Platform

End-to-end churn analytics project for an OTT subscription platform (Netflix/Hotstar/Prime-style), built by integrating multi-table customer data — demographics, subscriptions, and support escalations — to identify high-risk subscribers and quantify revenue impact.

---

## 🎯 Business Challenge

In the hyper-competitive OTT landscape, retention is the primary lever for survival. This project simulates the role of a Data Analyst tasked with identifying high-risk subscribers using a multi-dimensional dataset spanning customer demographics, subscription tiers, and support escalations — then translating those findings into actionable, business-facing recommendations.

---

## 🛠️ Tech Stack

- **SQL & Python Integration:** `sqlite3`, `pandas`, `numpy`
- **Visualization:** `matplotlib`, `seaborn`
- **Core Skills:** Data cleaning, feature engineering, exploratory data analysis (EDA), behavioral visualization, executive reporting

---

## 🗂️ Database Schema

**Database:** `customer_churn`

| `db_customer` | `db_subscription` | `db_support` |
|---|---|---|
| customerid | customerid | customerid |
| name | subscription_start_date | complaint_date |
| country | subscription_type | escalations |
| state | renewal_date | csat_score |
| gender | plan_type | col_1 |
| dob | contract_type | comment |
| interests | cancellation_date | |
| pincode | cancellation_reason | |
| | monthly_charges | |
| | cltv | |
| | churn_score | |

---

## 🧭 Project Roadmap

1. **Relational Data Extraction** — Connect Python to a SQL database and pull multi-table datasets (`pandas`, `sqlite3`)
2. **Data Cleaning** — Fix data types, rename columns, select relevant fields, run QC checks, handle missing/null values (`numpy`, `pandas`)
3. **Feature Engineering** — Create calculated columns (tenure, churn flags, customer aging), transform data, apply filters
4. **Data Analysis (EDA)** — Aggregation, group-by, pivot tables to surface churn patterns
5. **Data Visualization** — Communicate behavioral trends with `matplotlib` and `seaborn`
6. **Executive Reporting** — Translate technical findings into business-ready insights and a presentation deck

---

## 📐 Churn Definition

Churn analysis answers three questions:
- **Who** — which customers left, or are likely to leave
- **Why** — what behavior preceded the churn
- **When** — the "danger zone" at which a user is most likely to leave

| Business Type | Churn Definition |
|---|---|
| SaaS | Subscription canceled |
| E-commerce | No purchase in 90 days |
| Adtech | Inactive on service/app for 90–120 days |
| Streaming | Membership inactive |
| Telecom | Account terminated |
| Banking | No transactions for X months |

---

## 📊 Key Metrics & Formulas

| KPI | Formula |
|---|---|
| Churn Rate | Churned Customers / Total Customers |
| Churn by Plan Type | Churn Rate GROUP BY plan_type |
| Churn by State | Churn Rate GROUP BY country, state |
| Retention Rate | 1 − Churn Rate |
| ARPU | SUM(monthly_charges) / COUNT(active customers) |
| Avg. Customer Tenure | AVG(DATEDIFF(cancellation_date OR NOW(), subscription_start_date)) |
| Revenue at Risk | SUM(monthly_charges) WHERE churn_score > 70 |
| Escalation Rate | SUM(escalations) / COUNT(complaints) × 100 |
| Avg. Complaints per Customer | COUNT(complaints) / COUNT(DISTINCT customerid) |
| Escalation → Churn Correlation | Churn rate WHERE escalations ≥ 1 vs. 0 |

---

## 💡 Key Insights

- **Overall Churn Rate:** 28.6% | **Retention Rate:** 71.4%
- Most churn originates from the **Basic** subscription plan — limited direct revenue impact
- Churn spiked in **September 2024**, concentrated in **Karnataka**
- **Average Tenure:** 1,451 days | **ARPU:** ₹18.8
- **Total Revenue:** ₹395 | **Revenue Lost to Churn:** ₹74 (**18%** of total revenue)
- **CLTV Lost:** ₹2,047
- **Monthly vs. Annual Contract Churn:** 55.6% vs. 8.3% — a **6.7x** gap

## ✅ Recommended Action Items

- Investigate Karnataka-specific drivers — pricing changes, complaint spikes, technical issues
- Review whether Basic plan pricing changed recently, particularly around September
- Monitor competitor activity — at least one churned user migrated to a competing platform
- Prioritize outreach (email, SMS, calls) to **High** and **Medium** risk customers, ranked by CLTV and complaint history

---

## 📁 Portfolio Summary

**Churn & Revenue Impact**
Engineered an end-to-end churn analytics pipeline for an OTT subscription dataset (20+ KPIs), identifying a 28.6% overall churn rate and surfacing that monthly-contract subscribers churned at 55.6% — 6.7x the 8.3% annual-contract rate — directly attributing $73.94/mo in MRR leakage and $2,047 in CLTV erosion to six at-risk customers, and enabling a targeted contract-migration retention strategy.

**Risk Scoring & Segmentation**
Developed a multi-dimensional churn risk scoring model by synthesizing subscription tenure, plan type, and support escalation signals across three relational tables (20+ KPIs), segmented the customer base into risk tiers using composite churn scores, exposed a significant lifetime value gap between churned and retained cohorts, and recommended prioritizing Premium annual-plan retention over Basic monthly acquisition.

**Support Intelligence & Cancellation Analysis**
Performed cross-functional support-churn correlation analysis by joining complaint, escalation, and CSAT data with subscription records, identified that escalated support interactions were disproportionately concentrated among churned customers, decomposed cancellation drivers into competitor switching, pricing sensitivity, and content dissatisfaction, and translated findings into a prioritized product and pricing roadmap.



*This project is applicable across E-commerce, SaaS, Fintech, and Adtech industries — built as a portfolio-ready, business-first analytics case study.*
