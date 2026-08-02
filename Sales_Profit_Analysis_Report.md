# Superstore Sales & Profit Analysis — Full Report

## 1. Dataset Overview

| Metric | Value |
|---|---|
| Total Orders | 9,994 |
| Date Range | Jan 3, 2014 – Dec 30, 2017 |
| Unique Customers | 793 |
| States Represented | 49 |
| Categories | 3 (Office Supplies, Furniture, Technology) |
| Sub-Categories | 17 |
| Total Sales | $2,297,201.07 |
| Total Profit | $286,397.79 |
| Total Units Sold | 37,873 |
| Overall Profit Margin | 12.5% |

Data quality: no missing values in any of the 9 fields (order date, customer name, state, category, sub-category, product name, sales, quantity, profit). One fully duplicated order row was found (a Laurel Beltran order from Ohio, April 23, 2014) and flagged rather than silently dropped.

---

## 2. Year-over-Year Growth

| Year | Orders | Sales | Profit |
|---|---|---|---|
| 2014 | 1,993 | $484,247.56 | $49,544.06 |
| 2015 | 2,102 | $470,532.46 | $61,618.69 |
| 2016 | 2,587 | $609,205.86 | $81,795.27 |
| 2017 | 3,312 | $733,215.19 | $93,439.77 |

Order volume grew 66% from 2014 to 2017, and profit nearly doubled over the same period — profit grew faster than sales, indicating improving overall margin discipline even though, as shown below, that improvement wasn't uniform across categories.

The number of unique customers placing orders each year also climbed steadily: 595 (2014) → 573 (2015) → 638 (2016) → 693 (2017).

---

## 3. Category & Sub-Category Performance

### Sales, Profit, and Units by Category

| Category | Orders | Sales | Profit | Units | Profit Margin |
|---|---|---|---|---|---|
| Office Supplies | 6,026 | $719,046.99 | $122,490.88 | 22,906 | 17.0% |
| Furniture | 2,121 | $741,999.98 | $18,451.25 | 8,028 | 2.5% |
| Technology | 1,847 | $836,154.10 | $145,455.66 | 6,939 | 17.4% |

Furniture stands out immediately: it generates nearly as much revenue as Technology but converts almost none of it to profit (2.5% margin vs. ~17% for the other two categories).

### Profit by Sub-Category (highest to lowest)

| Sub-Category | Profit |
|---|---|
| Copiers | $55,617.90 |
| Phones | $44,516.25 |
| Accessories | $41,936.78 |
| Paper | $34,053.34 |
| Binders | $30,221.64 |
| Chairs | $26,590.15 |
| Storage | $21,279.05 |
| Appliances | $18,138.07 |
| Furnishings | $13,059.25 |
| Envelopes | $6,964.10 |
| Art | $6,527.96 |
| Labels | $5,546.18 |
| Machines | $3,384.73 |
| Fasteners | $949.53 |
| Supplies | -$1,188.99 |
| Bookcases | -$3,472.56 |
| Tables | -$17,725.59 |

Three sub-categories operate at a net loss — Supplies, Bookcases, and, most significantly, Tables. Tables alone erases nearly a third of Furniture's already-thin margin story, and is the single clearest pricing/discount problem in the catalog.

### Sales by Sub-Category (top 5)

| Sub-Category | Sales |
|---|---|
| Phones | $330,007.10 |
| Chairs | $328,167.76 |
| Storage | $223,843.59 |
| Tables | $206,965.68 |
| Binders | $203,412.77 |

Tables ranks 4th in revenue but dead last in profit — the clearest volume-vs-margin mismatch in the dataset.

### Profit by Year and Category

| Year | Furniture | Office Supplies | Technology |
|---|---|---|---|
| 2014 | $5,469.77 | $22,593.40 | $21,492.95 |
| 2015 | $3,015.17 | $25,099.55 | $33,503.97 |
| 2016 | $6,959.93 | $35,061.24 | $39,774.10 |
| 2017 | $3,018.44 | $39,736.69 | $50,684.64 |

Office Supplies and Technology profit both grew consistently and substantially over the four years. Furniture profit, by contrast, is flat and volatile — actually lower in 2017 ($3,018) than in 2014 ($5,470) despite Furniture's overall sales growing across the same period. This is consistent with the Tables sub-category's persistent losses dragging the whole category down.

---

## 4. Seasonality: Monthly Sales

