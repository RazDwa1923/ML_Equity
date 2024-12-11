# ML Pricing Algorithm Plan

### Objective

The aim of this document is to outline the next steps I will go through in order to build a ML model to predict P/E ratios of stocks

Two potential models I will build:

1. Fundemental Model: Quarterly Data using Financial Statements { symbolized by F}
2. Correlation Model: Daily Data using Prices and Indicies {symbolized by Q}


#### Building Dataset

API: The selected API will be from Financial Model Prep. The overview of the API can be accessed at [FMP API Overview](https://site.financialmodelingprep.com/developer/docs#valuation)

I will be building datasets for the following categories:

- [ ] Price Data {Q} : Daily Prices (get Earnings Annoucments dates from FMP and prices for day, week and month after from another source where prices are available __[requires two steps]__)
- [X] Financial Statement Data {F} : Quarterly Statments and Earnings
- [X] Earnings Data {F} : Earnings per share currrent and forecast (quarterly or trailing 12months)
- [X] Company Specific Information {F} : Information describing the Company
- [ ] Market Indicies {QF} : Index data of major exchnages 
- [ ] Economic Factors {QF} : Treasury yields, commodity prices, gold, unemployment, GDP releases
- [ ] Exchange Structure {QF} : Volumes over time, also can be combined volume during time or average volumes
- [X] Ratios/Specialized KPI {QF}: Financial statement ratios or created ratios such a Piotrowski Score

In order to support data creation, I will also need to create datasets or dictionaries with the following info:

- [x] S&P and Nasdaq members and symbols
- [x] Industry labels for classyfing stocks into industries 
- [x] Dates and quarters labels

Data Parameters:

- Time Frame: 5 years
- Frequency: Daily and Quarterly
- Separate Tables for each of above categories



#### Data Cleaning and Preparation

After each of the above the data tables are prepared, the following steps will be taken:

- Check for Missing Values
- Check for Duplicates
- Check for Outliers
- Check for Data Types

Once the data is cleaned each of the tables will be saved and then merged into a single dataset for each of the models. 

The tables will follow 3 principles:
1. Every column is a variable.
2. Every row is an observation.
3. Every cell is a single value.

In effect, the data will be a cross sectional timeseries dataset with each stock symbol as the observation and the variables as the columns.

In order to better work with a time series I will also translate the data into difference btw periods and percentage change.


#### Data Exploration and Visualization

Before embarging on building the models, I will explore the data to understand the relationships between the variables and the target variable.

The following steps will be taken:

- Descriptive Statistics
- Correlation Matrix
- Time Series Plots
- Scatter Plots
- Box Plots

The above will be done for each of the models. And the main aim is to understand the relationships between the variables and the target variable to see whether statistical relationships exist and are normally distributed.


#### Feature Engineering

After the data is explored, I will engineer features to be used in the models. The following steps will be taken:

- Create new variables
- Transform variables
- Scale variables
- Normalize variables
- Create dummy variables
- Create lagged variables
- Create rolling variables
- Create moving average variables
- Create momentum variables
- Create volatility variables
- Create trend variables
- Create seasonality variables
- Create interaction variables
- Create polynomial variables
- Create log variables



#### Model Building

After the features are engineered, I will build the models. The following steps will be taken:

- Split the data into training and testing sets
- Train the models
- Evaluate the models
- Tune the models
- Test the models
- Compare the models
- Select the best model

Possible Models to evaluate are:

- Linear Regression
- Ridge Regression
- Lasso Regression
- Elastic Net Regression
- Decision Trees
- Random Forest
- Gradient Boosting
- AdaBoost

I would like to also test designing models using Neural Networks and Support Vector Machines.

The model will be evaluated to see how well they predict the P/E ratio of stocks.

Once, I have the best model I would like to also build a pipeline to automate the model building process. 

The pipeline will then suggest stocks that are undervalued or overvalued based on the model predictions and the actual P/E ratios.

The suggested trades will be then backtested and the results will be analyzed.
