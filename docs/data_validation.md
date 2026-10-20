# Data Cleaning, Processing & Validation

**Project:** Vrinda Store — Annual Sales Analysis (2022)  
**Tool:** Microsoft Excel  
**Source reviewed:** `Vrinda Store Data Analysis.xlsx`  
**Scope:** Historical 2022 transaction-level sales data

## 1. Purpose

Document the dataset structure, observable preparation steps, numerical validation, quality considerations, and reporting limitations so the 2022 dashboard can be interpreted and reproduced responsibly.

> **Verification standard:** The final workbook shows the *result* of preparation and analysis, but it does not contain a complete change log. The checks below distinguish verified workbook evidence from cleaning operations that would require the analyst's process notes to substantiate.

## 2. Source and workbook structure

| Item | Verified observation |
|---|---|
| Data worksheet | `Vrinda Store` |
| Source range | `A1:U31048` (header + 31,047 records) |
| Source fields | 21 columns |
| Date coverage | All 31,047 stored date values fall in 2022 |
| Report sheet | `Vrinda Store Report 2022` |
| Reporting assets | 6 PivotTable definitions, 12 chart objects, 3 slicers |
| Recorded sales | **₹21,176,377** (sum of `Amount`) |
| Unique nonblank Order IDs | **28,471** |
| Source row count | **31,047** |

The workbook includes customer identifiers and shipping-location information. The original file should **not** be placed in a public GitHub repository before assessing privacy, redistribution rights, hidden worksheets and PivotTable caches.

## 3. Data cleaning and quality assessment

| Check | Finding | Interpretation / action |
|---|---|---|
| Nulls | No blank stored values were detected in the 20 reviewed business fields (`B:U`) | Completeness in the saved file is verified; whether missing values were removed or imputed earlier is **not** established |
| Date validity | 31,047 stored dates are in calendar year 2022 | Report date scope is consistent |
| Repeated Order IDs | 31,047 rows versus 28,471 distinct IDs; 2,576 occurrences beyond the first | Repeated IDs **must not automatically be deleted**; an order may contain multiple line items |
| Reporting month | Excel `TEXT(date,"mmm")` formula observed in `Month` field | Month labels were derived from transaction date; use calendar order rather than alphabetical sort |
| Age groups | `Age Group` is present in data and summaries | Exact age cutoffs/derivation could not be confirmed from the final workbook; do not invent thresholds |
| Categories / geography | Grouping fields are available for PivotTable reporting | Standardization rules and before/after cleaning counts are not independently documented |
| Pivot reporting | `Count of Order ID` measures nonblank **rows** | It is not a DISTINCTCOUNT of orders |

### Cleaning work log (complete with your actual steps)

The following are **documentation prompts, not claims that these operations were verified**:

- Missing-value treatment: `[Describe the checks or fixes you actually performed]`
- Duplicate-row handling: `[Describe how you differentiated duplicate rows from multi-line orders]`
- Formatting / standardization: `[Describe date, text, category, state or amount fixes you performed]`
- Data-type validation: `[Describe how you checked numeric, date and text columns]`
- Outliers / invalid records: `[Describe any tests performed and their outcomes]`

Remove placeholders before publishing if you do not have a corresponding documented step.

## 4. Data processing and reporting logic

- **Monthly sales:** `SUM(Amount)` grouped by reporting month.
- **Monthly transaction rows:** PivotTable `Count of Order ID`, grouped by reporting month.
- **Gender sales:** `SUM(Amount)` grouped by Gender.
- **Order status:** row count grouped by Status.
- **State ranking:** `SUM(Amount)` grouped by shipping state.
- **Channel share:** row count per channel divided by the total number of transaction rows.
- **Age-group share:** row count per recorded Age Group divided by the total number of transaction rows.
- **Category sales:** `SUM(Amount)` grouped by Category.

**Important:** These computations describe the *saved workbook's metrics*. `Amount` has not been independently reconciled to cash collections or returns-adjusted net revenue.

## 5. Reconciliation checks

| Control total / check | Result |
|---|---:|
| 2022 transaction rows | 31,047 |
| Distinct Order IDs | 28,471 |
| Difference: repeated-ID occurrences | 2,576 |
| Annual Amount sum | ₹21,176,377 |
| March sales (highest month) | ₹1,928,066 |
| March transaction rows | 2,819 |
| Women sales | ₹13,562,773 |
| Men sales | ₹7,613,604 |
| Gender sales reconciled | ₹21,176,377 |
| Delivered | 28,641 rows |
| Returned | 1,045 rows |
| Cancelled | 844 rows |
| Refunded | 517 rows |
| Status counts reconciled | 31,047 rows |

The public aggregate CSV files under [`../data/aggregated/`](../data/aggregated/) are suitable for checking the dashboard's summary measures without releasing original customer-level records.

## 6. Reporting limitations

1. **Order-count definition:** Row counts and distinct Order IDs are not interchangeable. Dashboard order-volume charts count rows.
2. **Returns and refunds:** Status categories have not been used to adjust the `Amount` aggregate; treat it as **recorded sales**, not verified net revenue.
3. **Age ranges:** The workbook shows `Adults`, `Teenagers` and `Senior`, but the age-band boundaries were not fully verified.
4. **No causality:** Historic rankings do not prove that a given marketing action will drive growth in 2023.
5. **Privacy:** A copied workbook can retain sensitive values in hidden sheets, old PivotTable caches, connections and metadata even if columns are hidden.
6. **Sharing rights:** Confirm the source dataset's license or sharing permission before public release.

## 7. Public-release checklist

- [ ] Confirm permission to publish the source or derived dataset.
- [ ] Use aggregated CSV reports rather than original customer-level data, unless an anonymized release has been reviewed.
- [ ] Check hidden sheets, PivotTable caches, external connections, named ranges and document properties in any public Excel workbook.
- [ ] Confirm dashboard totals and charts against the aggregate reports.
- [ ] Clearly describe row-count versus distinct-order metrics.
- [ ] Document only the cleaning actions actually performed.
- [ ] Remove unfinished placeholders from this file before release.

---

**Related:** [Business insights & recommendations](business_insights.md) · [Project README](../README.md)
