# IDXExchange Project

## Objectives:
Upon downloading datasets on real estate properties sourced from CRMLS (California Regional Multiple Listing Service), the goal is to build and train a machine learning model to predict ClosePrice, the price of any single residential property in California.

## Weekly Milestones & Progress

### Week 1:
*Goals*
- Download atleast 6 months of raw CSV data from CRMLS
- Review MetaData to understand important data features and key columns

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
