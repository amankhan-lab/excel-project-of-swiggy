# excel-project-of-swiggy
# Swiggy Sales Analytics Dashboard (Excel)

An interactive Excel dashboard that analyses Swiggy dish listings and orders across India, covering sales, ratings and popularity by geography, time, category and veg / non-veg type.

> This was my first Excel project. Everything here (the data model, pivot tables, charts and dashboard) is built in Excel.

<!-- Add a screenshot of your Dashboard sheet here, e.g.:
![Dashboard preview](images/dashboard.png)
-->

---

## Key Numbers

| KPI | Value |
|---|---|
| Total Sales | ₹ 53.01 M |
| Total Orders | 197,430 |
| Average Order Value | ₹ 268.51 |
| Average Rating | 4.34 |
| Total Rating Count | 5.59 M |

**Coverage:** 1 Jan 2025 – 31 Aug 2025 · 28 states (one city per state) · 993 restaurants

---

## What I Found

- **Veg dishes drive the revenue.** Veg accounts for about ₹ 35.3 M (~67%) of sales versus ₹ 17.7 M (~33%) for non-veg.
- **Bengaluru is far ahead of every other city.** It brings in about ₹ 5.46 M (~10% of all sales). Lucknow, Hyderabad, Mumbai and New Delhi follow, in that order.
- **KFC is the top restaurant by sales** (₹ 4.25 M), followed by McDonald's, Pizza Hut, Burger King and Domino's.
- **Sales are steady month to month.** They stay between ₹ 6.3 M and ₹ 6.8 M. January is the highest month, and February is the lowest (it is also the shortest).
- **Weekly pattern is fairly flat.** Saturday is the strongest day (₹ 7.78 M) and Tuesday the weakest (₹ 7.36 M), a gap of under 6%.
- **Ratings barely move.** The average stays around 4.34 in every quarter.
- **Q3 looks lower only because it is incomplete.** The data stops at 31 Aug, so Q3 contains just July and August.

---

## Workbook Structure

| Sheet | What it contains |
|---|---|
| **Dashboard** | The final interactive dashboard: KPI cards, charts, map and filter panel (slicers) |
| **Analysis** | All pivot tables that feed the dashboard |
| **Top 5 restaurants** | Top 5 restaurants by sales |
| **Description** | Project purpose, coverage, and definitions of KPIs and charts |
| **Sheet1** | Helper pivot table used for the monthly trend |
| **Swiggy Data** | The raw dataset (an Excel Table named `Table1`) |

---

## Dashboard Components

**KPIs:** Total Sales · Average Rating · Average Order Value · Total Rating Count · Total Orders

**Charts:**
- Monthly Sales Trend
- Daily (day-of-week) Sales Trend
- Weekly Sales Trend
- Sales by Food Type (Veg vs Non-veg)
- Quarterly Performance (sales, rating and orders)
- Sales by State (filled map chart)
- Top 5 Cities by Sales
- Total Sales, Rating & Orders by Store

**Filters (slicers):** Month · Restaurant Name · Category · Food type

---

## Dataset

The `Swiggy Data` sheet has **197,430 rows** and these columns:

| Column | Description |
|---|---|
| State, City | Location of the order |
| Order_id | Order identifier (`USER_001`, …) |
| Order Date | Date of the order |
| Day, Quarter, Week | **Calculated columns** derived from Order Date (see below) |
| Restaurant Name, Location | Restaurant and its area |
| Category | Menu category (e.g. Snack, Recommended) |
| Dish Name | Name of the dish |
| Food type | Veg / Non-veg |
| Price (INR) | Price of the dish |
| Rating, Rating Count | Dish rating and number of ratings |

**Data source:** _add where the data came from (e.g. Kaggle link) here._

---

## Excel Skills Used

- **Excel Tables** with structured references (`Table1[[#This Row],[Order Date]]`)
- **Calculated columns** using formulas:
  - Day of week: `=TEXT([@[Order Date]],"ddd")`
  - Quarter: `="Q" & INT((MONTH([@[Order Date]])-1)/3)+1`
  - ISO week number: `=ISOWEEKNUM([@[Order Date]])`
- **PivotTables** for every aggregation (sum of sales, average rating, order counts)
- **PivotCharts** (line, bar, doughnut) and a **Map chart** for state-level sales
- **Slicers** connected to multiple pivot tables for one-click filtering
- **Dashboard design:** KPI cards, consistent layout and navigation labels

---

## How to Use

1. Download `Project_2.xlsx` from this repository.
2. Open it in **Microsoft Excel** (desktop; Microsoft 365 or Excel 2019+ is recommended because the state map is a filled map chart).
3. Go to the **Dashboard** sheet.
4. Use the **Filter Panel** slicers to explore sales by month, restaurant, category and food type.
5. Check the **Analysis** sheet to see how each chart is built, and the **Description** sheet for definitions.

> **Note:** The file is about 25 MB because it holds the full dataset plus pivot caches, so it may take a moment to open. The interactive features (slicers, map) only work in desktop Excel, not in GitHub's preview, which is why a screenshot above is helpful.

---

## Possible Improvements

- Add data for Sep–Dec so quarterly comparisons are complete
- Add a restaurant-level rating vs. sales analysis
- Rebuild the dashboard in Power BI or Tableau for comparison

---

## Author

**Amankhan Pathan**

Feel free to open an issue or reach out with feedback. As this is my first Excel project, suggestions are very welcome!
