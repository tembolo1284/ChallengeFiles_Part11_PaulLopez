# Project Title

This is the Time series analysis application for challenge 11! This is one my favorite challenges so far.

I begin by pulling in the google_hourly_search_trends.csv file, and checking the first and last five rows.
I then slice the data to only look at May, 2020, and I plot it.  Then I calculate the total traffic for the month of May, 2020, and I 
compare this to median and sum of all the months that I have for every year in my data. I'm immediately able to determine
that there is indeed an increase in traffic when MercadoLibre released their financial results. It's a somewhat obvious result, but it is so great that we are able to prove it with data and visualization tools!

For the next part I group the hourly search data by weekday and calculate the mean.  I then run a heatmap looking at this data
to determine if there is any concentration of search traffic in just a few hours of a particular day. It is easy to see that there is
a concentration!

After the above is complete I then group the data by weeks in a year to see if there is any increased traffice during the winter holiday season, or between weeks 40 through 52 in the year. Again with the tools we are using it is easy to see that overall there 
is a healthy increase!

For the next part I pull in mercado_stock_price.csv and check the first five rows and the last five rows.  From here
the fun begins! I concatenate my two datafames where I have search traffic and stock prices.  I slice the data to just
the first half of the year.  From there I run an hvplot to look at both search traffic and stock prices.  I then answer the question
of whether both time series plots indicate a common trend that is consistent with companies facing difficulty in the first half
of 2020 because of the covid pandemic getting in full swing.  I believe both time series definitely indicate that!

From here I create two new columns to add to my dataframe: The first one is an exponentially weighted four-hour rolling
average that is based on the company volatility of their stock.  The second column is a simple hourly stock return, or percent
change function call based on the hourly stock price of the company.  I then run an hvplot on the stock volatility and notice
a healthy spike!

For the next part I create a correlation table of Stock volatility, Lagged Search Trends, and hourly stock returns. I 
then determine if I see a predictable relationship between the lagged search traffic and the stock vol, or between
the lagged search traffic and the stock price returns. This was probably my favorite part. It hits home ;)

For this last part I finally make use of Prophet.  I begin by formatting the dataframe to be compatible with colab.
I instantiate an instance of the Prophet model. It has begun!  I make predictions going out about 80 days by using
make_future_dataframe.  


## Story

In a bid to drive revenue, you’ll produce a Jupyter notebook that contains your data preparation, analysis, and visualizations for all the time series data that the company needs to understand. You’ll use text and comments to document your findings, and you’ll answer the question prompts in the instructions. Specifically, this file should contain the following:

Visual depictions of seasonality (as measured by Google Search traffic) that are of interest to the company.

An evaluation of how the company’s stock price correlates to its Google Search traffic.

A Prophet forecast model that can predict hourly user search traffic.

Answers to questions in the instructions that you write in your Jupyter Notebook.

(Optional) A plot of a forecast for the company’s future revenue.

Push your final notebook to your GitHub repository so that others can review your work.

---

## Technologies

I am using python version 3.7.10 and am importing the following from the built-in libraries and from functions i've created myself:

import pandas as pd
import holoviews as hv
from fbprophet import Prophet
import hvplot.pandas
import datetime as dt
import numpy as np
%matplotlib inline
I also install the following:

!pip install pystan
  !pip install fbprophet
  !pip install hvplot
  !pip install holoviews

---

## Installation Guide

I have python version 3.7.10 and git version 2.33.0.windows.2 installed on a laptop running windows 10 pro.

I launch the facebook colab webpage, upload forecasting_net_prophet.ipynb and that's it!


---

## Usage

Just upload the forecasting_net_prophet.ipynb notebook and run the code. User can feel free to change any dates used for charts or slicing if they want to study anything else.


---

## Contributors
Just me, Paul Lopez.


---

## License
No licenses required. Just install everything for free, pull from my repository, and enjoy!
