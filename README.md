# Jumia Product Performance Dashboard
## Project Overview
This is a Jumia Product Performance Project that was done using Excel as a tool for analysis. The analysis was done to understand how price, promotions, and customer feedback influence product performance. The focus was on the products, their pricing, their discount percentages derived from the product prices, and the customers rates and Reviews. The Project involved pulling the data from another github, cleaning the data, enriching the data by adding additional columns such as discount category, review category, rate category and others. Descriptive analysis was then carried out, Ranking tables were generated, pivot tables, pivot charts, slicers and an interactive dashboard was made to fully analyze the data.

## Project Objectives
The main reason that the project was carried out was to explain:
-	whether larger discounts are associated with more reviews
-	whether highly rated products attract stronger engagement
-	whether price and rating move together
-	which products perform best based on ratings and reviews
-	which products may need a different pricing or marketing strategy.
## Business Questions
The analysis was designed to help Jumia, and its sellers understand how price, promotions, and customer feedback influence product performance by answering:
1. Are larger discounts associated with higher customer engagement?
2. Do highly rated products receive more customer reviews?
3. Is there a relationship between product price and customer rating?
4. Which products have the highest ratings?
5. Which products have the highest number of reviews?
6. Which products have the largest discounts?
7. Which products combine high discounts with low ratings?
8. Which products combine high discounts with low engagement?
9. Which products have many reviews but only average ratings?
10. What pricing or marketing actions could be considered based on the findings?

## Dataset
The dataset contained product-level information from Jumia about product names, current prices, previous prices, advertised discounts, customer reviews, and customer ratings.
The main variables included: 

1. Product-This column contained Product names.
2. Current Price-it contained current selling price of the products in Kenyan shillings.
3. Discount-Contained the discount percentages of the products.
4. Review-Had number of  customer reviews recorded.
5. Rating-contained the ratings given by customers out of the possible five.

The customer review count was used as an engagement proxy and not a measure of sales because the data did not contain units sold or revenue.

## Tools and Technologies
The tools used were Excel, Gitbash and GitHub
Technologies-There was also the use of excel tables and formulas, Pivot tables and charts, slicers, conditional formatting, scatter plots, correlation analysis.
## Data Cleaning and Preparation
The raw data was pulled from a GitHub repository and the excel worksheet stored as an Excel Jumia dataset worksheet before any cleaning or transformation was done.

The original data contained:
1. Two duplicates 
2. Products that were written in mixed formats, some had Proper format and others were fully in caps.
3. Several missing values in the rate and review columns.
4. There were cells containing ranges in the current and old price column. 
5. The column Rating was named Ratingd
6. The values in Review had a negative preceding all of them.
7. The Rating column had a mixture of text and numeric values; the text was written as (out of 5).
8. The data in the columns were in the wrong data types.

So, to correct the data errors the following were done:
1. By using conditional formatting, the duplicated files were highlighted with red and the criteria used were products with the same name. Then they were filtered out, compared across their other column entries and the ones similar across columns were deleted.
2. Missing values in numeric columns were left as blanks and in text they were tagged as missing or missing entry.
3. Product names were turned into proper format using the =PROPER () function.
4. The cells containing range as a value were changed to a midpoint by averaging.
5. The column ratingd was rewritten as Rating.
6. The review column with the negative entries was highlighted and by use of CTRL + H we replaced the negative sign with a blank making the values appear without a negation.
7. The Rating column with the text “out of 5” was corrected by Ctrl+H where we removed the “out of 5” part.

The data type was converted by highlighting the columns with the wrong type and in home, selected the number section and changed the data types.

## Added Features.
There was need to add fields to support the analysis. These fields generated and stored in columns were:
1. Price check- we used it to check if the prices were valid by subtracting the old price to the new price and returning Ok if it was fine or otherwise flagging it to be checked.
2. Price category-with the use of the 1st and 3rd quartile we placed the Current prices in a properly defined threshold. Where Price Q_3 was 1669.5 and Price Q_1 was 493.
3. Discount amount- we calculated the precise discount amount for each product.
4. Discount check-we checked if the discount was between 0-1 and asked for a return of “OK” when it met the condition, otherwise it would return a “check the discount” message.
5. Discount category- created threshold for discount where <20% represented low discount, >20% but <=40% represented medium discount, and >40% represented High discount.
6. Review engagement flag-Created a well-defined threshold of 75% percentile-(Q_3) which acted as a wall between strong engagement and weak engagement.
7. Rate flag- Checked if the rate column was well defined and returned OK if it was,otherwise returning ” Check the rating.”
8. Rating category- Defined<3 as poor rating, <=4.5 as average, and >4.5 as Excellent otherwise returned missing or doesn’t meet these criteria.
9. High discount and low rating flag- recorded the cells with High discount and low rating flag, otherwise returned “doesn’t meet criteria” or “Missing entry.”
10. High discount and low review engagement- recorded the cells with High discount and low review engagement, otherwise returned “doesn’t meet criteria” or “Missing entry.”
11. Many reviews and average rating- recorded the cells with Many reviews and average rating flag, otherwise returned “doesn’t meet criteria” or “Missing entry.”
12. Strong review engagement and excellent rating- recorded the cells with Strong review engagement and excellent rating, otherwise returned “doesn’t meet criteria” or “Missing entry.”

