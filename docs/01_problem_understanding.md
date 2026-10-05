# NovaMart: Problem Understanding

## 1. The CEO's email (summary)

The CEO of NovaMart (a fictional online store in Pakistan) says:
- Sales are growing, but profit is not.
- Returns seem to be going up.
- Finance spends days every month building Excel reports.
- Order system numbers and payment numbers never match.
- He does not trust the data.
- The operations manager thinks some transactions look strange.

## 2. Problems found: symptom or possible cause

| Problem | Type | Note |
|---|---|---|
| Profit is inconsistent | Symptom | Possible causes: heavy discounts, low-margin categories, delivery cost, wrong cost data, returns |
| Returns seem to be going up | Hypothesis | Not measured yet. Could also be a cause of low profit |
| Order and payment numbers do not match | Likely root cause | Probably causes the distrust |
| CEO does not trust the data | Symptom (consequence) | Core problem of the project |
| Some transactions look strange | Symptom | Needs investigation |
| Reports are made by hand in Excel | Process problem | Slow, not repeatable. This is where automation comes in |

## 3. Questions I would ask the CEO

| Bucket | Question |
|---|---|
| Decision | What decision will you make differently once you have trusted numbers? |
| Definition | When you say "profit", do you mean before or after returns, discounts and shipping costs? |
| Data | Which system does your finance team treat as final when the order and payment numbers disagree, and who owns it? |
| Scope / Success | How will we know in 3 months that this worked? |

## 4. Is a dashboard the right solution?

A dashboard alone is not enough. The core issue is trust in the data. If the source data is inconsistent, a dashboard would only show wrong numbers in a more convincing way. First we agree on definitions (like profit), set one source of truth, and clean the data. The dashboard comes last.

## 5. Problem statement

NovaMart's management has a problem: sales are growing but profit is not, and they do not trust the data. This matters because profit may be leaking and nobody knows where, and the finance team loses days every month on manual reports. We will know it worked when orders and payments match (or the differences are listed and explained), profit by region and category uses a definition that finance agrees on, and the monthly report no longer needs days of manual work.

## 6. Five business questions

| # | Question | Area |
|---|---|---|
| 1 | Which product category has the lowest profit margin, and how much lower is it than the company average? | Profit |
| 2 | How much money did we give away in discounts last quarter, and which category got the biggest discounts? | Discounts |
| 3 | Is the return rate higher this quarter than last quarter, and which region has the highest rate? | Returns, regions |
| 4 | What percentage of orders have no matching payment, or a payment with a different amount? | Data trust, payment mismatch |
| 5 | How many orders have a value far above normal for their category, and which cities and payment methods do they come from? | Suspicious transactions |

Note: "far above normal" in question 5 will be defined after we see the real data.

## 7. "So what" example (question 3)

If the South region has a return rate of 14% and the company average is 6%:
1. First, break the number down by category, channel and delivery method to see where returns are concentrated.
2. Then ask the operations manager to investigate the cause together with us (delivery delays, packaging, product issues).
3. Do not blame anyone before checking the facts.
