# Airbnb Pricing Analysis (Excel/R)
Data from [InsideAirbnb](https://insideairbnb.com/get-the-data/) under [Creative Commons Attribution 4.0 International License](https://creativecommons.org/licenses/by/4.0/).

Columns where data was not used were deleted (such as urls and descriptions) from the dataset.
***
## Purpose
What affects the pricing of Airbnb's in San Francisco and what trends do they follow?
***
# Excel

## Process
1. Performed simple data cleaning after removing unused columns by checking for duplicates and removing $ from price column by converting from currency into a number.
2. Created availability column to determine whether the Airbnb was full-time or part-time based on its yearly availability.
3. Using an IF function, sorted rows that were available for more than 300 days a year.
```excel
=IF(AR3>300,"Full-Time","Part-Time")
```
4. To find what affects pricing, utilized pivot tables to compare price alongside neighborhood, availability, and room type.
5. Created bar charts using the three pivot tables and compiled findings into a dashboard.

## Dashboard
![image](https://github.com/echu-vb/airbnb_pricing_analysis/blob/34eaa6f4f960d81ecb775cf9dbf01411b3dc7be5/airbnb_dashboard.png)
(Slicers were included to show the effects of availability and room type on average price per neighborhood and can be viewed alongside all data used in `airbnb_pricing_sf.xlsx`)

## Conclusion
Airbnb's in San Francisco that had a full-time availability had a greater average price than those that had a part-time availability. 

In addition, shared rooms were shown to have the highest average price out of every room type with private rooms having the lowest average price. 
***
# R
To view the R portion of code please refer to `airbnb_r.pdf`

By using linear regression models we can see how quantitative parameters affect prices. 

All parameters used (bathrooms, accommodates, bedrooms) showed a positive relationship with price. 

Holding bedrooms and # of people being accommodated constant we can say that when comparing the price of two Airbnb's a single unit increase in bathrooms would increase price by 10.245. 

The model has an R-squared of 0.358 which means that the parameters chosen don't explain a majority of the variation shown by price. 

With the analysis shown in the Excel portion, I believe that a majority of price is explained by what neighborhood the Airbnb is located in. 
