### Iowa Liquor Sales


#### Introduction
Where would be a good location to open a storefront that would yield profits?

I was tasked with using exploratory data analysis and linear regression modeling in order to determine the three top counties to open a successful Liquor Store.
 
#### The Data

The data obained was from the Iowa.gov website. I built the model using a 10% subset of the data and then executed it on the full data set.

#### Import data & Mine the data

After importing the data using Pandas(a python library), I had to munge the data. This involved me dropping all null values and converting strings to integers so that we could conduct statistical analysis. Because we were looking for the location that would maximize sales, I start off by looking at the top statistics of sales/profits and transactions grouped by county. 

When comparing the transaction numbers of the top 15 counties to the sales figures of the top 15 counties, I noticed a new contender had jumped into the leader boards. Dallas County, which was around 20th in number of transactions, was rank 11 in sales. No other county had made this sort of significant jump. This was our starting point.

#### Refine the data

In order to build a model to support our findings, I had to first make a correlation heatmap to see which variables to use. If I had used every column, my model would have risked being overfit. After making the heatmap, the independent variables that I selected were [Profit, Bottles Sold, State Bottle Cost, State Bottle Retail, and Dummy variables for each county].


#### Building a model

The first time I ran the linear regession, my R^2 value for my train set was 99%. The same was true for my test data set. I took a deeper look at my correlation heat map, this time just looking at the variables that were used in my model. It became evident that Profit was incredibly correlated to sales and had to be causing such a suspicious R^2 value. 


#### The results

The model was ran again, this time dropping Profit as a variable. This yielded in an R^2 value of 71.57% for my training set, and 71.80% for my test set. Running lr.coeff_  and compiling it into a dataframe; then sorted descending allowed us to see which variables had the highest regression coefficient. The top three counties were Dallas: 64.37, Sioux: 24.23, and Carroll: 21.02.

Digging a little deeper, I decided to ask why was Polk the highest in sales and in number of transactions?
A 2015 Census of Polk County states the population at 467,711. Dallas County has a population of 80,133. Dallas is adjacent to Polk, which contains the city of Des Moines. This is the fastest growing city in the Midwest acording to the Census. Opening a Liquor store in Dallas would see future profits from all of the overflow coming from Des Moines as it continues to encroach towards Dallas County.

