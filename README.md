# VELoop-Rewards-Internship-Task-Submission-Portal.

# VELOOP Rewards Internship Task Submission Portal

**Task 01 — Data Analysis, Data Quality, Business Insights & Analytics Dashboard**

## Project Overview

This repository contains the deliverables for my VELOOP Rewards Data Analyst Internship Task 01. The project focuses on analyzing reward-platform data, identifying data-quality issues, defining measurable KPIs, building interactive dashboards, executing SQL queries, and translating analytical findings into practical business recommendations.

The objective is to establish a reliable analytics framework for task activity, reward transactions, wallet reversals, withdrawals, referrals, and product feature events.

> **Important:** All operational figures and dashboard metrics in this submission are based on simulated data. They do not represent actual VELOOP Rewards production performance, real user behavior, verified wallet balances, or actual payout success.

## Project Objectives

- Understand the available datasets and their relationships.
- Perform data profiling, cleaning, and quality validation.
- Analyze task completion and validation separately.
- Examine reward statuses, wallet transactions, and reversal references.
- Evaluate withdrawal and referral status distributions.
- Define practical KPIs and document their calculation rules.
- Build interactive dashboards for exploring analytical results.
- Execute SQL queries and preserve their outputs for verification.
- Provide actionable recommendations for product, engineering, analytics, and finance teams.

## Technology Stack

- **Python:** Data analysis and data processing
- **SQL / SQLite:** Data querying and analytical validation
- **Microsoft Excel:** KPI analysis, charts, and reporting
- **HTML, CSS, JavaScript:** Interactive analytics dashboard
- **GitHub:** Project documentation and deliverable submission

## Repository Contents

| File | Description |
|---|---|
| `README.md` | Project overview, setup instructions, findings, and limitations |
| `21_Final_Consolidated_Report.docx` | Consolidated analytical report and final findings |
| `31_Working_Analytics_Dashboard.xlsx` | KPI cards, charts, business insights, and SQL result sheets |
| `32_Working_Dashboard.html` | Interactive dashboard for exploring simulated records |
| `34_Research_Insights_Action_Plan.docx` | Market research, business insights, and recommendations |
| `30_Analytics_Queries.sql` | Executable SQL queries for analytical validation |
| `VELOOP_Analytics_Simulated.sqlite` | SQLite database used to execute the queries |
| `33_SQL_Execution_Results.xlsx` | Consolidated SQL query outputs |
| `SQL_Result_Q01.csv` – `SQL_Result_Q11.csv` | Individual SQL query result files |
| `VELOOP_Rewards_Corrected_Simulated_Workbook.xlsx` | Corrected synthetic dataset used for testing |

*Note: Some deliverables may be stored inside the submitted ZIP package rather than at the repository root. Filenames in this table describe the documented project package.*

## Datasets Analyzed

The analysis covers the following simulated datasets:

1. **Users:** Registration source, device platform, region, and account status.
2. **Task Activity:** Task lifecycle status and validation information.
3. **Rewards:** Reward units and transaction statuses.
4. **Wallet:** Reward credits, redemptions, and reversal transactions.
5. **Withdrawals:** Withdrawal requests and their lifecycle statuses.
6. **Referrals:** Referral records and conversion-related statuses.
7. **Feature Events:** Product feature activity and event outcomes.

## Key Analytical Findings

The following results describe the supplied synthetic test records only.

| Area | Finding |
|---|---|
| Task activity | 6,000 rows, including 3,069 marked completed |
| Task validation | 1,058 completed rows are labelled valid |
| Validation diagnostic | Approximately 34.5% of completed rows are labelled valid |
| Reward records | 5,000 rows across credited, pending, reversed, and corrected statuses |
| Wallet reversals | 839 reversal rows, of which 286 have candidate parent links and 553 remain unresolved |
| Withdrawals | 1,200 rows, including 738 marked completed |
| Referrals | 900 rows, including 453 with converted status |
| Feature events | 12,000 simulated event records |

These counts are descriptive diagnostics, not production conversion rates or verified business performance metrics.

## Data Quality and Validation

The project highlights several important data-quality and reconciliation requirements.

### 1. Task completion and validation

Task completion must not automatically be treated as successful validation or reward credit. The analysis separates completed tasks from records labelled valid and recommends explicit lifecycle tracking.

### 2. Wallet reversal reconciliation

Of the 839 simulated reversal records, 553 remain unresolved and quarantined. The other 286 have algorithmically inferred candidate parent links that still require business confirmation.

Candidate matches are not verified financial relationships. Unresolved records must remain excluded from trusted net-credit and reversal-cost reporting until reconciliation against the authoritative ledger is complete.

### 3. Reward unit integrity

