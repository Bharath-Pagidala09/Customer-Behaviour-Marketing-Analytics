# Customer Behaviour & Marketing Analytics — Smart Fresh Retail

## Overview
This project analyses customer spending behaviour for a fictional retail 
company called Smart Fresh Retail. Using R, I cleaned the dataset, ran 
statistical tests, applied factor analysis, and segmented customers into 
distinct groups to support better marketing decisions.

---

## What I Did

### 1. Data Cleaning
I removed customers born before 1950 as they have different spending 
patterns that could skew the analysis. I also created a new Age column 
for easier grouping. The dataset had only 23 missing values, so I used 
mean imputation rather than deletion to preserve as many records as 
possible. I also removed records where the last customer interaction 
was over 60 days ago and luxury spending was under £10, to keep the 
analysis focused on active buyers.

---

### 2. Descriptive Statistics
I focused on four key variables:

- **Annual Income** — right-skewed, showing income differences across customers
- **Spend on Luxury Goods** — skewed with a median of 28 vs mean of 48.4, 
  meaning a small number of big spenders pull the average up
- **Last Interaction** — near-uniform distribution with a mean of 45.68 days, 
  showing varied engagement over time
- **Purchases in Store** — mean of 5.96 with low variation, meaning most 
  customers visit stores a similar number of times

---

### 3. T-Tests (Hypothesis Testing)
I ran three t-tests to investigate key business questions:

**I. Do older customers shop in-store more than younger ones?**  
Yes — statistically significant (p = 0.0005663). Older customers average 
6.14 in-store purchases vs 5.59 for younger ones. This suggests older 
customers should be targeted with in-store promotions, while younger 
customers may respond better to loyalty rewards and experiential marketing.

**II. Do higher-income customers accept more promotions?**  
No — not statistically significant (p = 0.1523). Income does not 
meaningfully affect promotion acceptance, so the business should focus 
on behavioural factors like urgency-based offers and personalised 
discounts instead.

**III. Do recently inactive customers spend more on luxury goods?**  
Yes — statistically significant (p = 1.282e-05). Customers inactive for 
longer spend an average of £53.68 on luxury items when re-engaged, 
compared to £43.05 for recently active ones. This points to an opportunity 
for targeted re-engagement campaigns with premium deals.

---

### 4. Correlation Matrix
Key findings from the correlation analysis:
- Annual income and luxury spending are positively correlated — 
  higher earners spend more on luxury goods
- In-store purchases and luxury spending are also positively linked
- Younger customers show a slight tendency to accept more promotions
- Complaints have very little relationship with spending behaviour

---

### 5. PCA (Principal Component Analysis)
I selected 5 principal components, which together explain the most 
useful variance in the dataset:

- **PC1** — overall purchasing behaviour (meat, wine, luxury, store visits)
- **PC2** — demographics and offer acceptance (older customers, kids at home)
- **PC3** — promotional responsiveness (offers 3, 4 and latest response)
- **PC4** — online shopping activity (younger, more digitally engaged customers)
- **PC5** — promotion-sensitive customers who accept many offers but are 
  less likely to shop in-store or have high incomes

---

### 6. Customer Clustering (K-Means)
Using the elbow method, I identified 4 optimal customer clusters:

| Cluster | Profile | Key Behaviour |
|---|---|---|
| Cluster 1 | High-value food & drink buyers | Highest spending on wine and meat |
| Cluster 2 | Luxury shoppers | Highest luxury goods spending of all clusters |
| Cluster 3 | Budget-conscious | Lowest overall spending across all categories |
| Cluster 4 | Health-conscious | Highest spending on wellness and organic food |

These segments allow the business to tailor campaigns — premium offers 
for luxury spenders, discount deals for budget shoppers, and wellness 
incentives for health-conscious customers.

---

## Key Takeaway
Income alone does not drive customer behaviour. Age, recency of 
interaction, and spending category are stronger signals for targeted 
marketing. Segmenting customers using clustering enables Smart Fresh 
Retail to move away from broad promotions and towards personalised, 
behaviour-driven campaigns.

---

## Tools Used
- **R** — data cleaning, t-tests, PCA, clustering, correlation analysis
- **ggplot2** — visualisations (histograms, cluster plots, scree plot)