## Analysis
To analyze the data, we did Descriptive analysis,  then did relationship analysis with use of scatter plots, correlations and product ranking analysis where we used the Top/bottom products and performance flags.
### 1. Descriptive Analysis
The following metrics were calculated with the use of Excel formulas:
-  Total number of products
-  Average current price
-  Average old price
-  Average discount
-  Average rating
-  Total reviews
-  Highest current price
-  Lowest current price
### 2. Relationship analysis
Three relationships were investigated using scatter plots and Pearson correlation coefficients:
1. Discount versus review 
2. Rating versus review 
3. Current price versus rating 
Linear trendlines and R-squared values were also included in the scatter plots to help assess the strength and direction of the observed relationships. 
Correlation results were interpreted as associations and not as evidence of causation.
### 3. Product Ranking Analysis
The analysis identified:
 -  Top 5 products by rating- here 7 products had equal ratings, review count was used as a tiebreaker, and it enabled us to obtain 4 topmost products by rating but still we had one spot and 3 products with the same rate. So, we introduced current price as a tie breaker, and we got the top 5 products by rating.
 -   Bottom 5 products by rating
 -   Top 10 products by discount
 -   Top 10 products by review count
 -   Top 10 products by rating
 -   Products with high discounts and low ratings
 -   Products with high discounts and low engagement
 -   Products with many reviews and average ratings

### Dashboard
The dashboard created provides an interactive summary of the Jumia product 
analysis.
The dashboard displays 5 KPI’s:
-  Total Products
-  Average Current Price
-  Average Discount
-  Average Rating
-  Total Reviews
There is also Visualizations of various aspects of our data which include:
-  Top products by rating in a horizontal bar chart
-  Top products by reviews in a horizontal bar chart
-  Top products with discount on a horizontal bar chart
-  Discount versus reviews in a column chart- Rating versus reviews in a pie chart
-  Price versus rating in a column chart
-  Rating distribution in a column chart
-  Discount distribution in a column chart
To make our dashboard interactive we included three slicers:
-  Rating Category slicer
-  Discount Category slicer
-  Price Category slicer
These slicers allow filtering the dashboard and exploring different products 
segments interactively.
In addition, we placed a refreshing date that shows when the dashboard was last updated.

## Key Findings
## 1.Relationships

## Discount and Reviews
A scatter plot was created using Discount % entries and Reviews entries. A trendline was incorporated and the R^2 value calculated as well as the equation of the line.

The values obtained were: 
A correlation of 0.044005656
A R^2 of 0.244 
Equation of the line y=-0.0795x+15.52

Based on these findings, the analysis indicates that the relationship between discount percentage and reviews is very weak, suggesting that the level of discount does not strongly explain differences in the number of reviews.

#### Rating and Reviews
Another scatter plot was created using the Rating and Reviews entries. A trendline was incorporated and the R^2 value calculated as well as the equation of the line.

The findings were:
Correlation of 0.05721
R^2 of 0.0244
Equation of the line y=-0.0795x+15.52

The correlation coefficient of 0.05721 indicates a very weak positive relationship between the two variables. The R² value of 0.0244 suggests that approximately 2.44% of the variation in reviews can be explained by rating, indicating that rating has very little influence on the number of reviews. Overall, the analysis suggests that there is no strong relationship between product rating and the number of reviews in the dataset.

### Current Price Versus Rating
Finally, the relationship between prices and ratings was analyzed and we acquired the following values

Correlation of 0.110090213
R^2 of 0.2264
Equation of a line y=-0.0182x+4.52

The scatter plot indicates a very weak relationship between the two variables, with a correlation coefficient of 0.1101. The R² value of 0.2264 indicates that approximately 22.64% of the variation in the dependent variable is explained by the independent variable. The regression equation, y = -0.0182x + 4.52, shows a slight negative trend, meaning that the dependent variable tends to decrease as the independent variable increases. Overall, the relationship is weak, and the independent variable provides limited explanation of the dependent variable.

