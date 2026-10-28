# Empowering Gen-Z: Career Aspirations – Excel Dashboard

An interactive Excel dashboard that shows what Gen Z (born 1997+) expect to **earn** and how and where they want to **work**. It is driven entirely by live formulas, with dropdown filters and a salary slider, so every chart and KPI updates as you change the filters.

> **Data note:** The dataset is **simulated (synthetic)**. Only the India 2022–23 baseline is calibrated to a real career-aspirations survey (n = 3,343). All other markets, years, and trends are modelling assumptions. Use this project for learning, dashboard design, and analysis practice, not for real hiring or pay decisions.

## Screenshot

![Excel dashboard](screenshots/excel_dashboard.png)

## Project Overview

- **Goal:** Give an HR-style view of Gen Z salary expectations and work-setup preferences.
- **Tool:** Microsoft Excel (formulas, charts, form controls).
- **Data:** 25,000 survey responses, 8 waves, 18 countries, December 2022 – September 2026.
- **Questionnaire:** GZ-CORE 1.0, a single locked questionnaire (54 items, 9 sections) used for every wave and market.

## Dashboard Features

**Filters**
- **Region** dropdown: All, South Asia, Southeast Asia, North America, Europe, Africa, Latin America
- **Gender** dropdown: All, Man, Woman, Non-binary, Prefer not to say, Prefer to self-describe
- **Salary slider** (scroll-bar form control): sets a minimum expected 5-year salary from $0 to $10,000 per month, in $250 steps

**KPI cards**
- Total respondents (valid responses only)
- Average starting salary (USD per month)
- Average 5-year expected salary (USD per month)
- Expected salary growth (5-year salary ÷ starting salary)
- Average preferred office days per week
- Share who prefer hybrid or remote (3 or fewer office days)

**Charts (8)**
1. Average starting vs 5-year salary by region
2. Expected 5-year salary bands (% of respondents)
3. Average starting vs 5-year salary by education level
4. Average 5-year salary by preferred work setup
5. Preferred office days per week
6. Preferred work setup (doughnut)
7. Extra pay needed to work on-site
8. Pay vs flexibility trade-off (doughnut)

**Key Insights:** three sentences on pay growth, preferred work mode, and the pay-vs-flexibility trade-off. They are written by formulas, so they update with the filters.

## Workbook Structure

| Sheet | Purpose |
|---|---|
| **Dashboard** | Filters, KPI cards, 8 charts, and auto-generated key insights |
| **Read Me** | Study description, analysis rule, and data caveats |
| **Questionnaire** | All 54 questions with response types, options, and the decision each informs |
| **FX Rates** | Currency conversion assumptions (editable inputs) |
| **Markets & Waves** | Rollout plan and live response counts by country and year |
| **Responses** | 25,000 survey rows × 87 columns (the main data table) |
| **Baseline Calibration** | Compares the synthetic India 2022–23 baseline with the real 2023 survey |
| **Trends** | India trend 2022–2026, plus a 2026 snapshot by world region |
| **Dash_Calc** | Calculation layer that feeds the Dashboard |

## How It Works

1. **Responses** holds the survey data. Two formula columns convert local-currency salaries (starting and 5-year) into USD using the **FX Rates** sheet.
2. **Dash_Calc** reads the Region, Gender, and salary-slider selections from the Dashboard and calculates every KPI and chart table from valid responses only (`quality_status = "Valid"`).
3. The **Dashboard** displays those results in cards and charts and builds the insight sentences.

**Excel functions used:** `COUNTIFS`, `AVERAGEIFS`, `SUMIFS`, `SUBTOTAL`, `INDEX` / `MATCH`, `IF`, `IFERROR`, `ROUND`, `TEXT`, `MAX`.

## How to Use

1. Download `GenZ_Career_Aspirations_Dashboard_slider_ready.xlsx` and open it in **desktop Excel**.
2. Go to the **Dashboard** sheet.
3. Pick a region and gender from the dropdowns and drag the salary slider.
4. To use different exchange rates, edit the blue cells in **FX Rates**. The USD salary columns update automatically.

> The slider is an Excel form control. It works in desktop Excel but may not work in Excel Online, Google Sheets, or LibreOffice.

## Data Quality Notes

- About 5% of rows are flagged as speeders, failed attention checks, or a 5-year salary below the starting salary. The dashboard uses **valid responses only**.
- Salary averages are means, so they are sensitive to outliers, and they depend on the FX assumptions (2026 rates are estimates).
- Some 2023 questions had no clean equivalent in the new questionnaire. Where the mapping was indirect, the baseline target is an analyst judgement, documented in **Baseline Calibration**.

## Skills Demonstrated

Excel dashboard design, interactive filters and form controls, formula-driven KPIs and charts, data cleaning rules and quality flags, currency conversion, trend analysis, and documentation.

## Author

**Vansh Gupta**
GitHub: [github.com/vanshguptaa14](https://github.com/vanshguptaa14)
LinkedIn: [linkedin.com/in/vansh-gupta-62a117305](https://linkedin.com/in/vansh-gupta-62a117305)
