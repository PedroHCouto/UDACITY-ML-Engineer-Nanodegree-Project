# Machine Learning Engineer Nanodegree

## Capstone Proposal: Stock Price Forecasting of brazilian commodity-based companies
### Using AWS DeepAR and LSTM on SageMaker
___

### 1. Domain Background:  
The stock price market might seems chaotic at a first glance. There is a lot of information that must be taken into account in order to decide whether to buy or not a stock. Some say that the Fundamental Analysis [1] is the right way to decide whether or not to buy a stock, and some say that the Technical Analysis [2].

Based on this lack of convergence about which method should be used, and once that we can find a giant amount of data, a data science project could be a nice fit to predict the behaviour of the prices in the next day. Therefore we could use these predictions to guide the decisions.
Nowadays, besides corona crises, the markets of the USA are on their historic maximum. This fact means that there is not so much place to find a share of business with good profits possibilities. Therefore, when we would like to have a bigger profit, we must take more risk and investments that fit this profile are those in emergent markets, like Brazil, India, China, etc. I’m a chemical engineer from Brazil and to use data science to understand the market behaviour for the next weeks are a topic that interests me a lot and can bring my education, my experience living here and my data science skills together.

As we know, the commodity is an economic good that is often used as input the production of other goods or services. These goods have full or substantial fungibility, that is, they can be treated as equivalent (or nearly) regardless of who produced them. Some examples are coffee, gold ore, iron ore, oil, water, electric power, etc. Brazil is a land that has a commodity-based economy [3] and to be able to predict the share prices of business that work in some level with commodities, cold be an excellent opportunity for discovering bad and good calls.

Besides that, nowadays there are lots of discussions about a commodity rally in 2021 [4] [5][6][7]. That means, understanding the future of these goods and being able the share price of the companies or even the commodity itself like gold or silver, are key points to have success investing in Brazil.

So let’s dive in the Brazilian Stock Prices of commodity-based companies, explore them and predict its prices! 


### 2. Problem Statement:  
As mention above, our interest lay on the future share price of commodity-based companies. It gets even more dramatic with 2021 bringing the potential for a commodity rally. To predict those stock prices are a big prize.
**Based on this, we can define that our problem is to analyse the 5 biggest commodity-based companies in Brazil in order to understand their behaviour and relationships as well to get a deeper understanding about what we are going to predict. Then, an algorithm as well its pipeline will be designed and implemented in order to predict the prices for the future.**  


### 3. The Datasets and Inputs:  
The data will be gathered using the Yahoo! Finance API. A great tutorial (unfortunately only in Portuguese) can be found in this [medium post](https://medium.com/@rodrigobercinimartins/como-extrair-dados-da-bovespa-sem-gastar-nada-com-python-14a03454a720). The library yahooquery gives us all tools to colect the data as we want.  

We will gather data of the 5 biggest commodity-based companies in Brazil, that are:
- Petrobras (PETR4): largest Brazilian company, Petrobras produces oil;
- Vale (VALE3): the company is among the largest companies in Brazil, and is the largest producer of iron ore in the world;
- CSN (CSNA3): it is the largest steel industry in Brazil and Latin America, and one of the largest in the world;
- JBS (JBSS3): the company is one of the largest producers of animal protein in the world;
- Suzano (SUZB3): the company is considered the largest producer of eucalyptus pulp of the world;


The data will be divided into 7 features for each day: lowest, highest, open, closed and adjusted close price, as well as volume and ticker.
Since the last truly commodity rally was in 2008 and these companies had their maximum prices there, it would be nice to start with data from 2007 until today. So it is 3306 instances (13 years * 252 + January 2021) for each company. In total there will be 16530 instances that will be compiled in a CSV and uploaded to S3.

For training data it will be used all data available until December 2020. For testing data, it will be used the all the data from 2021, it means January and a part of February.


### 4. Solution Statement:        
The solution is to test two algorithms used for forecasting:
    a. The DeepAR, created by Amazon and available in the Estimator API;
    b. Create my on Neural Network using LTSM (Long Short Term Memory) method.
Having these two method we can compare both and use the best one to deploy the solution.  


### 5. Benchmark Model:  
Since it is a personal project the benchmark can be established from a simple model or even a statistical model. For this case, I will use Random Forest as a regression algorithm to fit the data and to make predictions for the next days.
Using such a simple algorithm as a baseline is a good fit, we have a simple way to create a reference and if the DeepAR and my own model don’t perform better than a simple model, they should be put away or at least to suffer major changes.  

### 6. Evaluation Metrics:       
Because this type of forecasting works with continuous output that can be a big range of values, the metrics used in the project will be **MSE (mean square error)**, **RMSE (root mean square error)** and if needed **MAE (mean absolute error).**

### 7. Project Design:     
The steps the project will follow are:
a. Gathering the Data using yahoo API;
b. Cleaning and Exploring the Data;
    b.1. Explore the risk and volatility of each company;
    b.2. Explore the correlation between the closing price;
    b.3. Explore the moving averages and trends;
    b.3. Feature engineering like binning of the variation or computing the difference between the lowest and highest price for the day.
    b.4. Split the data into train and test;
c. Uploading the data to S3;
d. Scaling the data for a better performance of the models;
e. Create, Training and Testing a Random Forest Regressor for Baseline;
f. Create, Training and Testing a DeepAR model;
g. Create, Training and Testing and customized LSTM model as a rolling basis model;
    g.1. Fine tune of hyperparamenters like number of LSTM layers, number of neurons, dropout rate, learning rate, etc.;
h. Comparing the results of the models;
i. Deploy the best one.

Since this is the capstone project for Machine Learning Engineer Nano degree, all work will be done using AWS and will focus more on working with SageMaker whether to build extremely great models.


### REFERENCES:    
[1] https://en.wikipedia.org/wiki/Fundamental_analysis#The_two_analytical_models  
[2] https://en.wikipedia.org/wiki/Technical_analysis  
[3] https://www.thebalance.com/brazil-and-commodities-808912  
[4] https://www.nasdaq.com/articles/3-reasons-why-commodities-etfs-may-rally-in-2021-2021-01-15  
[5] https://www.reuters.com/article/column-russell-commodities-yearahead-idUSL1N2IQ0A2    
[6] https://plusmining.com/en/commodities-rally-is-projected-to-2021-the-coronavirus-would-mark-a-milestone-in-the-cycle-potentially-leaving-years-of-weak-prices-behind/  
[7] https://www.fxempire.com/forecasts/article/speculators-bet-on-a-continued-commodity-rally-in-2021-690009  
