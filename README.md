# 📊 Superstore Sales & Profit Analysis – Excel

_Analyzing four years of order-level sales data to uncover profitability drivers, seasonal demand, and top customer/state performance, while demonstrating core Excel skills (pivot tables, formulas, conditional formatting, text functions, and macros)._

---

## 📌 Table of Contents
- <a href="#overview">Overview</a>
- <a href="#business-problem">Business Problem</a>
- <a href="#dataset">Dataset</a>
- <a href="#tools--technologies">Tools & Technologies</a>
- <a href="#project-structure">Project Structure</a>
- <a href="#data-cleaning--preparation">Data Cleaning & Preparation</a>
- <a href="#exploratory-data-analysis-eda">Exploratory Data Analysis (EDA)</a>
- <a href="#research-questions--key-findings">Research Questions & Key Findings</a>
- <a href="#excel-skills-demonstrated">Excel Skills Demonstrated</a>
- <a href="#how-to-run-this-project">How to Run This Project</a>
- <a href="#final-recommendations">Final Recommendations</a>
- <a href="#author--contact">Author & Contact</a>

---
<h2><a class="anchor" id="overview"></a>Overview</h2>

This project analyzes 9,994 retail orders placed between 2014 and 2017 to understand how sales and profit are distributed across product categories, states, customers, and time. Alongside the analysis, the workbook was built as a hands-on Excel skills showcase — covering pivot tables, lookup/aggregation formulas, text functions, conditional formatting, and macros — all applied directly to a real transactional dataset.

---
<h2><a class="anchor" id="business-problem"></a>Business Problem</h2>

Understanding which products, regions, and customers actually drive profit — versus just revenue — is critical for pricing, discounting, and inventory decisions. This project aims to:
- Track total sales and profit growth year over year
- Identify which product categories and sub-categories drive revenue vs. which quietly lose money
- Profile monthly sales seasonality to support inventory and staffing planning
- Identify top-performing states and customers by sales
- Flag high-risk order patterns (large orders that still lose money)
- Demonstrate practical Excel techniques (formulas, pivots, conditional formatting, macros) on a real dataset

---
<h2><a class="anchor" id="dataset"></a>Dataset</h2>

- `salesdata__1_.csv` — raw order-level transactions (order date, customer name, state, category, sub-category, product name, sales, quantity, profit)
- Loaded into an Excel Table (`Salesdata`) inside `salesdataproject.xlsm` for formulas, pivot tables, and dashboarding

---
<h2><a class="anchor" id="tools--technologies"></a>Tools & Technologies</h2>

- Microsoft Excel (Tables, PivotTables, formulas, conditional formatting, macros/VBA)
- CSV data source

---
<h2><a class="anchor" id="project-structure"></a>Project Structure</h2>

```
superstore-sales-analysis/
│
├── README.md
├── salesdataproject.xlsm                 # Full workbook: raw data, pivots, dashboard, formulas, macros
├── salesdata__1_.csv                     # Raw dataset
├── Sales_Profit_Analysis_Report.md       # Full write-up of findings
```

---
<h2><a class="anchor" id="data-cleaning--preparation"></a>Data Cleaning & Preparation</h2>

- Found 1 fully duplicated row (a Laurel Beltran order in Ohio recorded twice) out of 9,994 records — flagged, not removed, in the source file
- Confirmed no missing values across any of the 9 columns (order date, customer, state, category, sub-category, product, sales, quantity, profit)
- Parsed `Order Date` into a proper date field and derived Year/Month columns to support trend and seasonality analysis
- Loaded the raw range into a structured Excel Table (`Salesdata`) so all formulas and pivots reference dynamic ranges
- Flagged 1,871 orders (18.7% of all orders) that shipped at a net loss, worth isolating from healthy orders in profitability analysis

---
<h2><a class="anchor" id="exploratory-data-analysis-eda"></a>Exploratory Data Analysis (EDA)</h2>

**Dataset Snapshot:**
- 9,994 orders total across 3 categories (Office Supplies, Furniture, Technology) and 17 sub-categories
- Orders span Jan 2014 – Dec 2017, placed by 793 unique customers across 49 states
- Total Sales: $2,297,201.07 · Total Profit: $286,397.79 · Total Units Sold: 37,873

**Data Quality Notes:**
- No missing values in any column
- One fully duplicated order row identified
- 1,871 orders (18.7%) recorded a negative profit despite positive sales

**Growth & Composition Insights:**
- Sales grew every year: $484K (2014) → $470K (2015) → $609K (2016) → $733K (2017)
- Profit grew even faster than sales: $49.5K (2014) → $61.6K (2015) → $81.8K (2016) → $93.4K (2017)
- Office Supplies accounts for 60.3% of order volume (6,026 orders) but only 42.7% of profit, while Technology drives the largest profit share (50.8%) from far fewer orders (1,847)
- Monthly sales are strongly seasonal, peaking in November ($352K) and September ($308K), and troughing in February ($60K)

