# Food Delivery Dataset Analysis

A comprehensive data analysis project that merges and analyzes food delivery data from multiple sources to extract business insights about restaurants, users, orders, and revenue patterns.

## Overview

This project processes and analyzes food delivery data from three different sources (CSV, JSON, and SQL) to provide actionable insights for business decision-making. The analysis covers customer behavior, restaurant performance, revenue patterns, and membership trends.

## Dataset

The project integrates data from three sources:

- **orders.csv** - Order transaction data
- **users.json** - User profile and membership information
- **restaurants.sql** - Restaurant details and ratings

### Final Dataset Schema

| Column | Type | Description |
|--------|------|-------------|
| order_id | int64 | Unique order identifier |
| user_id | int64 | Customer identifier |
| restaurant_id | int64 | Restaurant identifier |
| order_date | object | Date of order (DD-MM-YYYY) |
| total_amount | float64 | Order value in currency |
| restaurant_name | object | Name of the restaurant |
| name | object | Customer name |
| city | object | City location (Bangalore, Chennai, Hyderabad, Pune) |
| membership | object | Membership tier (Gold, Regular) |
| cuisine | object | Cuisine type (Indian, Chinese, Italian, Mexican) |
| rating | float64 | Restaurant rating (3.0-5.0) |

**Total Records:** 10,000 orders

## Requirements

```
pandas
sqlite3
```

## Installation

```bash
pip install pandas
```

## Usage

Run the Jupyter notebook to execute the complete analysis:

```bash
jupyter notebook hackathon.ipynb
```

The script will:
1. Load data from SQL, CSV, and JSON sources
2. Merge datasets on common keys
3. Perform data cleaning and transformation
4. Generate the final consolidated dataset: `final-food_delivery_dataset.csv`

## Key Analyses

### 1. Revenue Analysis
- **Gold Member Revenue by City**: Chennai leads with ₹1,080,909.79
- **Highest Average Order Value**: Mexican cuisine at ₹808.02
- **Top Rating Revenue**: 4.8-rated restaurants generate ₹657,707.71

### 2. Customer Insights
- **High-Value Customers**: 2,544 users with total orders > ₹1,000
- **Gold Member Contribution**: 50% of total revenue
- **Total Unique Users**: 2,883 customers

### 3. Restaurant Performance
- **Best Performing Restaurant**: Restaurant_294 with ₹1,040.22 average order value (< 20 orders)
- **Cuisine Distribution**: Chinese cuisine has 120 distinct restaurants with ₹1,930,504.65 revenue

### 4. Temporal Patterns
- **Peak Quarter**: July to September with ₹2,037,385.10 revenue
- **Gold Member Orders**: 4,987 orders

### 5. Geographic Analysis
- **Hyderabad Revenue**: ₹1,889,367
- **Gold Member Hotspot**: Chennai with 1,337 orders

## Key Findings

1. **Gold members drive significant value** - Contributing 50% of revenue with higher average order values (₹797.15)
2. **Mexican cuisine commands premium pricing** - Highest average order value across all cuisines
3. **High ratings correlate with revenue** - 4.8-rated restaurants generate maximum revenue
4. **Q3 is peak season** - July-September shows highest order volume
5. **Chennai is the gold member hub** - Highest gold member revenue and order count

## Project Structure

```
hackathon/
│
├── hackathon.ipynb          # Main analysis notebook
├── README.md                # Project documentation
├── orders.csv               # Order data (source)
├── users.json               # User data (source)
├── restaurants.sql          # Restaurant data (source)
├── restaurants.db           # SQLite database (generated)
└── final-food_delivery_dataset.csv  # Merged output dataset
```

## Data Processing Pipeline

1. **Data Loading**
   - Read SQL file and create SQLite database
   - Load CSV order data
   - Parse JSON user data
   - Query restaurant data from database

2. **Data Integration**
   - Merge orders with users on `user_id`
   - Merge result with restaurants on `restaurant_id`
   - Handle duplicate columns

3. **Data Transformation**
   - Convert date strings to datetime objects
   - Create quarter labels for temporal analysis
   - Clean and standardize column names

4. **Export**
   - Save consolidated dataset to CSV

## Business Recommendations

1. **Focus on Gold Member Retention** - They contribute 50% of revenue
2. **Expand Mexican Cuisine Offerings** - Highest average order value
3. **Promote High-Rated Restaurants** - Strong correlation with revenue
4. **Target Chennai Market** - Highest gold member concentration
5. **Seasonal Campaigns** - Leverage Q3 peak season

## Author

Data Analysis Project - Food Delivery Insights

## License

This project is available for educational and analytical purposes.
