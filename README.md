# UPI Transaction Analytics

A comprehensive end-to-end data analysis portfolio project built in Microsoft Excel. This project transforms over **500,000 raw financial transaction records** into a dynamic, self-service executive dashboard to uncover critical payment performance insights and failure trends within the Indian Unified Payments Interface (UPI) ecosystem.

---

## Executive Summary & Objective

As UPI transaction volumes grow exponentially, payment service providers require real-time visibility into transaction health, app market share, and failure patterns. 

**The Objective:** To analyze a high-volume dataset and build a dynamic dashboard that enables stakeholders to monitor KPIs, evaluate payment app performance (e.g., PhonePe, Google Pay, Paytm), and identify operational bottlenecks—all without relying on expensive BI infrastructure.

## Dataset

- **Scale:** 500,000+ transaction records.
- **Attributes:** Transaction ID, Timestamps, UPI App, Merchant Details, Status (Success/Failed), Amounts (standardized in INR ₹), and Failure Reasons.
- **Access:** *Note: Due to GitHub's file size limits, the raw dataset and the working analytical file are hosted externally.*
  - [Download Raw Data & Analytic Excel File Here](https://drive.google.com/drive/folders/1PJGB6H1r0-MMIGDJY3df3ikkGagdMy_F?usp=sharing) 

## Data Scope & Analyst Actions

1. **Data Cleaning & Formatting:** Standardized raw timestamps, resolved date syntax errors, and eliminated null/blank entries to establish a clean source dataset.
2. **Feature Engineering:** Extracted temporal dimension attributes (e.g., `Hour of Day`, `Day of Week`) from raw timestamps to enable granular time-series and peak-traffic evaluation.
3. **Performance Optimization:** Optimized calculation pipelines and flattened intermediate data structures (Paste as Values) to prevent Excel from crashing and to support high-speed interactive filtering across half a million rows.

## Dashboard Architecture

To ensure clean UI separation, prevent lag, and maintain scalability, the solution was built using a structured **three-tier architecture**:

| Layer | Sheet Name | Function & Responsibilities |
| :--- | :--- | :--- |
| **1. Backend** | `Raw_Data` | Stores static transaction logs. Includes helper columns calculated once and flattened to preserve system memory. |
| **2. Middleware** | `Calc_KPI / Pivots` | Houses underlying Pivot Tables, dynamic aggregation structures, and helper logic using robust data retrieval formulas (e.g., `GETPIVOTDATA` + `IFERROR`). |
| **3. Frontend** | `Dashboard` | A highly polished, non-grid presentation layer featuring dynamic KPIs, interactive slicers, dual-axis charts, and conditional formatting heatmaps. |

## Key Analytical Insights Uncovered

### 1. Payment Performance & Failure Rates
- **Failure Rate Disparities:** Transaction success rates varied noticeably across payment apps, identifying specific platforms with elevated technical decline rates during peak usage.
- **Temporal Peak Stress Points:** Hour-by-hour matrix analysis (Heatmap) revealed concentrated traffic bursts during evening hours (**18:00–21:00**), correlating directly with increased transaction latency and status drop-offs.

### 2. App Ecosystem & Market Share Trends
- **Volume Distribution:** Market share analysis highlighted heavy transaction concentration among top-tier apps (PhonePe, Google Pay), while smaller apps showed higher average order values (AOV).
- **Demographic & Regional Patterns:** Transaction volume distributions underscored key high-density geographic corridors driving the majority of financial throughput.

## From Insight to Impact (Business Value)

This dashboard moves beyond simply tracking metrics; it connects clean data to specific operational decisions:

*   **Proactive Server Load Balancing:** Recommended infrastructure capacity adjustments during the identified 18:00–21:00 peak window to reduce technical decline rates.
*   **Targeted App Partnership Focus:** Identified partner apps requiring targeted technical routing support to improve their specific transaction completion rates.
*   **Continuous Monitoring Loop:** Established a framework to track volume, success rate, latency, and drop-offs simultaneously, enabling a continuous loop of detection, validation, and improvement.
