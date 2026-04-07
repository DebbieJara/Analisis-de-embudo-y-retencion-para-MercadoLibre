# Funnel & Retention Analysis with SQL — MercadoLibre

## Context
As a product analyst on MercadoLibre's Growth & Retention team, the product director posed the following challenge: "We need to understand at which stage of the process we lose users and how we can improve their retention over time." This analysis uses SQL to map the complete conversion funnel, identify the main drop-off points, and evaluate user retention by cohort.

## Objective
- Map the full conversion funnel from first visit to purchase
- Calculate conversion rates between each stage and identify the biggest drop-off
- Analyse user retention at D7, D14, D21, and D28 by country and monthly cohort
- Propose actionable improvements based on data

## Dataset
- `mercadolibre_funnel` — user events during the purchase process (first_visit, select_item, add_to_cart, begin_checkout, add_shipping_info, add_payment_info, purchase)
- `mercadolibre_retention` — recurring activity by user and period (signup date, activity date, active flag, days after signup)

**Period analysed:** January 1, 2025 – August 31, 2025

## Tools
- SQL (PostgreSQL) — CTEs, window functions, conditional aggregation
- Google Sheets — results dashboard

## Analysis Workflow
1. **Data exploration** — reviewed available events and table structure
2. **General conversion funnel** — built multi-stage funnel using CTEs and LEFT JOINs; calculated conversion rate at each stage relative to first visits
3. **Funnel by country** — segmented all funnel stages by country to identify geographic drop-off patterns
4. **Retention by country** — calculated D7, D14, D21, D28 retention counts and percentages per country
5. **Cohort retention analysis** — assigned each user to a monthly cohort based on their first signup date and tracked retention over time

## Key Techniques
- Multi-stage CTE funnels with LEFT JOIN chaining
- `NULLIF` to avoid division by zero in conversion calculations
- Conditional aggregation with `CASE WHEN` for retention metrics
- `DATE_TRUNC` and `TO_CHAR` for cohort month assignment
- `COUNT(DISTINCT ...)` for accurate user deduplication

## Files
- `analysis.sql` — all SQL queries organised by analysis section

## Author
Deborah Jara | Data Analyst | Mexico
[LinkedIn](https://linkedin.com/in/deborahjara) · [GitHub](https://github.com/DebbieJara)
