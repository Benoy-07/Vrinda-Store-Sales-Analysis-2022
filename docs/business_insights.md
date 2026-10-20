# Business Insights & Recommendations

**Vrinda Store | Annual Sales Report 2022**  
**Business goal:** Understand 2022 customers and sales patterns to identify practical experiments for increasing sales in 2023.  
**Source:** Verified summary values from the project's Excel workbook.

## Executive summary

Vrinda Store recorded **₹21,176,377** in sales across **31,047 transaction rows** in 2022 (representing **28,471 distinct Order IDs**). **March** produced the highest monthly revenue. Women accounted for approximately **64.05%** of recorded sales, **Maharashtra** was the leading state, and **Amazon** represented the largest share of transaction rows. **Sets** were the strongest product category by revenue.

> **Metric note:** The workbook's `Count of Order ID` reports nonblank transaction rows, **not** distinct orders. Channel, age-group, monthly order volume and status percentages below use this row-based measure. Revenue is the sum of `Amount`, not independently verified returns-adjusted net revenue.

## Performance at a glance

| KPI | Verified 2022 result |
|---|---:|
| Total recorded sales | **₹21,176,377** |
| Transaction rows | **31,047** |
| Distinct Order IDs | **28,471** |
| Best month (revenue) | **March — ₹1,928,066** |
| Best month (transaction rows) | **March — 2,819** |
| Leading state | **Maharashtra — ₹2,990,221** |
| Largest category | **Set — ₹10,507,546** |
| Delivered transaction rows | **28,641 (92.25%)** |

## 1. Monthly sales trends

- **March** led both recorded sales (**₹1,928,066**) and transaction rows (**2,819**).
- **November** had the lowest recorded sales (**₹1,615,356**) and the fewest transaction rows (**2,383**).
- Revenue fluctuated across the year and was generally weaker in the last quarter than during the first quarter.

**Business interpretation:** The March peak is a useful starting point for investigating campaign periods, product availability and seasonal factors. A single year does not establish a repeatable seasonal pattern.

**Recommended next step:** Compare promotional calendars, traffic and conversion rates for strong versus weak months; test time-bound campaigns and evaluate incremental revenue.

[Underlying aggregate: monthly sales](../data/aggregated/monthly_sales.csv)

## 2. Customer and demographic segments

| Segment | Recorded sales | Share of sales |
|---|---:|---:|
| Women | ₹13,562,773 | **64.05%** |
| Men | ₹7,613,604 | **35.95%** |

- The workbook labels **15,543 transaction rows** as **Adults**, approximately **50.06%** of all rows.
- Other recorded groups: **Teenagers — 9,415 rows**; **Senior — 6,089 rows**.
- The age-band boundaries were not independently validated, so no precise age-range claims are made.

**Business interpretation:** Women are the largest revenue-contributing gender segment in this dataset. However, revenue share alone does not establish conversion rate, profitability or customer lifetime value.

**Recommended next step:** Test women-focused product recommendations and relevant campaigns; use consent-based audience selection and measure conversion, repeat purchases and margin.

[Gender breakdown](../data/aggregated/sales_by_gender.csv) · [Age-group breakdown](../data/aggregated/age_group_distribution.csv)

## 3. Geographic opportunities

| Rank | State | Recorded sales | Share of annual sales |
|---:|---|---:|---:|
| 1 | Maharashtra | ₹2,990,221 | 14.12% |
| 2 | Karnataka | ₹2,646,358 | 12.50% |
| 3 | Uttar Pradesh | ₹2,104,659 | 9.94% |
| 4 | Telangana | ₹1,712,439 | 8.09% |
| 5 | Tamil Nadu | ₹1,678,877 | 7.93% |

The top three states—Maharashtra, Karnataka and Uttar Pradesh—generated approximately **36.56%** of annual recorded sales.

**Business interpretation:** These markets have demonstrated demand and are candidates for targeted merchandising and fulfillment experiments. Raw sales volume does not indicate market saturation or advertising efficiency.

**Recommended next step:** Pilot state-specific offers and compare cost per acquisition, conversion, returns and profit contribution against a control group.

[Top 10 states](../data/aggregated/top_10_states.csv)

## 4. Marketplace / channel performance

| Channel | Transaction rows | Share of rows |
|---|---:|---:|
| Amazon | 11,016 | 35.48% |
| Myntra | 7,254 | 23.36% |
| Flipkart | 6,703 | 21.59% |

Together these three platforms accounted for approximately **80.44%** of transaction rows.

**Business interpretation:** Marketplace activity is concentrated in three channels, but these shares **do not measure channel revenue, conversion, fees or profitability**.

**Recommended next step:** Analyze channel-specific revenue, marketing costs, cancellation/return rates and margins before reallocating promotional spend.

[Channel distribution](../data/aggregated/channel_distribution.csv)

## 5. Product-category opportunities

| Category | Recorded sales | Share of annual sales |
|---|---:|---:|
| Set | ₹10,507,546 | 49.62% |
| Kurta | ₹4,959,377 | 23.42% |
| Western Dress | ₹3,148,836 | 14.87% |

**Business interpretation:** The **Set** category contributes almost half of recorded sales, making it important to inventory and assortment planning.

**Recommended next step:** Review stockouts and returns for leading categories; test product bundles or cross-selling without assuming revenue share equals profitability.

[Category sales](../data/aggregated/category_sales.csv)

## 6. Fulfillment quality

| Recorded status | Transaction rows | Share of rows |
|---|---:|---:|
| Delivered | 28,641 | 92.25% |
| Returned | 1,045 | 3.37% |
| Cancelled | 844 | 2.72% |
| Refunded | 517 | 1.67% |

**Business interpretation:** Most records are marked delivered. Status rates are row-level, so they should not be presented as unique-order-level fulfillment rates.

**Recommended next step:** Break down cancellations, refunds and returns by category, marketplace and state; investigate issues such as product descriptions, sizing and delivery delays where supporting evidence exists.

[Status distribution](../data/aggregated/order_status.csv)

## 2023 action plan

| Priority | Proposed action | KPI to monitor |
|---|---|---|
| High | Pilot campaigns for relevant women-focused product segments | Incremental revenue, conversion, gross margin |
| High | Optimize assortment and replenishment in Set and Kurta categories | Stockout rate, sell-through, return rate |
| High | Evaluate Amazon, Myntra and Flipkart beyond transaction counts | Channel revenue, contribution margin, cancellation rate |
| Medium | Test region-specific campaigns in top-performing states | Incremental sales, acquisition cost, repeat purchase |
| Medium | Diagnose low-performing months before campaign planning | Monthly revenue, traffic, conversion |
| Medium | Investigate return and cancellation drivers | Return and cancellation rates by channel/category |

## Important caveats

- These are **historical descriptive findings**, not proof of causation or a 2023 forecast.
- Sales is defined as the source `Amount` total; it is not verified net sales after refunds or returns.
- Age groups are reproduced as recorded in the workbook; the exact age thresholds require source confirmation.
- `Count of Order ID` in the dashboard counts **rows**, not unique Order IDs.
- Public repository files contain only approved/aggregate outputs; avoid publishing original customer identifiers or shipping-level details.

---

**Related:** [Data validation & methodology](data_validation.md) · [Project README](../README.md)
