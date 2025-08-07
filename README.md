# Used Cars Analysis

## Table of Content
- Project Overview
- Problem Statement
- Dataset Overview
- Methodology
- Dashboards and Insights
- Key Findings
- Recommendations

### Project Overview

This project analyzes used car listings from Cars24, a major platform for buying and selling pre-owned vehicles in India. It looks into what customers prefer, what affects resale prices, and how cars lose value over time.

The goal is to give useful insights for buyers, sellers, dealerships, and marketers so they can make better decisions in the used car market.


### Problem Statement

The resale value of a used car depends on several factors — like mileage, age, condition, number of past owners, and the brand or model. For buyers, it can be hard to know if a car is priced fairly. For sellers and dealers, timing and stock choices matter a lot.

This project aims to answer key questions like:

- What factors have the biggest impact on resale price?
- How do age, mileage, and ownership affect a car’s depreciation?
- Which Maruti models and variants show up most often in listings?
- Do imperfections and repainted parts lower the car’s value?

### Dataset Overview

**Source:** The dataset was sourced from Kaggle, which hosts structured data scraped from the Cars24 platform.

**Key Columns:**

|Column|Description|
|------|-----------|
|Model Name|Complete car name including year and variant (e.g. "2015 Maruti Wagon R 1.0 Vxi")|
|Year|The year the car was manufactured|
|Price|The resale price (in Indian Rupees)|
|Km Driven|Total kilometers driven; an indicator of usage/mileage|
|Fuel Type|Type of fuel the car uses: Petrol, Diesel, or CNG|
|Transmission|Manual or Automatic transmission type|
|Ownership|Number of previous owners (e.g., First-owner, Second-owner)|
|Engine Capacity (cc)|Displacement of the engine in cubic centimeters|
|Spare Key|Indicates whether a spare key is available (Yes/No)|
|Imperfections|Number of visible imperfections observed during inspection|
|Repainted Parts|Number of car parts that have been repainted|


### Methodology

**Tools Used:**

**Microsoft Excel**: Used for the entire workflow, including data cleaning, transformation, analysis, and dashboard creation.

- **Power Query**: Used to prepare and clean the dataset.
- **Power Pivot**: Used to create calculated columns.


**Data Cleaning (Power Query):**

- Converted all columns to their appropriate data types (text, number, date).
- Removed trailing spaces and non-printable characters.
- Applied consistent capitalization to enhance readability.
- Renamed columns for clarity:
  - "Model Name" to "Full Model Name"
  - "Km Driven" to "Kilometers Driven"
  - "Ownership" to "Previous Owners"
  - "Engine Capacity" to "Engine Capacity (cc)"
  - "Spare Key" to "Spare Key Availability"
  - "Imperfections" to "Imperfection Count"
  - "Repainted Parts" to "Repainted Parts Count"

- Extracted brand, car model, and variant from "Full Model Name" and Created three new columns:
  - Brand: Maruti
  - Car Model: e.g., Swift, Baleno
  - Car Variant: e.g., ZXi, VXi, Delta

- Removed duplicates to ensure data integrity.

**Data Modeling (Power Pivot):**

New calculated columns were created:

 - Car Age (Years): Current year − Manufacturing year
 - Model Age Group:
   - New Model: 5 years old or less
   - Old Model: More than 5 years old
- Engine Category:
  - Small Engine: < 1000 cc
  - Mid-range Engine: 1000–1500 cc
- Kilometer Driven Range: Buckets such as 0–25K, 25K–50K, 50K–75K, etc.


### Dashboards and Insights 

**Customer Preference & Car Profile Analysis**

<img width="1791" height="886" alt="Screenshot 2025-08-06 130114" src="https://github.com/user-attachments/assets/e1fe2189-6769-4134-a1f3-370bacf023d4" />

**Objective:** Identify customer preferences and popular car profiles with a focus on Maruti brand listings.

**Insights:**
-  **Top 10 Most Listed Maruti Models**:
This chart highlights the most frequently listed Maruti models. Baleno leads with 236 listings, followed by Alto (161), Swift (151), Wagon R (141), and Celerio (141). Altogether, these five models make up 830 out of 1,445 total Maruti listings, which is approximately 57.5% of all Maruti cars listed.
This suggests that more than half of the Maruti cars being resold on the platform come from just these five models — a strong indicator of customer preference and trust in these models.

-  **Top 10 Most Listed Maruti Cars**:
This chart goes a level deeper by showing which specific model-year-variant combinations are most listed. The 2015 Wagon R 1.0 VXi came out on top, with 16 listings — making it the most frequently resold individual Maruti variant in the data.

    Taken together, these charts paint a clear picture of which Maruti cars are not only popular at the time of purchase but are also actively traded in the used car market — offering solid insight into long-term value and buyer behavior.

-  **Fuel Type Distribution**:
This chart gives a quick look at what fuel types people prefer. Petrol cars make up the majority, accounting for 87% of the listings. CNG comes next with 8%, and Diesel trails behind at just 5%. It’s clear that petrol vehicles are the most in demand, while CNG and diesel cars are far less common on the platform..

