# Cleaning Decisions Log

Judgment calls made while cleaning `data.csv`, and why.

1. **Country labels** — Replaced `EIRE` -> `Ireland`, `RSA` -> `South Africa`, and
   `Unspecified` -> missing. These were just inconsistent labels for real countries (or not a
   country at all), so standardizing them avoids splitting/miscounting in country-level totals.

2. **Missing `customer_id` (135,080 rows, ~25%)** — I kept these rows but filled the missing values with `'GUEST'`. These still
   look like real completed sales (real products, quantities, prices), so dropping them would
   have thrown away a quarter of total revenue. Keeping them under a shared placeholder lets
   them stay in revenue/product totals while being excluded from customer-level analysis. The reason for not removing them is because it is 25% of the dataset, which would skew the remaining values.

3. **Missing `description` (1,454 rows)** — Dropped. No usable product information to keep,
   and it's a small enough share of the data that dropping it has little impact.

4. **Dropped `unit_price`** — Removed after using it to calculate `revenue`. None of the
   business questions need raw per-unit price once revenue exists, so it was redundant.

5. **Removed cancellations, non-product codes, and bad prices/quantities (12,518 rows)** —
   These aren't real product sales (cancelled orders, postage/fees, invalid £0 or negative
   values), so they'd distort any revenue calculation if I left it in.

6. **Removed exact duplicate rows (5,221 rows)** — Duplicates matched on every field, almost
   certainly the same line re-exported rather than a real repeat transaction. If I had left them in, they'd double-count revenue.

7. **Left join instead of inner join for region lookup** — An inner join would have silently
   dropped rows from countries not in the lookup table (e.g. Ireland, Iceland, South Africa —
   thousands of real rows). A left join keeps all rows and leaves `region` blank for those
   instead, which is safer for a market analysis question.


## Overall impact

| Stage | Rows |
|---|---|
| Raw | 541,909 |
| After cleaning | 522,716 |
| Removed/repaired | ~19,193 (about 3.5%) |

(Missing customer IDs aren't counted as "removed" since those rows were kept.)