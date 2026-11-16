# 🏗️ Automated Interim Payment Application (IPA) & Commercial Reconciliation Engine

![Python](https://img.shields.io/badge/Python-3.10%2B-blue)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analytics-150458)
![OpenPyXL](https://img.shields.io/badge/OpenPyXL-Excel%20Automation-217346)
![Domain](https://img.shields.io/badge/Domain-Commercial%20Management%20%26%20QS-orange)

## 📌 Executive Overview
In large-scale infrastructure and construction projects, reconciling the Main Contractor's monthly **Interim Payment Application (IPA)** against the Supervision Consultant's (**CSC / Engineer**) certified measurement sheets is typically a manual, error-prone process across disconnected spreadsheets.

This Python ETL pipeline automates the commercial reconciliation workflow. It ingests raw BOQ claim logs and CSC certification sheets, calculates item-by-item quantity and financial variances, flags unapproved BOQ overruns requiring Variation Orders (VOs), and exports a color-coded **Excel Audit Workbook** alongside a **Gamma Executive Presentation Deck**.

---

## 🚀 Key Commercial & Technical Features
* **Automated Discrepancy Detection:** Instantly calculates the delta between *Current Claimed Quantities* and *CSC Certified Quantities*, isolating exact financial deductions per package.
* **Contract Overrun Guardrails:** Automatically flags line items where cumulative claimed quantities exceed original Contract BOQ quantities (`CRITICAL: BOQ Overrun - VO Required`).
* **Conditional Excel Formatting (`openpyxl`):** Generates a multi-tab Excel report with automated row highlighting (Red for high-value deductions/overruns, Yellow for moderate holds) without manual Excel intervention.
* **Executive Presentation Pipeline:** Auto-generates structured Markdown summaries ready for instant conversion into executive slide decks via **Gamma** and **Power BI**.

---

## 🛠️ Architecture & Tech Stack
1. **Data Ingestion & Cleaning (`pandas`, `numpy`):** Standardizes BOQ item codes, unit rates, previous certified baselines, and current cycle measurements.
2. **Commercial Rules Engine:** Evaluates cumulative progress percentages, deduction thresholds, and retention/advance recovery deductions.
3. **Automated Reporting (`openpyxl`):** Writes formatted `.xlsx` deliverables with executive rollup tabs and audit logs.
4. **BI & Presentation Integration:** Exports clean tables for **Power BI** dashboards and Markdown scripts for **Gamma** executive briefings.

---

## 📊 Sample Output Metrics (IPA-32 Audit Cycle)
| Package | Gross Claimed (SAR) | CSC Certified (SAR) | Disputed / Deducted (SAR) | Primary Hold Reason |
| :--- | :---: | :---: | :---: | :--- |
| **Earthworks** | 842,500.00 | 765,100.00 | 77,400.00 | As-Built Level Discrepancy |
| **Stormwater** | 615,200.00 | 558,400.00 | 56,800.00 | Pending Joint Survey Sign-off (WIR) |
| **Utilities** | 920,000.00 | 920,000.00 | 0.00 | Fully Certified |
| **Pavement** | 1,110,400.00 | 943,840.00 | 166,560.00 | Compaction Test Report Pending |

---

