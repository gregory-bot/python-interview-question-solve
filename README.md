# python-interview-question-solve
interview solve

# 🏡 Airbnb Data Analysis – LeetCode-Style Challenge

This repository recreates an **online technical assessment** as a local, LeetCode-style data analytics challenge.  
The focus is on **data cleaning, business logic, and analytical reasoning using Python & Pandas**.

The setup mirrors a real-world test environment where data is loaded via a shared loader module and each task is solved independently.

---

## 📌 Objective

Analyze Airbnb listings and reviews data to answer business-driven questions such as:

- Pricing behavior
- Host professionalism impact
- Seasonal demand patterns
- Revenue estimation
- Customer activity trends

---

## 🗂 Project Structure

```text
airbnb-analysis/
│
├── src/
│   ├── data_loader.py      # Loads listings & reviews data (API/CSV simulation)
│   ├── task1.py            # Average listing price
│   ├── task2.py            # Short-stay listings
│   ├── task3.py            # Professional vs non-professional hosts
│   ├── task4.py            # Reviews in last 365 days
│   ├── task5.py            # Best expected revenue listing
│   ├── task6.py            # Listings per neighbourhood
│   └── task7.py            # Host with most listings
│
├── tests/
│   └── test_main.py        # Unit tests (similar to online grader)
│
├── requirements.txt
└── README.md
📊 Dataset Overview
Listings (df_listings)
Column	Description
id	Listing ID
host_id	Host identifier
price	Nightly price (string: $1,200)
minimum_nights	Minimum stay
neighbourhood_cleansed	Location
calculated_host_listings_count	Number of listings per host

Reviews (df_reviews)
Column	Description
listing_id	Listing ID
date	Review date

🔌 Data Loading
All data is loaded through a shared loader to simulate an API-based system used in the online test.

python
Copy code
df_listings, df_reviews = load_data()
You are not expected to modify the loader logic.

🧩 Problems
Task 1 – Average Listing Price
Compute the average nightly price after cleaning currency symbols.

Task 2 – Short-Stay Listings
Count listings with minimum_nights ≤ 7.

Task 3 – Professional vs Non-Professional Hosts
A host is professional if they manage 5 or more listings.
Return the difference in average price:

nginx
Copy code
professional − non_professional
Task 4 – Reviews in the Last Year
Count reviews posted in the last 365 days.

Task 5 – Best Expected Revenue Listing
Estimate expected revenue using:

ini
Copy code
guests = reviews_last_year / 0.6
expected_revenue = guests × minimum_nights × price
Return the listing with the highest expected revenue.

Task 6 – Listings per Neighbourhood
Return a dictionary mapping neighbourhoods to listing counts.

Task 7 – Host with Most Listings
Return the host_id owning the most listings.

🧪 Testing
Run all tests locally (mirrors the online grader):

bash
Copy code
pytest
🛠 Installation
bash
Copy code
pip install -r requirements.txt
🧠 Skills Evaluated
Data cleaning & preprocessing

Pandas aggregations & joins

Time-series filtering

Business metric formulation

Writing testable Python code

Translating real-world questions into logic

🎯 Notes
Each task is intentionally isolated

Functions must be deterministic

Focus is on clarity over cleverness

Assumptions must be handled safely

🚀 Author
Gregory Kipngeno
Data | BI | Analytics | Engineering
