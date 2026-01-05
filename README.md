# Airbnb Data Analysis Challenge  
**LeetCode-Style Pandas Problem Set (Reconstructed from Online Coding Test)**

This repository contains a set of 7 Pandas-based data analysis problems inspired by a real Airbnb-themed online coding assessment. Perfect for practicing data manipulation, cleaning, grouping, merging, and datetime operations in Python with Pandas.

Ideal for interview preparation (data analyst, data scientist, backend roles involving data processing).

## Problem Overview

You work with two datasets:

- **`df_listings`**: Airbnb listings  
  Columns: `id`, `host_id`, `price` (string like "$1,200.00"), `minimum_nights`, `neighbourhood_cleansed`, `host_listings_count`, `calculated_host_listings_count`

- **`df_reviews`**: Reviews  
  Columns: `listing_id`, `date` (string)

Implement 7 analytical functions as described below.

## Project Structure

airbnb-analysis/
├── src/
│   ├── data_loader.py      # Load or simulate data (replace with real CSVs if desired)
│   ├── task1.py            # Average Price of Listings
│   ├── task2.py            # Short-stay Listings Count
│   ├── task3.py            # Professional vs Non-Professional Host Price Difference
│   ├── task4.py            # Reviews in Last Year
│   ├── task5.py            # Best Expected Revenue Listing
│   ├── task6.py            # Listings per Neighbourhood
│   └── task7.py            # Host with Most Listings
├── tests/
│   └── test_main.py        # Sample unit tests
└── README.md

## Problems

### Task 1: Average Listing Price
Return the average price of all listings (clean `$` and `,` from the price string).

```python
def average_listing_price(df_listings: pd.DataFrame) -> float:

Task 2: Count Short-Stay ListingsCount listings where minimum_nights <= 7.python

def count_short_stay_listings(df_listings: pd.DataFrame) -> int:

Task 3: Professional vs Non-Professional Host Price DifferenceProfessional host = calculated_host_listings_count >= 5.
Return avg_price_professional - avg_price_non_professional.python

def prof_nonprof_host_price_diff(df_listings: pd.DataFrame, df_reviews: pd.DataFrame) -> float:

Task 4: Reviews in the Last YearCount reviews from the last 365 days (current date: January 05, 2026).python

def reviews_last_year(df_reviews: pd.DataFrame) -> int:

Task 5: Listing with Best Expected RevenueFilter listings with minimum_nights <= 7.
Expected revenue = (reviews_last_year / 0.6) × minimum_nights × price
Return the id of the listing with highest revenue (lowest ID in case of tie).python

def listing_with_best_expected_revenue(df_listings: pd.DataFrame, df_reviews: pd.DataFrame) -> int:

Task 6: Listings per NeighbourhoodReturn a dictionary: {neighbourhood: count}.python

def listings_per_neighbourhood(df_listings: pd.DataFrame) -> dict:

Task 7: Host with Most ListingsReturn the host_id with the highest number of listings.python

def host_with_most_listings(df_listings: pd.DataFrame) -> int:

Setup & Running Locallybash

# Clone the repo
git clone https://github.com/your-username/airbnb-data-analysis.git
cd airbnb-data-analysis

# Create virtual environment
python -m venv venv
source venv/bin/activate    # Windows: venv\Scripts\activate

# Install dependencies
pip install pandas pytest

Data LoadingEdit src/data_loader.py to load real data (e.g., from CSV files or Kaggle Airbnb datasets):python

import pandas as pd

def load_data():
    df_listings = pd.read_csv("data/listings.csv")
    df_reviews = pd.read_csv("data/reviews.csv")
    return df_listings, df_reviews

Run Testsbash

pytest tests/test_main.py -v

