# Findings

## 1. Seasonality
Total revenue for the year was **£10,266,083.79**. Revenue peaked in **November 2011**
(£1,453,265.98) and was lowest in **February 2011** (£508,081.54). November was about
**84% higher than an average month**.

Monthly Revenue Trend:

![alt text](<Monthly Revenue Trend-1.png>)


## 2. Best sellers
**Top 10 by revenue:** Regency Cakestand 3 Tier (£174,157), Paper Craft Little Birdie
(£168,470), White Hanging Heart T-Light Holder (£104,284), Party Bunting (£99,445), Jumbo Bag
Red Retrospot (£94,160), Medium Ceramic Top Storage Jar (£81,701), Rabbit Night Light
(£66,870), Paper Chain Kit 50'S Christmas (£64,876), Assorted Colour Bird Ornament (£58,928),
Chilli Lights (£54,096).
 
**Top 10 by units sold:** Paper Craft Little Birdie (80,995), Medium Ceramic Top Storage Jar
(78,033), World War 2 Gliders Asstd Designs (54,951), Jumbo Bag Red Retrospot (48,371), White
Hanging Heart T-Light Holder (37,580), Popcorn Holder (36,749), Pack Of 72 Retrospot Cake
Cases (36,396), Assorted Colour Bird Ornament (36,362), Rabbit Night Light (30,739), Mini
Paint Set Vintage (26,633).
 
**6 of 10 products appear on both lists.** They are not the exact same list and one major difference is that the **Regency
Cakestand 3 Tier** is the single biggest revenue earner (£174,157) but isn't on the
units top 10 at all. This means that it is a higher-priced item selling in smaller volume. The **Popcorn Holder**,
by contrast, sold 36,749 units but never reaches the revenue top 10, which means it is a cheap, high-volume item. This tells me that the higher priced items drive revenue more than the cheaper but higher volume items. 

## 3. Markets
Outside the UK, the top revenue markets are **Netherlands** (£283,889), **Ireland**
(£276,091), **Germany** (£205,381), **France** (£184,679), and **Australia** (£138,104).

By region, **Western Europe** is at **£891,311** (driven by Netherlands,
Germany, France, and the other Western European countries combined), followed by **Oceania**
(£138,104, almost entirely Australia) and **Nordics** (£105,840). 
 
By distinct customer count, **Germany leads with 94 customers**, followed by **France (88)**,
**Spain (30)**, **Belgium (25)**, and **Switzerland (22)**.
 
**Where to expand:** Netherlands and Ireland lead on revenue (£283,889 and £276,091) so I would expand to either one of those. 

Top Markets:

![alt text](top_markets-1.png)


## 4. Customer concentration
The top 10 customers by total spend (excluding the `GUEST` placeholder for unidentified
customers) are: **14646** (£279,138), **18102** (£259,657), **17450** (£194,391), **16446**
(£168,473), **14911** (£140,337), **12415** (£124,565), **14156** (£117,210), **17511**
(£91,062), **12346** (£77,184), and **16029** (£72,708).
 
Out of **4,334** identified customers, the **top 1% (43 customers) account for 32.0% of total revenue**. This is a wholesale-driven business because there's not that many individual shoppers contributing and a third of all revenue comes from just 43 customers. 


## 5. Order value
The average order value (revenue per invoice) across all customers is **£519.04**. UK orders
average **£488.03**, while non-UK orders average **£815.12**. Non-UK orders are roughly
**1.7x higher** than UK orders on average. 

## 6. Returns & cancellations
**9,288 raw rows (1.71% of all rows)** were cancellations, worth **-£896,812.49** in value.
 
The products most associated with cancellations are: **Paper Craft Little Birdie** (-80,995 units), **Medium Ceramic Top Storage Jar** (-74,494), **Rotating Silver
Angels T-Light Holder** (-9,376), a generic **Manual** adjustment (-4,066), and **Fairy Cake
Flannel Assorted Colour** (-3,150). 

## 7. Data-quality memo
Of the 541,909 raw rows, **19,193 (≈3.5%)** were removed during cleaning including cancellations,
non-product lines, invalid prices/quantities, blank descriptions, and exact duplicates.
Missing `customer_id` (~25% of rows) was kept and labeled `GUEST` rather than dropped, since
those rows still represent real completed sales revenue. I would trust this dataset for a board report since it removes missing values, removes duplicates, deletes unncessary rows/columns like descriptions and is labeled well. 