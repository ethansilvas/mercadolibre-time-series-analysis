# Module 11 Challenge - Mercado Libre Time Series Analysis

This project is best viewed/ran in Google Colab! -> <a href="https://colab.research.google.com/github/ethansilvas/mercadolibre-time-series-analysis/blob/main/forecasting_net_prophet.ipynb" target="_parent"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a>

This is my time series analysis of Mercado Libre's Google search trend and stock price data to find out if the ability to predict search traffic can translate into the ability to successfully trade the stock. In my analysis I visualize the data's seasonality, evaluate how the company's stock price correlates to its Google search traffic, and use [Facebook's Prophet](https://facebook.github.io/prophet/) to train a machine learning model that forecasts search traffic and future revenue. 

### Data Used
1. [google_hourly_search_trends.csv](/Resources/google_hourly_search_trends.csv) - Hourly Google search traffic values 2016-2020
2. [mercado_stock_price.csv](/Resources/mercado_stock_price.csv) - Closing stock price values 2015-2020
3. [mercado_daily_revenue.csv](/Resources/mercado_daily_revenue.csv) - Daily revenue reported in millions of dollars 2019-2020

### Summary

I start by finding unusual patterns in the Google search traffic, and to do so I look at the data from May 2020 which was the trends during peak Covid. For that month I compare the total search traffic to the median total search traffic across the whole dataset. 

![Line graph showing spike in May 5th 2020 for Mercado Libre Google search traffic](/Resources/Images/may-2020-trends.png)

Then I look for seasonality in the search trends by analyzing the search traffic based on day of the week and week of the year. 

![Heatmap showing that for each day of the week 11am-1pm have the highest search traffic](/Resources/Images/day-of-week-heatmap.png)
![Line graph showing that the first and last weeks of the year show the highest search traffic](/Resources/Images/week-of-year.png)

Next I analyze the stock price with the Google search trends to see if there are any correlating relationships between them.

![Correlation matrix showing an inverse relationship between lagged search trends and stock volatility, and a positive correlation between lagged search trends and hourly stock returns](/Resources/Images/trend-stock-corr.png)

After that I use Prophet to train a machine learning model to make in and out of sample forecasts (80 days out of sample). 

![Forecast line graphs showing metrics like Tuesday being the highest search traffic day, 11am-1pm being the highest search traffic times, and November seeing the lowest search traffic out of the year](/Resources/Images/trend-components.png)

Finally, I again use Prophet to create another model to forecast the next quarter's potential revenue based on the sales data. 

![Scatter plot showing the prophet model's prediction compared to actual values](/Resources/Images/revenue-forecast.png)

---

## Technologies

This is a Python 3.8 project ran in Google Colab but can be used in JupyterLab using a Conda dev environment. 

The following dependencies are used: 
1. [Jupyter](https://jupyter.org/) - Running code 
2. [Conda](https://github.com/conda/conda) (4.13.0) - Dev environment
3. [Pandas](https://github.com/pandas-dev/pandas) (1.3.5) - Data analysis
4. [Matplotlib](https://github.com/matplotlib/matplotlib) (3.5.1) - Data visualization
5. [Numpy](https://numpy.org/) (1.21.5) - Data calculations + Pandas support
6. [hvPlot](https://hvplot.holoviz.org/index.html) (0.8.1) - Interactive Pandas plots
7. [Holoviews](https://hvplot.holoviz.org/index.html) (1.14.9) - Interactive Pandas plots
8. [PyStan](https://pystan.readthedocs.io/en/latest/) (3.3.0) - Prophet support
9. [Prophet](https://facebook.github.io/prophet/) (1.1.1) - Machine learning time series forcasting models

---

## Installation Guide

The Google Colab notebook installs the required dependencies in the first cell: 
```python
# Install the required libraries
!pip install pystan
!pip install prophet
!pip install hvplot
!pip install holoviews
```

If you would like to run the program in JupyterLab, install the [Anaconda](https://www.anaconda.com/products/distribution) distribution and run `jupyter lab` in a conda dev environment.

To ensure that your notebook runs properly you can use the [requirements.txt](/Resources/requirements.txt) file to create an exact copy of the conda dev environment used in development of this project. 

Create a copy of the conda dev environment with `conda create --name myenv --file requirements.txt`

Then install the requirements with `conda install --name myenv --file requirements.txt`

---

## Usage

The Jupyter notebook [forecasting_net_prophet.ipynb](/forecasting_net_prophet.ipynb) will provide all steps of the data collection, preparation, and analysis. Data visualizations are shown inline and accompanying analysis responses are provided. It can be uploaded to Google Colab with the provided .csv files in `/Resources`, or can be viewed in the [GitHub uploaded version](https://colab.research.google.com/github/ethansilvas/mercadolibre-time-series-analysis/blob/main/forecasting_net_prophet.ipynb)

---

## Contributors

[Ethan Silvas](https://github.com/ethansilvas)

---

## License

This project uses the [GNU General Public License](https://choosealicense.com/licenses/gpl-3.0/)