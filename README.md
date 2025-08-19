# Airbnb Bangkok Data Analysis

## Table of Contents
1. [Background in Information](#1-background-in-information)
2. [Problem Statement and Business Questions](#2-problem-statement-and-business-questions)
3. [Features](#3-features)
4. [Data Cleaning](#4-data-cleaning)
5. [Recommendations](#5-recommendations)
   - [SWOT Analysis — Determining the Room Types](#swot-analysis--determining-the-room-types)
   - [Room Type Specific Recommendation](#room-type-specific-recommendation)
6. [Tableau Link](#6-tableau-link)
---

# 1. Background in Information

The short-term rental market in Thailand—especially in tourism hubs like Bangkok—is experiencing rapid growth. Platforms such as Airbnb have opened opportunities for property owners and managers to reach a global audience.

However, many stakeholders still rely on intuition or inconsistent strategies for pricing, marketing, and managing availability. Without leveraging data, they risk missing opportunities to:

- Align with guest preferences.
- Identify high demand locations and listing types.
- Identify pricing based on property and locations

---

# 2. Problem Statement and Business Questions

## Problem Statement

The short-term rental market in Thailand—especially in tourism hubs like Bangkok—is experiencing rapid growth. Platforms such as Airbnb have opened opportunities for property owners and managers to reach a global audience.

However, many stakeholders still rely on intuition or inconsistent strategies for pricing, marketing, and managing availability. Without leveraging data, they risk missing opportunities to:

- Align with guest preferences.

- Identify high demand locations and listing types.

- Identify pricing based on property and locations

**Main question:**

**How should renters and property managers position their listings?**


This analysis uses Bangkok Airbnb data to address the following key business questions:


Market Distribution
---
1. Neighborhood Supply Patterns

  - Which neighborhoods have the highest concentration of listings, and how is supply distributed across Bangkok?

2. Room Type & Location Trends

  - How does room type availability vary by neighborhood, and are certain types more concentrated in specific areas?

3. Stay Duration Preferences

  - What are the common minimum night stay requirements, and which areas cater more to short-term vs long-term guests?

  - Host & Market Structure

  - How many properties do hosts typically manage, and where are high-volume hosts most active?

Competition
---
4. Large Operator Concentration

  - Where are large-scale operators (50+ properties) located, and are they clustered in high-demand or high-value neighborhoods?

5. Medium Operator Distribution

  - How widespread are medium operators (11–50 properties), and in which neighborhoods are they most active?

6. Competitive Landscape

  - How does the presence of large vs. medium operators vary across Bangkok’s neighborhoods?

Price
---

7. Price Distribution Across Neighborhoods

  - Which neighborhoods command the highest median prices?

  - Which neighborhoods have the lowest median prices?

  - How wide is the overall price range across Bangkok neighborhoods?

8. Price by Room Type

  - How do median prices vary between different room types?

  - Which room types are typically the most expensive, and which are the cheapest?

  - Are there statistically significant differences in prices between room types?

9. Neighborhood & Room Type Interaction

  - How do prices for each room type vary by neighborhood?

  - Which neighborhoods have unusually high or low prices for specific room types?

  - Are there extreme price outliers that may skew perceptions or indicate niche luxury/low-cost markets?

10. Strategic Pricing Opportunities

  - In which neighborhoods can certain room types command premium prices?

Demand
---
11. Demand Distribution

  - How is demand (total bookings and bookings in the last 12 months) distributed across different room types?

  - Which neighborhoods consistently attract the highest booking volumes?

12. High-Demand Pricing Dynamics

  - In high-demand areas, which room types are able to sustain premium pricing while maintaining strong booking levels?

  - Are there specific neighborhoods where guests show a strong willingness to pay above market averages for certain room types?

13. Room Type–Location Performance

  - Which neighborhoods deliver the best combination of high demand and high pricing for each room type?

  - How wide is the price spread within each room type, and how much is it influenced by neighborhood characteristics?

14. Strategic Demand Drivers

  - Beyond price, what other factors (location, amenities, property type, seasonality) are likely influencing booking patterns in high-demand segments?

15. Demand Concentration

  - What proportion of total listings achieve high demand, and how does this vary by room type?

16. Room Type Performance Gap

  - Which room types are most overrepresented in the high-demand segment, and which are underrepresented?

  - How can property managers adjust inventory to align with market preferences?

17. Geographic Demand Distribution

  - Which neighborhoods have high-demand listings, and which areas currently lack them?

  - Do these gaps represent untapped opportunities or reflect low inherent demand?

18. Market Structure

  - How do statistical tests (Chi-square) confirm that observed differences in room type distribution are structural and not random?

High Demand vs All Listings
---

19. Market Share

  - What proportion of listings achieve high demand (>=50 bookings), and how is this distributed across Bangkok?

20. Room Type Preferences

  - Which room types dominate in high-demand segments, and how does this compare to the overall market distribution?

21. Geographic Coverage

  - Which neighborhoods have high-demand listings, and which areas have none?

22. Structural Differences

  - Do room type distributions in high-demand listings differ significantly from the overall market, and what does this reveal about guest preferences?

---

# 3. Features

## Feature Information

### access pdf here: https://issuu.com/urielss/docs/airbnb_listings_bangkok_data_dictionary

| **No** | **Column Name**                      | **Description**                                                                                                                                                                                                                                                                       |
|--------|---------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1      | **id**                                | Airbnb's unique identifier for the listing.                                                                                                                                                                                                                                          |
| 2      | **name**                              | Name of the listing.                                                                                                                                                                                                                                                                 |
| 3      | **host_name**                         | Name of the host (usually just the first name).                                                                                                                                                                                                                                      |
| 4      | **neighbourhood**                     | Neighborhood geocoded using the latitude and longitude against neighborhoods defined by public digital shapefiles.                                                                                                                            |
| 5      | **latitude**                          | Latitude using the World Geodetic System (WGS84) projection.                                                                                                                                                                                                                         |
| 6      | **longitude**                         | Longitude using the World Geodetic System (WGS84) projection.                                                                                                                                                                                                                        |
| 7      | **room_type**                         | Type of room offered: <br> - Entire home/apt <br> - Private room <br> - Shared room <br> - Hotel                                                                                                                                                                                      |
| 8      | **price**                             | Daily price in local currency (may include a "$" sign regardless of locale).                                                                                                                                                                                                         |
| 9      | **minimum_nights**                    | Minimum number of nights required for a booking (calendar rules may differ).                                                                                                                                                                                                         |
| 10     | **number_of_reviews**                 | Total number of reviews the listing has received.                                                                                                                                                                                                                                    |
| 11     | **last_review**                       | Date of the most recent review.                                                                                                                                                                                                                                                      |
| 12     | **calculated_host_listings_count**    | Number of listings the host has in the current scrape for the city/region.                                                                                                                                                                                                           |
| 13     | **availability_365**                  | Number of days in the next 365 days the listing is available (may be blocked or booked).                                                                                                                                                                                             |
| 14     | **number_of_reviews_ltm**             | Number of reviews in the last 12 months.                                                                                                                                                                                                                                             |
| 15     | **operators** *(feature engineered)*  | Categorization based on `calculated_host_listings_count`: <br> - Owner: ≤ 2 properties managed <br> - Small operator: 3–10 properties managed <br> - Medium operator: 11–50 properties managed <br> - Large operator: > 50 properties managed                                                                        |
| 16     | **stay** *(feature engineered)*       | Categorization based on `minimum_nights`: <br> - Short: 1–7 nights <br> - Medium: 8–30 nights <br> - Long: 31–180 nights <br> - Permanent: > 180 nights                                                                                                                               |

---

# 4. Data Cleaning

steps of cleaning: 


**Change or remove columns**
1. The 'Unnamed: 0' column seems to be unnecessary to the broader df
2. The 'id' and 'host_id' column should be changed to string to better analyze listings performance based on 'host_id' using descriptive statistics
3. The 'reviews_per_month' column should be changed from float to integer for better viewing
4. The 'last_review' column should be changed to datetime in order for time series analysis to be utilized

**Removing irregular datas**
5. Remove datas inside the 'minimum_nights' column based on Airbnb regulations (maximum 720 minimum_nights per listing/booking)
6. Remove prices that are below 1 baht since Airbnb doesn't allow for prices to be free in their listing

**Data distribution in columns containing numerical data**
7. Although **'price', 'minimum_nights', 'number_of_reviews', 'number_of_reviews_ltm' , and 'calculated_host_listings_count'** contain extreme outliers, these columns reflects the 'natural' distribtuion of the business world.
  - Some properties are more expensive than others depending on luxury
  - Some properties have more demand than others
  - Some hosts manage way more listings depending on their asset
8. All statisitcal analysis using numerical columns will be done using median due to the skewed distribution of the data

documentation of cleaning:


1. No duplicates were found in the column 'id' (unique value)
2. 5.790 rows of data from 'number_of_reviews' were filled with '0' for the purpose of statistical analysis in data analysis
3. Amount of 'host_id' and 'calculated_host_lisitngs_count corresponds with each other
4. 7 rows of data from 'minimum_nights' were removed due to Airbnb not allowing listings to have a minimum night of more than 730 days per listing.

---

# 5. Recommendations

## SWOT Analysis — Determining the Room Types

### Strengths
- **Entire home/apt**:  
  - Dominates high-demand market share (77.26%).  
  - Strong appeal from privacy, space, and upscale image supported by location proximity to transport (BTS, MRT, Sukhumvit, Asok) and premium amenities (WiFi, Netflix, Pool, Gym).  
  - Works well in premium, high-connectivity neighbourhoods (Khlong Toei, Vadhana, Bang Rak).  

- **Private room**:  
  - Targets budget-conscious guests while still offering privacy.  
  - Strong demand drivers include transport accessibility (BTS, MRT, Subway), city branding (Bangkok, Siam, Old Town), and added conveniences like WiFi and breakfast.  
  - Performs well in transport-linked mid-cost areas (Ratchathewi, Huai Khwang, Sathon).  

- **Hotel room**:  
  - Stable demand share with clear amenity advantages (Pool, Parkview, Garden) and ability to brand experiences uniquely (“Mustang”, “Nero”).  
  - Concentrated in tourist-heavy zones with BTS/MRT access (Bang Rak, Phra Nakhon, Pathum Wan).  

- **Shared room**:  
  - Appeals to niche budget traveler and backpacker segment.  
  - Strong association with social atmosphere and dorm-type setup in nightlife/backpacker areas (Khaosan, Ari, Sathorn).  

---

### Weaknesses
- **Entire home/apt**:  
  - Higher operational costs and competition from established premium listings.  
  - Requires significant capital for furnishing and amenities to meet guest expectations. 

- **Private room**:  
  - Smaller market share (17.70% in high-demand listings).  
  - Competes heavily with budget hotels and entire home/apartment rentals at slightly higher prices.  

- **Hotel room**:  
  - Small share of high-demand listings (4.07%), making scaling harder.  
  - High overhead costs compared to other room types.  

- **Shared room**:  
  - Minimal high-demand presence (0.97%).  
  - Limited appeal beyond budget travelers.  

---

### Opportunities
- **Entire home/apt**:  
  - Further capitalize on premium positioning by focusing on neighbourhoods with strong BTS/MRT connections and high tourist activity (Khlong Toei, Vadhana, Bang Rak).  
  - Expand amenity offerings (smart TVs, workspace setups, luxury bedding) to justify premium pricing.  

- **Private room**:  
  - Leverage proximity marketing (“1 min to BTS”) and distinctive style (Vintage, Chic) to differentiate from standard budget stays.    

- **Hotel room**:  
  - Position properties as lifestyle destinations with unique branding/themes to stand out from generic hotels.  
  - Focus expansion in high-tourist traffic neighbourhoods underserved by large operators (Phra Nakhon, Pathum Wan).  

- **Shared room**:  
  - Expand in backpacker/nightlife districts (Khaosan, Ari, Sathorn) with added-value experiences (city tours, pub crawls).  
  - Use short-stay positioning to target transit travelers.  

---

### Threats
- **Entire home/apt**:  
  - Price competition from other premium listings and hotels.  
  - Dependence on tourist flows; economic downturns and low seasons can quickly impact demand (usually reserved for family or 4 or more tourists per listings).  

- **Private room**:  
  - Vulnerable to undercutting from hostels and budget hotels.  
  - Lower booking volumes compared to entire homes may limit profitability.  

- **Hotel room**:  
  - Competes with well-established hospitality brands and chain hotels with larger marketing budgets.  

- **Shared room**:  
  - Susceptible to market fluctuations affecting backpacker and budget tourism.  
  - Strong competition from established hostels in prime tourist areas.

---

## Room Type Specific Recommendation

### 1. Entire home/apt

- **Why**  
  High-demand entire home/apartment listings dominate the market share (77.26% of high-demand listings). Wordcloud analysis shows guests are strongly attracted to properties near public transport (BTS, MRT, Sukhumvit, Asok) and city hubs, as well as listings that highlight premium amenities (WiFi, Netflix, Pool, Gym) and upscale property types (Condo, Penthouse, Modern, Loft). This indicates a preference for privacy, convenience, and style in urban environments.

- **Action**  
  - In listing titles and descriptions, prominently highlight proximity to BTS/MRT and major hubs.  
  - Include and advertise premium amenities like high-speed WiFi, streaming services, and access to pools/gyms.  
  - Use upscale descriptors (“Luxury”, “Modern”, “Deluxe”) and property type mentions (Condo, Loft) to target higher-spending travelers.  
  - Showcase both functional size (2BR, 3BR, Spacious) and atmosphere (Cozy, Quiet) to appeal to families and couples alike.  

- **Neighbourhood to Focus**  
  Focus on neighbourhoods already strong in high-demand listings and well-connected to BTS/MRT, such as Khlong Toei, Vadhana, and Sathon — areas with proven demand and premium positioning potential.

- **Price**  
  Maintain premium pricing relative to market averages, supported by superior location and amenities, but monitor competition in key BTS/MRT-linked neighbourhoods to avoid overpricing. 
  - Lower bound price: ~฿1,029
  - Upper bound price: ~฿2,571

---
### 2. Private room

- **Why**  
  While private rooms represent only 17.70% of high-demand listings, demand drivers are clear: proximity to transport (BTS, MRT, Subway, “walk to”), city branding (Bangkok, Siam, Old Town), privacy, and budget-friendly comfort. Wordclouds show that basic amenities (WiFi, Free WiFi, Netflix, Breakfast) and stylistic features (Cozy, Chic, Antique) improve appeal.

- **Action**  
  - Lead titles with location proximity claims (“1 min to BTS”, “Near MRT Siam”) to strengthen search relevance.  
  - Highlight privacy features in descriptions (Private Room, Balcony, Loft, House).  
  - Offer added-value basics like breakfast or free WiFi, even if simple, to stand out in the budget-conscious segment.  
  - Use style descriptors (“Vintage”, “Chic”) to target niche traveler preferences (e.g., solo explorers, couples).  

- **Neighbourhood to Focus**  
  Focus on neighbourhoods with solid transport links but potentially lower property costs, such as Ratchathewi, Huai Khwang, and Phra Nakhon, where medium operators are active and competitive pricing can capture demand.

- **Price**  
  Keep rates competitive within the budget to mid-tier range, with small premiums justified for strong location or distinctive style.
  - Lower bound price: ~฿800
  - Upper bound price: ~฿2,090

---
### 3. Hotel room

- **Why**  
  Hotel rooms have stable but small market share (4.07% in high-demand listings). Wordcloud results show transport proximity (BTS, MRT) remains important, but amenities and brand-like differentiation (“Mustang”, “Nero”) can significantly improve appeal. Guests value leisure facilities (Pool, Parkview, Garden) and clear room/bed specifications.

- **Action**  
  - Emphasize transport proximity in listing titles and hotel descriptions.  
  - Include leisure-focused imagery showcasing pools, gardens, and rooftop spaces.  
  - Brand rooms or packages with unique names/themes to stand out from generic hotel listings.  
  - Clearly state bed types (Double, Twin) and room size to meet guest expectations.  

- **Neighbourhood to Focus**  
  Prioritize tourist-heavy and high demand areas with strong BTS/MRT links such as Ratchatewi, Khlong Toei, and Vadhana.

- **Price**  
  Position pricing mid-to-premium depending on amenity set; use seasonal promotions to capture shoulder-season (season between high and low seasons) demand.
  - Lower bound price: ~฿996
  - Upper bound price: ~฿3,171

---
### 4. Shared room

- **Why**  
  Shared rooms are the smallest segment (0.97% of high-demand listings) but cater to budget-conscious and social travelers. Wordcloud results highlight dorm and bed type prominence (Dorm, Mixed, Bunk, Capsule), transport access (BTS, “near”), and experience-based terms (Hostel, Homestay, Cozy). Locations like Khaosan and Ari indicate nightlife and backpacker appeal.

- **Action**  
  - Clearly specify dorm setup, bed type, and shared facilities in titles (“Mixed Dorm 8 Bed near BTS Ari”).  
  - Focus marketing on social and community aspects (shared lounges, events).  
  - Highlight affordability and short-stay suitability for transit travelers.  
  - Promote proximity to nightlife or backpacker districts in descriptions.  

- **Neighbourhood to Focus**  
  Focus on high demand areas like Phra Nakhon, Ratchatewi, and Vadhana.

- **Price**  
  Maintain highly competitive, low rates to capture budget travelers, with optional upsells for lockers, breakfast, or tours.
  - Lower bound price: ~฿390
  - Upper bound price: ~฿650

# 6. Tableau Link
Access tableau dashboard here: https://public.tableau.com/app/profile/uriel.siboro/viz/Airbnb_17551116230080/Dashboard1?publish=yes
