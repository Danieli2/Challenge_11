** #Challenge_11**


**Background**

I am growth analyst at MercadoLibre. With over 200 million users, MercadoLibre is the most popular e-commerce site in Latin America. I have been tasked with analyzing the company's financial and user data in clever ways to make the company grow. So, I want to find out if the ability to predict search traffic can translate into the ability to successfully trade the stock.

**What I Created**

In a bid to drive revenue, I produced a Jupyter notebook that contains my data preparation, analysis, and visualizations for all the time series data that the company needs to understand. I used text and comments to document my findings, and I answered the questions prompts in the instructions. 
The subsections detail these steps.
***
**Step 1: Find Unusual Patterns in Hourly Google Search Traffic**

The data science manager asks if the Google search traffic for the company links to any financial events at the company. Or, does the search traffic data just present random noise? 
To answer this question, I picked out any unusual patterns in the Google search data for the company, and I connect them to the corporate financial events.
To do so, I complete the following steps:
1. I read the search data into a DataFrame, and then sliced the data to just the month of May 2020. 
2. Use hvPlot to visualize the results. Do any unusual patterns exist?
3. I calculated the total search traffic for the month, and then compared the value to the monthly median across all months. Did the Google search traffic increase    during the month that MercadoLibre released its financial results?
***
**Step 2: Mine the Search Traffic Data for Seasonality**

Marketing realized that I could  use the hourly search data, too. If they can track and predict interest in the company and its platform for any time of day, they can focus their marketing efforts around the times that have the most traffic. This will get a greater return on investment (ROI) from their marketing budget.
To that end, I wanted to mine the search traffic data for predictable seasonal patterns of interest in the company. 
To do so, I complete the following steps:
1. I grouped the hourly search data to plot the average traffic by the day of the week (for example, Monday vs. Friday).
2. Using hvPlot,I visualized this traffic as a heatmap, referencing the index.hour as the x-axis and the index.dayofweek as the y-axis.  
3. I Grouped the search data by the week of the year. 
***
**Step 3:Relate the Search Traffic to Stock Price Patterns**

The finance group at my company. Wanted to know if any relationship between the search data and the company stock price exists, and they asked if I could investigate.
To do so, I complete the following steps:
1. I read in and plot the stock price data. Concatenated the stock price data to the search data in a single DataFrame.
2. I sliced the data to just the first half of 2020 (2020-01 to 2020-06 in the DataFrame), and then use hvPlot to plot the data. 
3. I created a new column in the DataFrame named “Lagged Search Trends” that offsets, or shifts, the search traffic by one hour. 
4. I then created two additional columns:
     “Stock Volatility”, which holds an exponentially weighted four-hour rolling average of the company’s stock volatility
     “Hourly Stock Return”, which holds the percent change of the company's stock price on an hourly basis
5. I then reviewed the time series correlation 
***
**Step 4:Create a Time Series Model with Prophet**

I produced a time series model that analyzes and forecasts patterns in the hourly search data. To do so,I completed the following steps:

1. I set up the Google search data for a Prophet forecasting model.
2. After I estimated the model, then I plotted the forecast. 
3. I plotted the individual time series components of the model 
***
**Step 5(Optional): Forecast Revenue by Using Time Series Models**

A few weeks after my initial analysis, the finance group follows up to find out if I can help them solve a different problem. 
Specifically, the finance group wants a forecast of the total sales for the next quarter. This will dramatically increase their ability to plan budgets and to help guide expectations for the company investors.
To do so, I completed the following steps:
1. I read in the daily historical sales (that is, revenue) figures, and then applied a Prophet model to the data.
2. I Interpretted the model output to identify any seasonal patterns in the company's revenue.
3. I Produced a sales forecast for the finance group. Giving them a number for the expected total sales in the next quarter. I included the best- and worst-case        scenarios to help them make better plans.
