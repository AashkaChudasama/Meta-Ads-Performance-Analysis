# Meta-Ads-Performance-Analysis
An end-to-end marketing analytics project that analyzes paid advertising performance across **Facebook and Instagram** using **Power BI**. The project brings together ad events, ad attributes, campaign budgets and audience information to help evaluate reach, engagement, conversions and budget utilization.

## Project Objective

The objective is to give the marketing team a consolidated view of Meta advertising performance and help answer questions such as:

- How do Facebook and Instagram compare on reach and conversion?
- Which ad formats and target audience segments perform best?
- How does advertising activity vary by country, date and time?
- How are campaign budgets distributed, and which campaigns appear more efficient?

**Scope:** Paid campaigns on Facebook and Instagram. Messenger, Audience Network and organic engagement are outside the scope of this analysis.

## Dataset

The project uses four CSV files:

| Dataset | Records | Description |
|---|---:|---|
| `ad_events.csv` | 400,000 | Ad-level user events, including impressions, clicks, likes, comments, shares and purchases |
| `ads.csv` | 200 | Ad attributes such as platform, ad type, target gender, target age group and target interests |
| `campaigns.csv` | 50 | Campaign names, start and end dates, duration and total budget |
| `users.csv` | 9,841 | User demographics, country, location and interests |

The event data covers **7 May 2025 to 6 August 2025**.

## Tools & Technologies

- **Power BI** – Data modelling, DAX measures and interactive dashboard development
- **Power Query** – Data cleaning, transformation and preparation
- **DAX** – KPI calculations and analytical measures
- **CSV** – Source data format

## Project Workflow

1. **Business requirements:** Reviewed the reporting objectives, scope, KPI definitions and required visualizations.
2. **Data loading and profiling:** Imported the four CSV datasets into Power BI and reviewed their structure and data quality.
3. **Data cleaning and preparation:** Standardized data types, checked missing and duplicate values, validated date and category fields, and addressed inconsistent user IDs.
4. **Data modelling:** Connected ad events to ads, users and a date table; connected ads to campaigns.
5. **KPI development:** Created measures for reach, engagement, conversion and budget reporting using the definitions in the Business Requirements Document.
6. **Dashboard development:** Built an interactive report with platform, measure, campaign and target-interest filters.
7. **Validation and analysis:** Compared dashboard KPI outputs with independently calculated analytical results and interpreted the findings.

### Data Preparation Highlights

- Standardized user IDs to improve matching between the event and user datasets. The share of events linked to users increased from **95.0% to 97.7%**.
- Retained all 400,000 event records. A total of **9,044 events (2.3%)** could not be reliably linked to a user and were excluded from user-country analysis, but remained in overall KPI totals.
- Kept campaigns without ads in the campaign budget totals and flagged them for budget-efficiency analysis.
- Created date-related fields and a date table to support weekly and monthly analysis.
- Retained Like events in the dataset, but excluded them from the Engagements KPI in line with the business requirement.

## Key Performance Indicators

The dashboard reports the following KPIs:

| KPI | Definition |
|---|---|
| Impressions | Count of impression events |
| Clicks | Count of click events |
| Shares | Count of share events |
| Comments | Count of comment events |
| Purchases | Count of purchase events |
| Engagements | Clicks + Shares + Comments |
| Click-Through Rate (CTR) | Clicks / Impressions × 100 |
| Engagement Rate | Engagements / Impressions × 100 |
| Conversion Rate | Purchases / Clicks × 100 |
| Purchase Rate | Purchases / Impressions × 100 |
| Total Budget | Sum of campaign budgets |
| Average Budget per Campaign | Total budget / Number of campaigns |

## Dashboard Features

The Power BI dashboard includes KPI cards and interactive visuals to explore performance from different perspectives.

- **Platform selection:** Switch between Facebook and Instagram.
- **Dynamic measure selection:** Change the metric displayed in the relevant visuals.
- **Campaign and target-interest filters:** Narrow the analysis to selected campaigns or audience interests.
- **Target gender:** Donut chart showing the selected metric by target gender.
- **Target age group:** Bar chart comparing performance across age groups.
- **Country analysis:** Map showing geographic distribution of performance.
- **Calendar month:** Calendar heat map showing activity by date.
- **Weekly trend:** Stacked column chart comparing weekly performance by ad type.
- **Hourly trend:** Trend chart showing activity by hour of day.
- **Ad type analysis:** Matrix comparing performance across ad formats.

### Dashboard Preview

Add the two dashboard screenshots to your repository and update the paths below if your image filenames differ.

**Facebook view**

<img width="860" height="492" alt="Screenshot 2026-10-30 153138" src="https://github.com/user-attachments/assets/bf9ff8d3-bd39-455c-90c1-12bbe511a903" />


**Instagram view**

![Meta Ads Performance Dashboard - Instagram](images/dashboard-instagram.png)

## Key Findings

- **Similar platform performance:** Facebook and Instagram showed broadly comparable rates. CTR was **11.76%** for Facebook and **11.86%** for Instagram; purchase rate was **0.61%** and **0.57%**, respectively. The reported platform differences were not statistically significant.
- **Stories performed well on conversion:** Stories had the highest conversion rate (**5.34%**) and purchase rate (**0.63%**) among the four ad types.
- **Budget did not consistently translate into purchases:** The highest-budget campaign group accounted for **41.4% of budget** and **24.6% of purchases**. Budget-to-purchase figures are an allocation-based proxy, not actual acquisition cost.
- **Country performance varied:** Japan, Mexico and the United States had the highest purchase rates among the countries analyzed. Country analysis uses events that could be linked to a user.
- **Limited timing differences:** Weekly and hourly activity was relatively consistent, providing limited evidence for strong timing-based optimization.

## Business Recommendations

- Run controlled Facebook-versus-Instagram tests with comparable ad volumes and capture spend by platform before reallocating budgets.
- Review high-budget campaigns with relatively few purchases and investigate campaigns that have budgets but no associated ads.
- Test Stories performance further and investigate the lower conversion observed for Instagram Image ads.
- Review country-level performance before changing market investment.
- Improve tracking by capturing spend and revenue at ad and platform level, and standardize user IDs at the source.

## Important Limitations

- The source data does not include revenue or spend at the ad/platform level. Therefore, **actual ROI and actual cost per acquisition (CPA) cannot be calculated**.
- Allocated budget per purchase is used only as a campaign-level comparison proxy; it should not be interpreted as actual CPA.
- Campaign budgets are stored at campaign level. As a result, total budget remains the same in the Facebook and Instagram dashboard views and should not be interpreted as platform-specific spend.
- May and August are partial months because the event period begins on 7 May and ends on 6 August 2025.
- The **2.3% of events without a reliable user match** are included in overall KPIs but excluded from user-country analysis.
