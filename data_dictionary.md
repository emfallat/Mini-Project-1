# Data Dictionary — clean_online_retail.csv

Final columns in the cleaned, completed-sales dataset (522,716 rows).

| Column | Type | Description |
|---|---|---|
| `invoice_no` | text | Transaction ID. All cancelled invoices (leading `C`) have been removed from this dataset. |
| `stock_code` | text | Product code. Non-product codes (POST, DOT, M, BANK CHARGES, AMAZONFEE) have been removed. |
| `description` | text | Product name. Cleaned (whitespace stripped, title-cased). Rows with a blank description were removed. |
| `quantity` | integer | Units sold per line. Only positive values remain (returns/cancellations removed). |
| `invoice_date` | datetime | Timestamp of the transaction, parsed to a proper datetime type. |
| `customer_id` | text/float | Customer number. Rows with no customer ID on the original export are labeled `'GUEST'` rather than a real ID — exclude these when doing per-customer analysis. |
| `country` | text | Customer country. Labels standardized (`EIRE` -> `Ireland`, `RSA` -> `South Africa`); `'Unspecified'` converted to missing. |
| `revenue` | float | Line-item revenue, calculated as `quantity * unit_price`. `unit_price` itself was dropped after this was computed. |
| `region` | text | Broader region for the customer's country, added via a merge with a hand-built country-to-region lookup table. Missing for a few countries not covered by the lookup (e.g. Ireland, Iceland, South Africa). |