# Enterprise Insurance Claims Analytics Dashboard 📊

## 📌 Project Overview
Monitoring financial liabilities, claim leakages, and settlement efficiency is critical in the insurance industry. This Power BI project is an end-to-end analytical solution designed to provide executive-level insights into claim settlements, rejection rates, and year-over-year (YoY) financial impact.

## 🎯 Business Objectives Answered
* **Financial Tracking:** What is the total claim amount vs. the approved payout?
* **Operational Efficiency:** What is the current Settlement Ratio and Rejection Rate?
* **Trend Analysis:** How do current Year-to-Date (YTD) claims compare against Last Year's performance?
* **Deep-Dive:** Which geographical regions and policy types (Auto, Health, Life) drive the highest financial liabilities?

## ⚙️ Technical Architecture & Data Modeling
This project moves beyond flat-file reporting by implementing a robust, enterprise-grade data model:
* **Star Schema Design:** Built a highly optimized data model connecting `FactClaims` with multiple dimension tables (`DimDate`, `DimRegion`, `DimPolicy`) using 1-to-Many (*:1) single-direction relationships.
* **Custom Date Dimension:** Engineered a dynamic Calendar table using DAX (`CALENDAR(MIN, MAX)`) to ensure perfect chronological sorting and accurate time intelligence without relying on auto-date/time bloat.

## 🧠 Advanced DAX Implementations
* **Context Transition:** Leveraged `CALCULATE` to manipulate filter contexts for status-specific metrics (e.g., `Approved Claims %`).
* **Iterators:** Utilized `AVERAGEX` over the Fact table to accurately compute row-by-row ticket sizes.
* **Time Intelligence:** Implemented dynamic `TOTALYTD` (with `ISBLANK` logic to prevent future-date carryovers) and `SAMEPERIODLASTYEAR` for precise YoY Growth % calculations.
* **Variable Optimization:** Used `VAR` within DAX measures to store intermediate results, improving both code readability and engine performance.
