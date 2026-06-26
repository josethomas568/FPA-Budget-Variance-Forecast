# BrewMetrics Coffee Co. — FP&A Budget vs. Actual & Rolling Forecast

A self-contained **Financial Planning & Analysis (FP&A)** model that takes a fictional multi-location coffee company through a full planning cycle: **budgeting, variance analysis, management reporting, and a driver-based rolling forecast.** Built in Excel with fully dynamic formulas (no hard-coded results), so every output recalculates when an input changes.

---

## Overview

`BrewMetrics_FPA_Budget_vs_Actual.xlsx` simulates the core monthly workflow of a corporate FP&A analyst:

1. Capture **budget vs. actual** results by department and account.
2. Compute and interpret **variances** ($ and %), flagging each as favorable or unfavorable.
3. Roll results into a **P&L summary dashboard** for leadership.
4. Project the next quarter with a **driver-based rolling forecast** and scenario-ready assumptions.

The dataset is synthetic but realistic: four departments (Sales, Marketing, Operations, G&A) across eight revenue and expense accounts over Q1 (Jan–Mar).

---

## What's inside

| Tab | Purpose |
|-----|---------|
| **Data** | Line-item budget vs. actual with live `Variance ($)`, `Variance (%)`, and a color-coded `Status` (Favorable / Unfavorable) flag. |
| **Summary** | Quarter P&L (Revenue → COGS → Gross Profit → Operating Expenses → Operating Income → Operating Margin %) with variances, a revenue-by-month table, and a Budget-vs-Actual chart. |
| **Forecast** | Driver-based Q2 (Apr–Jun) rolling forecast built off Q1 actuals, with an assumptions block and a Revenue vs. Operating Income chart. |

---

## Methodology

**Variance & favorability logic.** Variance = `Actual − Budget`. The favorability rule is sign-aware: for **revenue**, actual above budget is *Favorable*; for **costs (COGS/Opex)**, actual above budget is *Unfavorable* (an overspend). This is implemented with a nested `IF` keyed off each line's category.

**Roll-ups.** The Summary P&L aggregates the line items with `SUMIFS` by category and by month — the standard FP&A approach to building a P&L from a transaction-level dataset.

**Driver-based forecast.** Rather than copying prior actuals, the forecast is built from explicit drivers:
- **Revenue** compounds at a monthly growth assumption off the latest actual month.
- **COGS** flexes as a **percentage of revenue**, derived from Q1 actuals.
- **Operating Expenses** grow at a separate monthly assumption.
- Gross Profit, Operating Income, and Margin % all fall out as formulas.

**Color conventions** follow finance-modeling standards: **blue = hard-coded input assumptions**, **green = links pulling from other tabs**, black = calculations.

---

## Key insight from this dataset

Q1 **revenue beat budget by ~$28K (favorable)**, but **operating income landed ~$10.5K under plan** because operating expenses overran budget — driven largely by Digital Ads. This "favorable top line, unfavorable margin from overspend" pattern is exactly the kind of finding an FP&A analyst surfaces and explains to business partners.

---

## How to use

1. Open the workbook in Excel or Google Sheets.
2. On **Data**, edit any `Actual` value — the Summary dashboard and charts update automatically.
3. On **Forecast**, change the assumption cells (revenue growth, Opex growth) to run **upside / base / downside scenarios** and watch the Q2 P&L re-forecast instantly.

---

## Skills demonstrated

- Full-cycle FP&A: **budgeting, variance analysis, management reporting, forecasting**
- **Driver-based financial modeling** and scenario analysis
- Excel: `SUMIFS`, nested `IF` logic, dynamic referencing, conditional formatting, charting
- Financial-modeling best practices (assumption/calculation separation, color conventions)
- Translating numbers into a clear business narrative

---

## Author

**Jose Thomas** — M.S. Statistics & Data Science, B.S. Mathematics
[LinkedIn](https://www.linkedin.com/in/jose-thomas-852b67290/)
