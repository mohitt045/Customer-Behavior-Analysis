# Customer Shopping Behavior Analysis

Analysis of 3,900 customer transactions to uncover spending patterns, customer segments, product preferences, and subscription behavior — built with **Python**, **PostgreSQL**, and **Power BI**.

## Overview

This project explores a retail transactions dataset to answer a set of business questions around revenue, customer loyalty, discounting, and product performance, then presents the findings in an interactive dashboard.

**Pipeline:** `Python (clean & prepare)` → `PostgreSQL (business queries)` → `Power BI (dashboard)`

## Dataset

| | |
|---|---|
| Rows | 3,900 transactions |
| Columns | 18 |
| Missing data | 37 values in `Review Rating` |

**Fields cover:**
- **Customer demographics** — Age, Gender, Location, Subscription Status
- **Purchase details** — Item Purchased, Category, Purchase Amount, Season, Size, Color
- **Shopping behavior** — Discount Applied, Promo Code Used, Previous Purchases, Frequency of Purchases, Review Rating, Shipping Type

## Tech Stack

- **Python** (`pandas`) — data loading, cleaning, and feature engineering
- **PostgreSQL** — structured business-question queries
- **Power BI** — interactive dashboard for stakeholders

## Data Preparation

- Checked structure and summary statistics with `df.info()` and `.describe()`
- Imputed missing `Review Rating` values using the median rating per product category
- Standardized all column names to `snake_case`
- Engineered `age_group` (binned ages) and `purchase_frequency_days` columns
- Checked `discount_applied` vs. `promo_code_used` for redundancy and dropped `promo_code_used`
- Loaded the cleaned DataFrame into PostgreSQL for SQL analysis

## Business Questions Answered (SQL)

1. Revenue by gender
2. High-spending customers who still used a discount
3. Top 5 products by average review rating
4. Standard vs. Express shipping — average purchase amount
5. Subscribers vs. non-subscribers — spend and revenue
6. Top 5 most discount-dependent products
7. Customer segmentation — New / Returning / Loyal
8. Top 3 products per category
9. Repeat buyers (>5 purchases) vs. subscription status
10. Revenue by age group

## Key Findings

- **Male customers generate ~2.1x** the revenue of female customers ($157,890 vs. $75,191)
- **Clothing** is the anchor category, led by Blouses and Pants (171 orders each)
- Only **27% of customers are subscribed**, yet subscribers spend almost the same per order as non-subscribers — non- subscribers still drive 73% of total revenue
- **839 customers** used a discount and still spent above the $59.76 average order
- **Hat, Sneakers, and Coat** are the most discount-dependent products (~49–50% of purchases discounted)
- Revenue is broadly even across age groups (within an 11% band)
- **3,116 of 3,900 customers (80%)** fall into the "Loyal" segment

## Recommendations

- **Boost Subscriptions** — promote exclusive benefits for subscribers
- **Customer Loyalty Programs** — reward repeat buyers to move them into the "Loyal" segment
- **Review Discount Policy** — balance sales boosts with margin control
- **Product Positioning** — highlight top-rated and best-selling products in campaigns
- **Targeted Marketing** — focus on high-revenue categories and express-shipping users

## Dashboard

An interactive Power BI dashboard presents customer counts, average purchase amount, average review rating, revenue and sales by category, revenue and sales by age group, and subscription status — filterable by gender, category, and shipping type.

## Repository Structure

```
.
├── data/                  # Raw and cleaned datasets
├── notebooks/             # Python data cleaning & EDA
├── sql/                   # PostgreSQL business-question queries
├── dashboard/             # Power BI (.pbix) file
└── README.md
```