-  **Transmission Type Distribution**:
This chart shows how cars are split between manual and automatic transmissions. Manual cars make up the bulk of the listings with 1,073 entries, while automatic cars account for 372. It’s a useful snapshot of current buyer behavior, showing that manual is still the more common choice, though there’s a growing presence of automatic options too.


**Resale Value & Depreciation Analysis**

<img width="1788" height="887" alt="Screenshot 2025-08-06 131111" src="https://github.com/user-attachments/assets/9e164c17-4b8a-4322-9354-1892efca16a4" />

**Objective:** Understand how vehicle characteristics affect resale value and depreciation trends.

**Insights:**

-  **Car Age vs. Average Price**:
The scatter plot clearly shows that as cars get older, their value drops. There’s a strong negative correlation of **-99%** between car age and average price, meaning older cars are consistently worth less. This trend highlights the natural depreciation that comes with age — the longer you keep a car, the less you’re likely to get back when selling it.


-  **Kilometer Driven Range vs. Average Price**:
This chart looks at how the distance a car has been driven affects its value. The mileage was grouped into buckets: 0–25k km, 25k–50k km, 50k–75k km, 75k–100k km, and 100k+ km. Cars in the 0–25k km range had the highest average price at ₹632,400, followed by ₹540,600 for 25k–50k km. The price continues to drop as mileage increases, with cars over 100,000 km averaging ₹436,400. This clearly shows that as cars are driven more, their value depreciates — higher mileage is closely tied to lower resale prices.


-  **Mileage vs. Imperfections & Repainted Parts**:
This chart highlights how wear and tear builds up as a car is used more. Cars with higher mileage tend to have more imperfections and repainted parts. It shows that the more a car is driven, the more likely it is to need cosmetic or body repairs — and that kind of visible damage can lower how much buyers are willing to pay. It’s another sign of how both usage and condition contribute to a car’s depreciation.

-  **Average Price by Number of Owners**:
This chart shows how the number of previous owners impacts car value. First-owner cars have the highest average price at ₹547,900. That drops to ₹474,300 for second-owner cars and falls even further to ₹369,500 for third-owner cars. The pattern is clear — the more owners a car has had, the less it’s worth. It also reflects depreciation tied to ownership history, as buyers tend to value cars with a simpler, more trustworthy background.

-  **Average Price by Spare Key Availability**:
This chart shows a small but noticeable difference in value when a car comes with a spare key. Cars listed with a spare key had slightly higher average prices compared to those without one. It may seem minor, but it suggests better overall care and completeness — things that buyers tend to appreciate when making a purchase decision.

-  **Average Price by Engine Category**:
This chart compares car prices based on engine size. Cars with mid-range engines (1000–1500 cc) had an average resale price of ₹615,300, while small-engine cars (under 1000 cc) averaged ₹388,200. Mid-range engines are often valued higher because of better performance, while small engines tend to attract fuel-conscious buyers. The difference in average price shows that engine size is definitely a factor that influences resale value.

-  **Average Price by Fuel Type**:
This chart shows how fuel type affects resale prices. Diesel cars had the highest average price at ₹589,100, followed by petrol at ₹527,100, and CNG at ₹475,800. The price difference across fuel types suggests that fuel type does influence resale value — with diesel generally commanding higher prices, likely due to better fuel efficiency and engine longevity. Petrol and CNG cars, while cheaper, may appeal more to budget-focused or city drivers.


### Key Findings

-**Depreciation is clear**: Car value steadily drops as the vehicle gets older. Age is one of the strongest factors affecting resale price.
- **Top Maruti Models**: Swift, Baleno, and Wagon R appear most often in listings. This shows that these models are not only popular among buyers but are also commonly resold — reflecting strong customer preference. 
- **Single Ownership Holds Value**: Cars with only one previous owner tend to sell for higher prices compared to those with multiple past owners.
- **Condition Affects Pricing**: Cars with more imperfections or repainted parts usually have lower resale prices, showing that visible wear and cosmetic issues matter.
- **Spare Key Makes a Difference**: While it may seem small, having a spare key is linked to slightly higher resale value, possibly because it signals better overall care.

### Recommendations

**For Buyers:**
- Go for older cars if you're on a budget.
- Check the car’s condition carefully.
- Choose single-owner cars with extras like spare keys.

**For Sellers:**
- Sell before the car hits 6 years to get better value.
- Fix scratches, dents, and paint issues to improve resale price.

**For Dealerships:**
- Focus on fast-moving models like Swift, Baleno, and Wagon R.
- Choose low-mileage, single-owner cars for better turnover.
- Sort inventory by:
  - **Fuel Type**: Diesel has the highest resale value, petrol comes next and is more common in cities, while CNG is the cheapest option
  - **Engine Category**: Performance-oriented buyers may prefer mid-range engines; fuel-efficient buyers lean toward small engines.

  This segmentation strategy enables better pricing, targeted promotions, and efficient inventory turnover based on customer demand and resale trends.
  



  


