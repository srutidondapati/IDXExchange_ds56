# IDXExchange Project

## Objectives:
Upon downloading datasets on real estate properties sourced from CRMLS (California Regional Multiple Listing Service), the goal is to build and train a machine learning model to predict ClosePrice, the price of any single residential property in California.

## Weekly Milestones & Progress

### Week 1:
*Goals*
- Download atleast 6 months of raw CSV data from CRMLS
- Review MetaData to understand important data features and key columns

---

### Week 2:
*Goals*
- Load 6 months of dataset into jupyter notebook using pandas
- Explore the distributions of key columns: ClosePrice, LivingArea, Bedrooms, Bathrooms, LotSize
- Restrict to PropertyType = Residential and PropertySubType = SingleFamilyResidence

*Results*
- Close Price: most houses are sold between $750k to $900k, with outliers existing above $3M
- Living Area: most houses have around 1,500 to 2,000 square footage of living area
- Bedrooms: most houses have 3-4 bedrooms
- Bathrooms: most houses have 2-3 bathrooms
- Lot Size: most houses have a lot size of around 10k to 15k square footage

---

### Week 3:
*Goals*
- Handle missing values (decide whether to drop, impute, or flag).
- Convert categorical fields to numeric (encoding).
- Normalize numerical features if needed.
- Create train/test split

*Results*
- #### Handling Missing Values:
    - ClosePrice: 0 nulls, no handling necessary
    - LivingArea: 35 nulls, dropped rows (since it is required for model)
    - BedroomsTotal: 0 nulls, no handling necessary
    - BathroomsTotalInteger: 2 nulls, filled with median (under 50% threshold)
    - LotSizeSquareFeet: 1,210 nulls, filled with median (under 50% threshold)

 - #### Outlier Removal:
     - Removed large/unrealistic values using the findings from Week 2 data exploration
       - ClosePrice: kept between $50K and $10M
       - LivingArea: kept between 300 and 15,000 sq ft
         
- #### Observed that PostalCode and City had strong influence on ClosePrice:
    - ZIP code median prices range from $75K to $9M
    - City median prices range from $75K to $6.9M
    - encoded as median price features computed on training data: zip_median_price, city_median_price

- #### Train/Test Split:
    - Training set contains data from September 2025 - March 2026
    - Test set contains data from April 2026
    - Final Features (X): LivingArea, BedroomsTotal, BathroomsTotalInteger, 
      LotSizeSquareFeet, zip_median_price, city_median_price
    - Target (y): ClosePrice

---

### Week 4:
*Goals*
- Train a Linear Regression as the first model. 
- Evaluate using R² on the test set. 
- Record baseline results. 

*Results*
- Linear Regression Results: 
    - Training R²: 0.7778
    - Test R²: 0.7611
 
- The model had an R² score of 0.7611 on the test set, indicating that it explains approximately 76% of the variation in home sale prices. Both R² results are similar to each other with a difference of 0.0167 representing that the model is generalizing well without overfitting.

 
