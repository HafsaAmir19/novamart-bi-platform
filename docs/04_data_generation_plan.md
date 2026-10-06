# NovaMart: Data Generation Plan

The data is fake (synthetic). No real people or companies. I add mistakes on purpose so I can find and fix them later, like an analyst would with real data.

Target size: about 50,000 order lines. The percentages below are planned numbers, not measured results. After generating the data I will check whether profiling finds roughly these amounts.

| Column | Problem | Example messy values | Planned % of rows |
|---|---|---|---|
| region | Same city written in different ways | karachi, KHI, Karchi, KARACHI | 3 |
| product_category | Inconsistent names | electronics, Electronic, Home & Kitchen | 2 |
| quantity | Invalid value | 0, -1, 250 | 0.5 |
| order_date | Wrong format, future date, too old | 19,10,2026 / 2027-03-01 / 1996-05-12 | 1 |
| payment_status | Words not in the allowed list | Processing, paid, PAID, empty | 1.5 |
| amount_paid | Negative, higher than revenue, or empty | -700, 9999, empty | 1 |
| amount_paid vs revenue | Money paid does not match the revenue | revenue 1800, paid 1500, status Paid | 3 |
| customer_id | Missing value | empty | 1.5 |
| whole row | Exact duplicate row | same row twice | 1 |
| order_id | Same order_id used for different orders | ORD-100245 on two different customers | 0.5 |
| revenue | Suspicious very high value for the category | a 500,000 value in Groceries | 0.5 |

Together, about 10 to 15 percent of rows have at least one problem. Some rows have more than one.

Not planned as an error:
- Cash on Delivery orders that are Pending for a few days are normal.
- Cash on Delivery orders that stay Pending for a very long time are suspicious.

Other rules for the data:
- The data also has one planted pattern in returns, so there is something real to find later. The details are not written here, so the analysis stays honest.
- Revenue follows the formula: quantity x unit_price x (1 - discount_pct / 100).
