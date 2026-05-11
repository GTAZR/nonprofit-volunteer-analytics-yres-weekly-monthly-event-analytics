[YRES_README.md](https://github.com/user-attachments/files/27607325/YRES_README.md)
# nonprofit-volunteer-analytics-yres-weekly-monthly-event-analytics
# YRES Volunteer & Program Analytics Portfolio

A portfolio repository documenting my data analytics work for **York Region Educational Services (YRES)**.  
The project focuses on cleaning operational datasets, building repeatable Python workflows, preparing Tableau-ready outputs, and translating raw volunteer/program data into business insights for reporting and decision-making.

> **Note:** This repository is prepared for portfolio demonstration. Sensitive volunteer information such as names, emails, phone numbers, addresses, and internal raw files should be removed, anonymized, or replaced with sample data before public release.

---

## Project Overview

YRES manages volunteer sign-ups, coaching sessions, volunteer hour records, Slack engagement, and youth program information. These datasets were collected from multiple operational systems and often required manual cleaning before they could be used for reporting.

My role was to build data cleaning and analysis workflows using **Python, Pandas, Excel, and Tableau**, then generate clean datasets, summary reports, and dashboards for recurring organizational reporting.

This repository includes multiple analytics tasks completed across March–April 2026, including:

- Weekly volunteer sign-up reporting
- Weekly 1:1 coaching session reporting
- Monthly volunteer hour and milestone reporting
- Volunteer progress and Slack engagement analysis
- Summer camp program availability and pricing analysis

---

## Key Business Questions

This project was designed to answer practical operating questions such as:

- Where are new volunteers signing up from by province, city, and country?
- Which referral channels and age groups drive volunteer interest?
- How many coaching sessions were booked, completed, or canceled each week?
- Which volunteers have completed service or training hours?
- Which volunteers reached milestone thresholds during the month?
- Which volunteers have not booked interviews, joined Slack, or remained active?
- Which summer camp programs have available spots, what are their prices, and how do they differ by location and program type?

---

## My Contributions

### 1. Data Cleaning & Standardization

Built Python workflows to clean inconsistent operational data, including:

- Removed empty rows and repeated header rows from exported CSV files
- Standardized long survey column names into analysis-friendly fields
- Cleaned city, province, country, and referral source values
- Parsed messy creation log text into structured datetime fields
- Converted start/end timestamps into dates, times, weekdays, and week ranges
- Extracted province and program names from event type strings
- Handled duplicate records and missing values with documented business logic
- Standardized outputs into clean CSV/Excel files for Tableau and reporting

### 2. Weekly Sign-Up Analytics

Processed weekly volunteer sign-up exports and prepared clean datasets for dashboarding.

Main outputs included:

- Cleaned weekly sign-up datasets
- Province/city/country distribution summaries
- Age range and referral channel breakdowns
- Signup date and weekday fields for time-based analysis
- Tableau dashboard files and exported PDF dashboard snapshots

Example fields created:

- `Created Datetime`
- `Created Date`
- `Created Weekday`
- `Province`
- `City`
- `Country`
- `Referral`
- `Age range`

### 3. Weekly 1:1 Coaching Analytics

Combined coaching event data across 2025 and 2026, cleaned event-level records, and generated weekly reporting datasets.

Main logic included:

- Combined historical and current-year coaching records
- Standardized event timestamp fields
- Split event names into province and program type
- Calculated week ranges using a Sunday–Saturday reporting window
- Identified completed vs. canceled sessions
- Produced Tableau-ready coaching datasets

Example fields created:

- `Province`
- `Program name`
- `Start date & time`
- `End date & time`
- `Canceled by`
- `Week Range`

### 4. Monthly Volunteer Hour & Milestone Reporting

Created a monthly volunteer hour report using volunteer logs and VSP volunteer records.

Main logic included:

- Aggregated volunteer hours by name, email, and log type
- Separated service hours and training hours
- Calculated March 2026 monthly totals
- Calculated cumulative hours up to February 28 and March 31
- Identified volunteers who reached milestone thresholds during March
- Produced Excel reports for operational review

Main outputs included:

- `Final_Volunteer_Hour_Report_By_Mar2026.xlsx`
- `Volunteer_Milestone_Report_March_2026.xlsx`
- Volunteer hour distribution chart
- Volunteer distribution statistics text summary

### 5. Volunteer Progress & Slack Engagement Analysis

Analyzed volunteer progress across VSP records, Calendly interview records, and Slack activity data.

Main questions addressed:

- Which VSP volunteers had not booked an interview?
- Which interviewed volunteers had not been invited to Slack?
- Which volunteers were invited to Slack but had not joined?
- Which Slack members had low or no recent activity?

Data quality work included:

- Checked duplicate names and emails before joins
- Used left joins to identify missing workflow stages
- Created a data integrity alert file for duplicated YRES emails
- Documented why some joins required careful handling due to duplicate or inconsistent identifiers

### 6. Summer Camp Program Analysis

Cleaned and analyzed summer camp program data, including Vancouver and Aurora program information.

Main logic included:

- Parsed program date ranges into start and end dates
- Merged program metadata with pricing data by Activity ID
- Extracted numeric price values from messy cost text
- Converted available spot information into numeric fields
- Classified programs into half-day vs. full-day based on duration
- Prepared cleaned data for Tableau analysis of availability, pricing, and program structure

Main output included:

- `YRES_Summer_Camp_Vancouver_cleaned_data.csv`

---

## Technical Stack

| Category | Tools / Skills |
|---|---|
| Programming | Python |
| Data Processing | Pandas, NumPy, Regular Expressions |
| Data Cleaning | Missing value handling, duplicate checks, string normalization, datetime parsing |
| Data Transformation | GroupBy, pivot tables, merges/joins, feature engineering |
| Reporting | Excel, CSV exports, formatted operational reports |
| Visualization | Tableau, Matplotlib |
| Business Analysis | KPI definition, volunteer funnel analysis, weekly/monthly reporting logic |

---

## Repository Structure

```text
YRES-Analytics-Portfolio/
│
├── notebooks/
│   ├── weekly_signup_reports/
│   ├── weekly_coaching_reports/
│   ├── monthly_volunteer_hours/
│   ├── volunteer_progress_report/
│   └── summer_camp_analysis/
│
├── outputs_sample/
│   ├── cleaned_csv_samples/
│   ├── excel_report_samples/
│   └── tableau_dashboard_exports/
│
├── dashboards/
│   └── tableau_workbooks_or_pdf_exports/
│
├── docs/
│   └── project_notes_and_business_logic/
│
└── README.md
```

> Recommended public GitHub setup: keep the notebooks, anonymized sample outputs, dashboard screenshots/PDFs, and documentation. Do not upload raw confidential volunteer data.

---

## Data Workflow

```text
Raw operational exports
        ↓
Python data cleaning and validation
        ↓
Standardized analytical fields
        ↓
Clean CSV / Excel outputs
        ↓
Tableau dashboards and business reports
        ↓
Operational insights for YRES reporting
```

---

## Selected Technical Highlights

- Built repeatable Python notebooks for recurring weekly and monthly reports
- Used defensive data cleaning to handle repeated headers, blank rows, inconsistent text, and messy date formats
- Applied business-rule-based cleaning instead of only relying on generic null/duplicate checks
- Used `groupby`, `pivot_table`, and `merge` to create volunteer-level and event-level reporting tables
- Used left joins to identify missing workflow stages such as volunteers without interviews or Slack activity
- Created Tableau-ready datasets with standardized date, week, province, and program fields
- Produced Excel/PDF/CSV outputs for both internal reporting and dashboard visualization

---

## Business Impact

This project helped convert fragmented operational exports into structured reporting assets. The cleaned datasets and dashboards supported YRES in understanding:

- Volunteer acquisition patterns
- Regional distribution of new sign-ups
- Weekly coaching activity and cancellations
- Volunteer service/training hour progress
- Volunteer engagement gaps across interview and Slack stages
- Summer camp pricing, duration, and availability patterns

The work demonstrates an end-to-end analytics workflow from messy raw data to stakeholder-ready reporting.

---

## Portfolio Value

This project demonstrates my ability to work on real-world nonprofit operational data where data is not perfectly clean or standardized. It shows practical experience in:

- Data cleaning and validation
- Python-based reporting automation
- Business logic design
- Tableau dashboard preparation
- Operational analytics
- Communicating insights for non-technical stakeholders

---

## Future Improvements

Potential next steps include:

- Refactor notebooks into reusable Python scripts
- Build a single automated pipeline for weekly report generation
- Add data validation tests for required columns and date ranges
- Create anonymized sample datasets for public portfolio demonstration
- Build a consolidated Tableau dashboard across sign-ups, coaching, volunteer hours, and engagement metrics

---

## Author

**Andi Dong**  
Master of Engineering in Systems & Technology, McMaster University  
Data Analytics | Python | SQL | Tableau | Business Intelligence