| Month | Sales |
|---|---|
| Jan | $94,924.87 |
| Feb | $59,751.26 |
| Mar | $205,005.51 |
| Apr | $137,480.79 |
| May | $155,028.83 |
| Jun | $152,718.72 |
| Jul | $147,238.11 |
| Aug | $159,043.99 |
| Sep | $307,649.96 |
| Oct | $200,323.03 |
| Nov | $352,461.09 |
| Dec | $325,293.54 |

Sales are strongly back-half-weighted. September, November, and December alone account for roughly 41% of annual sales, while February is the weakest month by a wide margin. This pattern should directly inform inventory build-up and promotional calendars ahead of Q4.

---

## 5. Geographic Performance

Top 10 states by sales:

| State | Sales |
|---|---|
| California | $457,687.68 |
| New York | $310,876.20 |
| Texas | $170,187.98 |
| Washington | $138,641.29 |
| Pennsylvania | $116,512.02 |
| Florida | $89,473.73 |
| Illinois | $80,166.16 |
| Ohio | $77,976.84 |
| Michigan | $76,269.61 |
| Virginia | $70,636.72 |

California alone accounts for roughly 20% of total company sales — nearly 1.5x the next closest state (New York). At the other end, low-volume states like North Dakota ($919.91), Maine ($1,270.53), West Virginia ($1,209.82), and Wyoming ($1,603.14) each contribute well under 0.1% of sales, suggesting limited market penetration outside a core set of large states.

---

## 6. Top Customers

| Rank | Customer | Sales |
|---|---|---|
| 1 | Sean Miller | $25,043.07 |
| 2 | Tamara Chand | $19,052.22 |
| 3 | Raymond Buch | $15,117.35 |
| 4 | Tom Ashbrook | $14,595.62 |
| 5 | Adrian Barton | $14,473.57 |

These five customers alone contributed $88,281.83 in sales — about 3.8% of total company revenue from just 0.6% of the customer base — making them clear priorities for account management and retention efforts.

---

## 7. Risk & Outlier Orders

- 1,871 of 9,994 orders (18.7%) shipped at a net loss, despite all having positive sales values — meaning discounting or cost issues are eating margin on nearly 1 in 5 orders.
- The single worst order in the dataset: a Cubify CubeX 3D Printer (Double Head) sold to Cindy Stewart in Ohio (Nov 25, 2016) — $4,499.99 in sales across 5 units, resulting in a $6,599.98 loss.
- The single largest sale in the dataset: a Cisco TelePresence System EX90 sold to Sean Miller in Florida (Mar 18, 2014) for $22,638.48 across 6 units — which itself still lost $1,811.08.

Both outliers sit in the Technology category's Machines sub-category, suggesting that large, heavily-discounted equipment orders are a recurring source of margin erosion even in Technology's otherwise strong profit performance.

---

## 8. Excel Techniques Applied

This analysis was built entirely in Excel (`salesdataproject.xlsm`) using:

- **PivotTables** for every aggregation above (category, sub-category, year × category, monthly, state, top customers, customer counts)
- **Formulas**: `SUM` and `MAX` for headline totals; `SUMIF` / `SUMIFS` for conditional aggregations (e.g., total Office Supplies sales, or total Office Supplies sales specifically in Texas)
- **Text functions**: `CONCAT` to combine Customer Name and State into a single descriptive field
- **Conditional formatting**: a custom rule flagging any order where profit is negative, quantity exceeds 5, and sales exceed $150 — a practical filter for identifying high-volume, high-risk, unprofitable orders at a glance
- **Macros (VBA)** for repeatable automation tasks within the workbook
- A consolidated **Dashboard** sheet bringing the pivot outputs together into one interactive view

---

## 9. Recommendations

1. **Fix Tables pricing/discounting.** Tables is the only sub-category losing more than a few thousand dollars overall (-$17,726); review discount thresholds and supplier costs specifically for this line.
2. **Audit large Technology "Machines" orders individually.** Both the worst single loss and the single largest sale in the entire dataset come from this sub-category — a small number of deeply discounted big-ticket orders may be responsible for a disproportionate share of losses.
3. **Investigate Furniture's stagnant margin.** Despite steady sales growth, Furniture's profit hasn't grown in four years; Tables and Bookcases losses are likely the main drag.
4. **Plan inventory and promotions around the Sep–Dec surge.** Nearly 41% of annual sales lands in these four months; under-stocking risks lost sales, over-stocking ties up capital in slower months like February.
5. **Prioritize top customers and top states.** California, New York, and the top 5 customers represent an outsized share of revenue and are natural targets for loyalty or account-management programs.
6. **Operationalize the conditional-formatting rule.** The existing "negative profit + quantity > 5 + sales > $150" rule is a ready-made monthly checkpoint for catching risky orders before or shortly after they ship.
