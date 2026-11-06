# Airbnb Singapore Price Analysis | Data Analysis with Python

## Business Question
What factors influence Airbnb nightly prices in Singapore, and where and what type of listing should a new host choose to maximise potential revenue?

## Dataset
| Item | Details |
|---|---|
| Name | Airbnb Singapore listings |
| Source | [ADD SOURCE LINK HERE] |
| Rows | 3,208 |
| Columns | 90 (14 used for the analysis) |
| Rows after cleaning | 2,645 |
| Currency | USD per night |

**Columns used:**

| Column | Meaning |
|---|---|
| listing_url | Link to the listing |
| price | Nightly price |
| room_type | Entire home/apt, Private room, Hotel room, Shared room |
| neighbourhood_group_cleansed | Region of Singapore |
| neighbourhood_cleansed | Neighbourhood |
| accommodates | Number of guests the listing sleeps |
| bedrooms, beds | Number of bedrooms and beds |
| minimum_nights | Minimum stay required |
| availability_365 | Days available for booking in a year |
| number_of_reviews | Total reviews |
| review_scores_rating | Average review score (1 to 5) |
| host_is_superhost | Whether the host is a Superhost |
| estimated_revenue_l365d | Estimated revenue in the last 365 days |

## Tools Used
Python, Pandas, NumPy, Matplotlib, Seaborn, Jupyter Notebook

## Data Cleaning
| Issue | Action |
|---|---|
| 13 columns completely empty | Dropped |
| Only 14 of the remaining columns needed | Kept the 14 relevant columns |
| `price` stored as text with `$` and `,` | Removed symbols and converted to float |
| `host_is_superhost` stored as `t` / `f` | Converted to True / False |
| Duplicates | None found |
| 480 listings with no price | Rows dropped |
| Missing bedrooms, beds, minimum nights | Filled with the median |
| Extreme prices (max $13,000) and a $0-10 listing | Removed prices above the 99th percentile ($1,245) and below $10, which dropped 27 rows |

## Charts

**1. Distribution of nightly price**

[ADD CHART IMAGE: images/price_distribution.png]

**2. Nightly price by room type**

[ADD CHART IMAGE: images/price_by_room_type.png]

**3. Median nightly price by region**

[ADD CHART IMAGE: images/price_by_region.png]

**4. Top 10 priciest neighbourhoods**

[ADD CHART IMAGE: images/top10_neighbourhoods.png]

**5. Correlation heatmap**

[ADD CHART IMAGE: images/correlation_heatmap.png]

**6. Guests accommodated vs price**

[ADD CHART IMAGE: images/accommodates_vs_price.png]

**7. Listings across Singapore coloured by price**

[ADD CHART IMAGE: images/price_map.png]

## Key Insights
1. **Singapore Airbnb is mostly a Central Region story.** 2,256 of 2,645 cleaned listings (about 85%) are in the Central Region, which also has the highest median price (about $213). The North Region is cheapest (about $73, only 34 listings).
2. **Room type is the biggest price divider.** Median price is about $300 for an entire home, $188 for a hotel room, $126 for a private room and $52 for a shared room. An entire home costs about 2.4 times a private room.
3. **Price is right-skewed.** The mean ($233) is above the median ($197), with skewness of 1.09, so the median is a fairer figure.
4. **Longer minimum stays mean cheaper nights.** `minimum_nights` has a correlation of -0.37 with price. The number of guests a listing sleeps has the strongest positive correlation (0.49).
5. **Orchard is the priciest area** at about $395 median, followed by Clementi and Jurong East (both about $300, but with only 25 to 50 listings, so treat with caution).
6. **Most listings are not earning.** About 69% have zero estimated revenue in the last 12 months. Among earning listings, private rooms had the highest median revenue (about $10,700), ahead of entire homes (about $8,300), even though they charge less per night.

## Conclusion
Nightly price is driven mainly by what is being rented and how many guests it sleeps, with location (Orchard and the Central Region) also important. For a new host, a well-located private room or small home in the Central Region looks like a sensible start, but competition from professional hosts is heavy.

## Repository Structure
```
airbnb-singapore-analysis/
├── data/airbnb_singapore.csv
├── notebook/Airbnb_Singapore.ipynb
├── images/
└── README.md
```

## Author
**Afnan M** | BCA (Data Science), Amrita School of Arts and Sciences, Kochi
[LinkedIn] | [GitHub] | [Email]