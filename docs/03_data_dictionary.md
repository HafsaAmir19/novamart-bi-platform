# NovaMart Data Dictionary

One row = one product line in an order. The same order_id can appear on more than one row, so count unique order_id values to count orders. All money is in PKR.

| Column | Meaning | Type | Example | Rule |
|---|---|---|---|---|
| order_id | Order number | Text | ORD-100245 | Not empty |
| order_date | Day the order was placed | Date | 2026-03-15 | YYYY-MM-DD, not in the future |
| customer_id | Customer number | Text | CUST-004512 | Not empty |
| region | Delivery city | Text | Karachi | Karachi, Lahore, Islamabad, Rawalpindi, Faisalabad, Multan |
| product_id | Product number | Text | PRD-0231 | Not empty |
| product_category | Product group | Text | Electronics | Electronics, Fashion, Home, Groceries |
| sales_channel | Where the order was placed | Text | Website | Website, Mobile App, Social Media |
| payment_method | How the customer pays | Text | Cash on Delivery | Card, Cash on Delivery, Bank Transfer, Mobile Wallet |
| delivery_method | How it is delivered | Text | Standard | Standard, Express, Pickup Point |
| quantity | Items in this line | Whole number | 2 | At least 1. Over 10 needs checking |
| unit_price | Price of one item before discount | Decimal | 1000.00 | Above 0 |
| discount_pct | Discount in percent | Decimal | 10 | 0 to 100 |
| cost | What NovaMart paid for all items in this line | Decimal | 1200.00 | Above 0 |
| revenue | quantity x unit_price x (1 - discount_pct/100), before returns | Decimal | 1800.00 | Must match the formula |
| return_status | Was this line returned | Text | Not Returned | Returned, Not Returned |
| payment_status | Did the money arrive | Text | Paid | Paid, Pending, Failed, Refunded |
| amount_paid | Money actually received for this line | Decimal | 1800.00 | 0 or more |

Notes
- No column may be empty.
- Profit for now is revenue minus cost. Delivery cost and returns are not included. The final definition needs to be agreed with finance.
- Payments are saved per line here to keep things simple. A real system would keep them per order in a separate table.
- Cash on Delivery orders stay Pending until the courier hands over the money.