Reward units such as VE, Gems, Tokens, and XP must be analyzed separately. The supplied synthetic tables do not establish verified conversion rates or monetary values. VE/SVE definitions, conversion rules, rounding, expiry, and redemption policies require approval from the relevant business owners.

### 4. Withdrawal monitoring

Withdrawal status counts alone do not establish payout reliability. Valid lifecycle timestamps, processing durations, pending-age measures, rejection reasons, and payout eligibility rules are needed for operational monitoring.

### 5. Referral measurement

A record marked converted does not, by itself, establish successful acquisition or retained engagement. Referral activation criteria, fraud exclusions, and cohort-based retention measures must be defined before reporting a reliable referral conversion rate.

### 6. Feature-event quality

Feature failure metrics should use an explicitly defined eligible-event denominator. Events marked `not_applicable` should not automatically be classified as either successful or failed.

## Dashboard Features

The interactive HTML dashboard provides:

- KPI summaries based on simulated records.
- Task lifecycle status distributions.
- Reward status analysis.
- Wallet reversal reconciliation summaries.
- Withdrawal and referral status distributions.
- Task-type completion comparisons.
- Dataset selection and categorical filtering.
- Record-level exploration through interactive tables.
- Business recommendations based on analytical findings.

The Excel dashboard provides additional KPI summaries, charts, business insights, and SQL query outputs.

## How to Run the Dashboard

### Option 1: Open the HTML dashboard

1. Open the repository on GitHub.
2. Locate `32_Working_Dashboard.html`.
3. Download the file to your computer.
4. Open the downloaded HTML file in Chrome, Edge, or another modern browser.
5. Select a dataset and use the available filters to explore the simulated records.

The HTML dashboard contains embedded data and can run locally without a separate application server.

### Option 2: Explore the Excel dashboard

1. Download `31_Working_Analytics_Dashboard.xlsx`.
2. Open it using Microsoft Excel or a compatible spreadsheet application.
3. Review the KPI cards, charts, business insights, and SQL result sheets.

### Option 3: Execute the SQL queries

Requirements:
- SQLite
- The project SQL file
- The supplied SQLite database

Open a terminal in the directory containing the SQL file and database, then execute:

```bash
sqlite3 VELOOP_Analytics_Simulated.sqlite
```

At the SQLite prompt, run:

```sql
.read 30_Analytics_Queries.sql
```

To exit SQLite:

```sql
.quit
```

The SQL file contains analytical `SELECT` queries. The documented query outputs are also available in the project result files.

## Business Recommendations

Based on the analysis, the following actions are recommended:

1. **Improve task lifecycle tracking:** Record task completion, partner callbacks, validation decisions, and reward-credit posting as separate events.
2. **Strengthen wallet reconciliation:** Require valid parent transaction references and reconcile reversal records against authoritative ledger data.
3. **Standardize reward definitions:** Approve reward-unit definitions, conversion rules, rounding policies, and redemption semantics before publishing financial-style metrics.
4. **Improve withdrawal visibility:** Monitor pending age, median and 90th-percentile processing times, and rejection or reversal reasons.
5. **Measure referral quality:** Track qualifying activation, fraud exclusions, retained users, and incentive costs by referral cohort.
6. **Improve event observability:** Define event-specific success criteria, eligible denominators, error codes, and platform or release dimensions.
7. **Validate product hypotheses:** Use consented production telemetry, user research, and controlled experiments before making product decisions based on simulated findings.

## Project Limitations

- All analytical datasets and reported operational metrics are simulated.
- Synthetic data corrections do not represent changes to VELOOP production systems.
- Candidate wallet reversal links are not business-verified.
- A total of 553 reversal records remain unresolved and quarantined.
- Reward conversion rules and monetary values have not been verified.
- Production event streams, authoritative ledger records, and validated user-level funnel definitions were not supplied.
- Market and competitor research provides public product context, not evidence of internal competitor performance.

Interactive Analytics Dashboard

View or download the VELOOP Rewards analytics dashboard:

View Dashboard HTML — Open the dashboard file in the repository.

**Download Dashboard **— Download the HTML file and open it in Chrome.

Note: GitHub's file viewer may show the raw HTML instead of rendering the interactive dashboard. Download the file and open it locally, or publish it using GitHub Pages.

## Conclusion

This project demonstrates a structured approach to data analysis, data-quality validation, SQL-based investigation, dashboard development, KPI definition, and business recommendation development.

The primary takeaway is that reliable product analytics requires trustworthy source data, clearly defined metrics, traceable transactions, and consistent event semantics. The proposed controls and dashboards provide a foundation for future validation using approved production data.

**Project:** VELOOP Rewards Internship — Task 01  
**Focus:** Data Analytics | SQL | Data Quality | KPI Development | Dashboarding | Business Insights
