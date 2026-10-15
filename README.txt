# Week 1 Data Engineering Lab

## Scenario
A small online shop sends daily order data as a CSV file. A manager wants a reliable summary of valid orders by city.

## Pipeline plan
- Source: `orders.csv` (daily batch file)
- Raw destination: BigQuery table `de_intro.raw_orders`
- Curated output: query results after checking and filtering the data
- User of the output: shop manager

## Local data check
Before reporting, record at least two issues you found in the CSV and what you recommend doing with each.

1. Issue: Order O-1005 has a quantity of 0, resulting in a total price of 0.00.
Recommendation: Verify the original order data and correct the quantity if it is a data-entry error; otherwise, confirm whether zero-quantity orders should be retained.
2. Issue: Order ID O-1006 appears twice in the CSV, with the same date, customer, and product details.
Recommendation: Check whether this is a duplicate record. If it is, remove the duplicate; otherwise, distinguish the records using a unique order or line-item ID.


## What the pipeline does
Complete after the lab: In one sentence, describe how the data moves from the source to a useful output.


- Rows loaded: 8 
- Rows with a missing city: 1 
- Rows with a non-positive quantity: 1 
- Rows returned by the filtered query: 5 