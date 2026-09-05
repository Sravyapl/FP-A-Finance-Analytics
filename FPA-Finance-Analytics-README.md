# 💰 FP&A Finance Analytics

A finance/FP&A dashboard covering budget variance, revenue trends, and time-intelligence reporting for executive review.

## 📌 Overview

Built to mirror how a finance team tracks actuals against budget across periods — variance analysis, scenario comparison, and period-over-period trends, backed by a clean star schema.

## 🗂️ Data Model

- Star schema: 1 fact table + 6 dimension tables (including a dedicated Time and Scenario dimension)

## 📐 DAX

Time intelligence was the core challenge on this build, including fixing:
- `STARTOFWEEK` not being supported in the target engine — reworked with an alternative pattern
- An `Amount` column stored as text instead of numeric, breaking aggregations
- A "Period Parameter" that had accidentally been created as a measure instead of a disconnected table
- Base measures missing a `Scenario` filter, which was producing incorrect Net Income figures

Design rule: dynamic period-variance measures are scoped to Revenue, and only apply on the Time Intelligence page — kept isolated using `USERELATIONSHIP` so they don't leak into other pages' context.

## 📊 Dashboard

4 report pages: Overview, Revenue & Variance, Time Intelligence, and Scenario Comparison.

## 🛠️ Tech Stack

Power BI • DAX • Power Query

## 📄 Documentation

Full build documentation, including the DAX fixes above, is included as a Word document in this repo.

## 🖼️ Screenshots

*(add dashboard screenshots here)*