## 2.Pivot tables analysis interpretation
## Product Performance Findings
### Top Products by Rating
The top 10 products by rating recorded an average rating of 4.94/5. Seven of these products had the maximum rating of 5.0, while the remaining three had ratings of 4.8. These products represent the highest-rate listings in the dataset and may provide useful examples of products associated with strong customer satisfaction.
### Top Products by Discount
The top 10 products by discount had an average discount of 54%. The highest individual discount was 61%, recorded for the Pen Grips for Kids Pen Grip Posture Correction Tool for Kids. Several other products had discounts between 52% and 55%, indicating that some listings were offered with substantial price reductions.
### Low-Rated Products
The bottom five products by rating had an average rating of 2.12/5, compared with the overall dataset average of 3.89/5. The lowest-rated product was the Wall-Mounted Sticker Punch-Free Plug Fixer, with a rating of 2.0/5. These products may require closer attention to customer expectations, product quality, product descriptions, or marketing strategy.
### Top Products by Reviews
The top 10 products by reviews accounted for 388 of the 723 total reviews, representing approximately 53.7% of all reviews in the dataset. The 120W Cordless Vacuum Cleaner had the highest review count with 69 reviews, followed by the 137 Pieces Cake Decorating Tool Set with 55 reviews. This indicates that review engagement is concentrated among a relatively small group of products.

## Business Recommendations
1. Prioritize High-Engagement Products
The top 10 products generated 388 of the 723 total reviews (53.7%), indicating that customer engagement is concentrated among a relatively small group of products. Jumia sellers should identify the characteristics of these high-engagement products and prioritize them for visibility, promotions, and inventory planning.

3. Review Promotion Strategies Rather Than Relying on Discounts Alone
Medium-discount products recorded the highest total reviews (348), followed by high-discount products (327), while low-discount products recorded 48 reviews. However, the correlation between discount percentage and reviews was only 0.044, indicating a very weak relationship. Sellers should therefore test targeted discounts rather than if larger discounts will automatically increase customer engagement.

5. Investigate Low-Rated Products Before Increasing Promotion
The bottom five products by rating had an average rating of only 2.12/5, compared with the overall dataset average of 3.89/5. Sellers should investigate customer feedback, product quality, product descriptions, and customer expectations for these products before investing additional marketing or promotional resources in them.

7. Use High-Rated Products as Benchmarks
The top 10 products by rating recorded an average rating of 4.94/5, with seven products achieving a rating of 5.0. Sellers can examine these products to identify practices that may contribute to positive customer experiences, such as product quality, accurate descriptions, pricing, and fulfillment.

9. Avoid Using Price or Rating as Standalone Predictors of Engagement
The analysis found very weak relationships between rating and reviews (0.0572) and between current price and rating (0.1101). Sellers should therefore avoid making pricing or marketing decisions based on a single metric. A broader approach combining price, discount, ratings, reviews, product quality, and customer feedback would provide a stronger basis for decision-making.

## Limitations

1. No sales or revenue data: The dataset does not contain actual sales, revenue, profit, or conversion data. Therefore, reviews are used only as a proxy for customer engagement and should not be interpreted as direct evidence of sales performance.
2.	Missing ratings: 55 out of 112 products (49.1%) have no recorded rating. This limits the reliability of comparisons involving product ratings and may affect the overall interpretation of rating-based analysis.
3.	No listing-age information: The data set does not indicate how long each product has been listed. Products that have been available for longer may naturally accumulate more reviews, which cannot be accounted for in this analysis.
4. Correlation does not imply causation: The correlation analyses show relationships between variables but cannot establish that discounts, prices, or ratings directly cause changes in review engagement.
5.	Limited product and customer information: The dataset does not include detailed customer review comments, product quality measures, seller information, delivery performance, or other factors that may influence ratings and reviews.
6.	Dataset size: The analysis is based on 112 products, so the findings may not represent the performance of all products on Jumia or the wider e-commerce market.
7.	Snapshot of product performance: The data set represents the products available in the data collected and may not reflect changes in prices, discounts, ratings, or reviews over time.

## Conclusion
The Jumia Product Performance Dashboard provides a consolidated view of product pricing, discounts, ratings, and customer review engagement across 112 products. The analysis found that the relationships between discount and reviews, rating and reviews, and current price and rating were all very weak, suggesting that no single pricing or rating variable strongly explains customer review engagement in this dataset.
Product-level analysis showed that engagement was concentrated among a small group of products, with the top 10 products accounting for 388 of 723 total reviews (53.7%). At the same time, the bottom five rated products had an average rating of 2.12/5, highlighting products that may require further investigation. The analysis also showed substantial variation in discount levels, while 55 products (49.1%) had missing ratings, limiting some rating-based comparisons.
Overall, rather than relying on discounts, prices, ratings, or reviews individually, sellers should consider multiple performance indicators together when making pricing, promotional, and product-management decisions. Further analysis using sales, revenue, listing age, and detailed customer feedback would provide a stronger basis for evaluating product performance.



