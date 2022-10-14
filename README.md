# Business Solution for Real State Company
## <p align="center" dir="auto">Data Science Insights Project</p>
<div align="center">
<img src="https://user-images.githubusercontent.com/103151311/195822516-02686b8c-0096-4ad3-896e-6f0801010978.jpg" width="700" />
</div>


# 1. House Rocket and Business Problem
House Rocket is a real state company whose model consist in identifying good properties with a good price and futurely sold for a higher price aiming to maximize profit. For this case, we will be operating on King Country.

Obs: The company and business problem are both fictitious, although the data is real.

This Data Science project is focused on solving two problems:

+ Problem 1: Which properties should House Rocket buy and for which suggested price?
+ Problem 2: Once a property is bought, for which price should it be sold?

# 2. Data Overview
Feature   | Definition
:--------- | :------
id   | Unique ID for each home sold
date | 	Date of the home sale
price | Price of each home sold
bedrooms | Number of bedrooms
bathrooms | Number of bathrooms, where .5 accounts for a room with a toilet but no shower
sqft_living | Square footage of the apartments interior living space
sqft_lot | Square footage of the land space
floors | Number of floors
waterfront | A dummy variable for whether the apartment was overlooking the waterfront or not
view | An index from 0 to 4 of how good the view of the property was
condition | An index from 1 to 5 on the condition of the apartment
grade | An index from 1 to 13, where 1-3 falls short of building construction and design, 7 has an average level of construction and design, and 11-13 have a high quality level of construction and design.
sqft_above | The square footage of the interior housing space that is above ground level
sqft_basement | The square footage of the interior housing space that is below ground level
yr_built | The year the house was initially built
yr_renovated | The year of the house’s last renovation
zipcode | What zipcode area the house is in
lat | Lattitude
long | Longitude
sqft_living15 | The square footage of interior housing living space for the nearest 15 neighbors
sqft_lot15 | The square footage of the land lots of the nearest 15 neighbors

# 3. Assumptions
+ Location in real estate is undoubtedly a decisive factor in price evaluation.
+ The address information for these properties was gathered by using the two created modules: address.py and defs.py.

# 4. Solution Plan
## 4.1. How both problems were solved
### Problem 1: Which properties should House Rocket buy and for which suggested price?
To solve this problem, we firstly need to analyse the properties by their location, because in real estate, location is undoubtedly a decisive factor in price evaluation. 
One interesting metric in this case is to calculate the price median by each zipcode, as the median isn't influenced by extreme values (outliers) in the data.

Then we will take the median price for each one of the zipcodes and build a table of recomendation respecting the following rules:

+ Their asked price has to be lower than the median price for that region
+ The property needs to be in good conditions, which means condition >= 3

As for suggested price, we will take into account the density of the region, which means that regions that have more houses to sell, it is viable to offer lower prices. Therefore the rule we will follow is:

+ From 0 to 204 properties in the region => Offer the asked price
+ From 205 to 282 properties in the region => Offer 3% less than the asked price
+ From 283 to 408 properties in the region => Offer 5% less than the asked price
+ From 409 properties upwards => Offer 7% less than the asked price

### Problem 2: After we buy a house, for which price should it be sold?
To suggest a sell price, again the density by region will be considered, since for regions where the number of real estate ads is lower it's possible to sell the property for a higher price, and vice-versa. Hence, a reasonable rule for suggested sell prices is:

+ From 0 to 204 properties in the region => Sell for 15% than the suggested buy price
+ From 205 to 282 properties in the region => Sell for 14% than the suggested buy price
+ From 283 to 408 properties in the region => Sell for 12% than the suggested buy price
+ From 409 properties upwards => Sell for 10% than the suggested buy price

## 4.2. What was delivered as solution
+ Buy Suggestion Table: Contains the suggestion price to buy and sell

## 4.3. Financial Results
+ Profit Descriptive Analyses
+ Average and median profit grouped by zipcode
+ House Rocket Cloud App: App deployed using Streamlit Cloud containing all tables (Buy Suggestion Table, Sell Suggestion Table and Financial Results Tables)
with filters and a Buy Suggestion Map, as well as data insights.

## 4.4. Tools and techniques used
+ Python, Pandas, Matplotlib, Plotly and Geopandas.
+ Jupyter Notebook and VSCode.
+ Streamlit and Streamlit Cloud.
+ Git and Github.
+ Measures of Central Tendency and Dispersion.
+ Exploratory Data Analysis (EDA).

# 5. Business Insights
<p align="center" dir="auto">Properties with more bathrooms are more expensive on average</p>
<div align="center">
<img src="https://user-images.githubusercontent.com/103151311/195824451-85303aba-cc9c-46a1-83ca-d3ff777503d5.png" width="600" />
</div>
Usage: House Rocket could buy a house with few bathrooms and build bathrooms aiming to increase de profit
<hr>
</hr>
<p align="center" dir="auto">Proprerties with larger living area are more expensive on average</p>
<div align="center">
<img src="https://user-images.githubusercontent.com/103151311/195824505-0e69899f-aab3-431c-9d80-43a7d8f6e825.png" width="600" />
</div>
Usage: House Rocket could buy some lot with low living area and build one more room or bathroom
<hr>
</hr>
<p align="center" dir="auto">Proprerties waterfront</p>
<div align="center">
<img src="https://user-images.githubusercontent.com/103151311/195824547-5922f036-dc95-4241-a68c-fe1520063e56.png" width="600" />
</div>
Usage: House Rocket could focus on buying and selling waterfront view properties, since the profit will be higher in absolut values.
<hr>
</hr>

# 6. Financial Results
Three interesting metrics to evaluate the financial performance for this solution is the profit mean and median, as well as the total profit. This in-depth information can be found in here. As for the profit for each property it can be checked in the House Rocket Cloud App, where filters can also be applied for better visualization.

If this feasible solution strategy used in this project were applied by House Rocket the total obtained profit would be US$ 463,714,394.29 with an average profit of US$ 44,096.08 per property. The main profit metrics are displayed below:

Metric   | Profit (US$)
:--------- | :------
Total Profit  | 463,714,394.29
Mean Profit | 44,096.08
Median Profit | 38,595.00
Min Profit | 8,044.50
Max profit | 282,000.00

# 7. Conclusion
In this project the two main objectives were accomplished:

+ A feasible solution was found for both business problems, leading to profitable results.
+ Three interesting and useful insights were found through Exploratory Data Analysis (EDA).

We also managed to deliver table with in-depth financial results, as well as buy and sell suggestion prices. All this information can be filtered by using the House Rocket Cloud App, that also has the five business insights and a interactive Buy Suggestion Map.

# 8. Next Steps
+ We could improve the solution applying a regression machine learning model to determinate wheter a propertie has a good buying price and for which price it could be sold