---
<h2><a class="anchor" id="research-questions--key-findings"></a>Research Questions & Key Findings</h2>

1. **Sales & Profit by Category**: Technology leads profit ($145,456 from $836,154 in sales), Office Supplies contributes $122,491 in profit, while Furniture trails with only $18,451 in profit despite $741,999 in sales — the weakest margin of the three
2. **Sub-Category Profitability**: Copiers ($55,618), Phones ($44,516), and Accessories ($41,937) are the most profitable sub-categories; Tables (-$17,726), Bookcases (-$3,473), and Supplies (-$1,189) lose money overall and are the clearest candidates for pricing or discount-policy review
3. **Sub-Category Sales Volume**: Phones ($330,007) and Chairs ($328,168) are the top revenue-generating sub-categories, followed by Storage ($223,844), Tables ($206,966), and Binders ($203,413)
4. **Monthly Seasonality**: Sales climb sharply into Q4, with November ($352,461), December ($325,294), and September ($307,650) the three strongest months — useful for inventory and promotional timing
5. **Profit by Year & Category**: Technology's profit nearly tripled from $21,493 (2014) to $50,685 (2017); Furniture's profit was flat and volatile, actually dropping from $5,470 (2014) to $3,018 (2017)
6. **Top States by Sales**: California ($457,688), New York ($310,876), Texas ($170,188), Washington ($138,641), and Pennsylvania ($116,512) lead all states
7. **Top Customers by Sales**: Sean Miller ($25,043), Tamara Chand ($19,052), Raymond Buch ($15,117), Tom Ashbrook ($14,596), and Adrian Barton ($14,474) are the top 5 customers by total sales
8. **Customer Base Growth**: Unique customers placing orders grew from 595 (2014) to 693 (2017), tracking the overall sales growth
9. **Loss Outliers**: A single Cubify CubeX 3D Printer order in Ohio lost $6,600 on $4,500 in sales (5 units) — the single worst-performing order in the dataset; the largest sale overall, a $22,638 Cisco TelePresence System order in Florida, also lost $1,811

📄 Full write-up with tables and commentary: [`Sales_Profit_Analysis_Report.md`](./Sales_Profit_Analysis_Report.md)

---
<h2><a class="anchor" id="excel-skills-demonstrated"></a>Excel Skills Demonstrated</h2>

- **PivotTables**: Sales by category, profit by year & category, monthly sales, top 5 customers, sales by state, and customer counts by year
- **Formulas**: `SUM`, `SUMIF`, `SUMIFS`, `MAX` for total sales/profit and conditional lookups (e.g., total Office Supplies sales in Texas)
- **Text Functions**: `CONCAT` to merge Customer Name and State into a single field
- **Conditional Formatting**: a custom multi-condition rule highlighting orders where profit is negative, quantity exceeds 5, and sales exceed $150 — surfacing the riskiest high-volume, low-margin orders
- **Macros (VBA)**: automation routines included in the workbook's Macros sheet
- **Interactive Dashboard**: a consolidated Dashboard sheet tying the pivot outputs together into a single view

---
<h2><a class="anchor" id="how-to-run-this-project"></a>How to Run This Project</h2>

1. Clone the repository:
```bash
git clone https://github.com/yourusername/superstore-sales-analysis.git
```
2. Open `salesdataproject.xlsm` in Microsoft Excel (enable macros/content when prompted)
3. If prompted, point the data source to `salesdata__1_.csv` in the cloned folder
4. Refresh all PivotTables (Data > Refresh All) to recalculate against the current data
5. Review findings in [`Sales_Profit_Analysis_Report.md`](./Sales_Profit_Analysis_Report.md)

---
<h2><a class="anchor" id="final-recommendations"></a>Final Recommendations</h2>

- Review pricing and discounting on Tables, Bookcases, and Supplies — the only three sub-categories operating at a net loss
- Investigate high-value, low-margin orders (like the Cubify 3D Printer and Cisco TelePresence orders) individually; a handful of outliers are dragging down Furniture and Technology profit
- Double-check discount policy on Furniture broadly, since its profit margin lags far behind Office Supplies and Technology despite comparable sales
- Lean into Q4 seasonality (Sep–Dec) for inventory planning and promotional campaigns, since nearly a third of annual sales lands in these four months
- Prioritize retention for top customers (Sean Miller, Tamara Chand, and others) and top states (California, New York) given their outsized share of revenue
- Use the conditional-formatting rule already built into the workbook as a recurring monthly check to flag risky orders before they ship

---
<h2><a class="anchor" id="author--contact"></a>Author & Contact</h2>

**Your Name Here**
Data Analyst
📧 Email: your.email@example.com
🔗 [LinkedIn](https://www.linkedin.com/in/your-profile/)
