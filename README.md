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

This project delivers an extensive data analysis of used car listings sourced from **Cars24**, one of India’s most popular online platforms for buying and selling pre-owned vehicles. The analysis focuses on understanding customer preferences, evaluating the factors that influence resale prices, and examining how various attributes contribute to vehicle depreciation over time.

Through exploratory analysis and visualization, this project offers actionable insights tailored to help key stakeholders such as **car buyers**, **sellers**, **dealership**s, and **marketers** make informed decisions within the dynamic landscape of the used car market.


### Problem Statement

The value of a used car is influenced by a combination of factors including mileage, car age, condition, number of previous owners, and brand/model popularity. For buyers, determining fair value and ensuring quality can be difficult. For sellers and dealers, identifying the right time to sell and choosing which cars to stock is essential.

This project addresses the following key questions:

- What are the most influential factors affecting the resale price of used cars?
- How do car age, mileage, and ownership history impact depreciation?
- Which Maruti models and variants are most frequently listed and resold?
- How do imperfections and repainted parts affect perceived value and pricing?


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
  - "Model Name" → "Full Model Name"
  - "Km Driven" → "Kilometers Driven"
  - "Ownership" → "Previous Owners"
  - "Engine Capacity" → "Engine Capacity (cc)"
  - "Spare Key" → "Spare Key Availability"
  - "Imperfections" → "Imperfection Count"
  - "Repainted Parts" → "Repainted Parts Count"

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


## Dashboards
**Dashboard 1: Customer Preference & Car Profile Analysis**
**Dashboard 2: Resale Value & Depreciation Analysis**


**Customer Preference & Car Profile Analysis**

**Objective:** Identify customer preferences and popular car profiles with a focus on Maruti brand listings.

**Insights:**
-  **Top 10 Most Listed Maruti Models**:
Displays the most frequently listed Maruti models (e.g., Swift, Wagon, Baleno). revealing overall brand-level popularity and customers trust in these models.

-  **Top 10 Most Listed Maruti Cars**:
Provides more granular detail including production year and variant (e.g., 2015 Wagon R 1.0 VXi).
Indicates which trims and years are most resold.
Together they reveal what type of Maruti cars customer buy and later resale the most, offering strong insights into preference and resale trends .

-  **Fuel Type Distribution**:
Highlights customer preference among Petrol, Diesel, and CNG.
Offers a view into market demand by fuel type.

-  **Transmission Type Distribution**:
Shows distribution between Manual and Automatic cars.
Useful for identifying shifts in buyer preferences.


**Resale Value & Depreciation Analysis**

**Objective:** Understand how vehicle characteristics affect resale value and depreciation trends.

**Insights:**

-  **Car Age vs. Average Price**:
Visualizes depreciation curve.
Confirms that car value drops significantly as age increases.

-  **Kilometer Driven Range vs. Average Price**:
Reveals that higher mileage often correlates with lower resale prices.

-  **Mileage vs. Imperfections & Repainted Parts**:
Shows how wear and tear increases with use.
Indicates that cosmetic and physical damage reduces perceived value.

-  **Average Price by Number of Owners**:
Demonstrates that single-owner cars fetch higher prices than those with multiple owners.

-  **Average Price by Spare Key Availability**:
Minor but noteworthy value gain when a spare key is available, indicating better upkeep.

-  **Average Price by Engine Category**:
Mid-range engines often valued higher for performance.
Small engines appeal to fuel-conscious buyers.

-  **Average Price by Fuel Type**:
Diesel vehicles often command higher resale prices, while CNG and Petrol follow.


### Key Findings

- **Depreciation is inevitable**: Car value consistently decreases with age, especially beyond 5–6 years.
- **Popular Maruti Models**: Swift, Baleno, and Wagon R dominate listings.
- **Single Ownership Advantage**: Vehicles with fewer previous owners retain more value.
- **Vehicle Condition Matters**: More imperfections and repainting correlate with lower resale prices.
- **Spare Key Availability**: Although minor, contributes positively to perceived vehicle value.


### Recommendations

**For Buyers:**
- Opt for older cars if you're looking for affordability.
- Inspect the car's physical condition thoroughly.
- Prefer single-owner cars with complete accessories (e.g., spare keys).

**For Sellers:**
- Resell before 5–6 years of usage to minimize depreciation losses.
- Fix visible imperfections and repainting to increase appeal and market value.

**For Dealerships:**
- Stock high-demand models and variants, especially for the Maruti brand.
- Prioritize low-mileage, single-owner cars to ensure faster resale and higher profit margins.
- Segment inventory by:
  - **Fuel Type**: Different buyer segments favor different fuels (Diesel may fetch higher prices, CNG may be more economical).
  - **Engine Category**: Performance-oriented buyers may prefer mid-range engines; fuel-efficient buyers lean toward small engines.
  This segmentation strategy enables better pricing, targeted promotions, and efficient inventory turnover based on customer demand and resale trends.
  



  


