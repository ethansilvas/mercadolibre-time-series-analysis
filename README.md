# Module 11 Challenge - Mercado Libre Time Series Analysis

This project is best viewed/ran in Google Colab! -> <a href="https://colab.research.google.com/github/ethansilvas/mercadolibre-time-series-analysis/blob/main/forecasting_net_prophet.ipynb" target="_parent"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a>

This is my time series analysis of Mercado Libre's Google search trend and stock price data to find out if the ability to predict search traffic can translate into the ability to successfully trade the stock. In my analysis I visualize the data's seasonality, evaluate how the company's stock price correlates to its Google search traffic, and use [Facebook's Prophet](https://facebook.github.io/prophet/) to train a machine learning model that forecasts search traffic and future revenue. 

### Data Used
1. [google_hourly_search_trends.csv](/Resources/google_hourly_search_trends.csv) - Hourly Google search traffic values 2016-2020
2. [mercado_stock_price.csv](/Resources/mercado_stock_price.csv) - Closing stock price values 2015-2020
3. [mercado_daily_revenue.csv](/Resources/mercado_daily_revenue.csv) - Daily revenue reported in millions of dollars 2019-2020

### Summary

---

## Technologies

This is a Python 3.7 project ran using a JupyterLab in a conda dev environment. 

The following dependencies are used: 
1. [Jupyter](https://jupyter.org/) - Running code 
2. [Conda](https://github.com/conda/conda) (4.13.0) - Dev environment
3. [Pandas](https://github.com/pandas-dev/pandas) (1.3.5) - Data analysis
4. [Matplotlib](https://github.com/matplotlib/matplotlib) (3.5.1) - Data visualization
5. [Numpy](https://numpy.org/) (1.21.5) - Data calculations + Pandas support
6. [hvPlot](https://hvplot.holoviz.org/index.html) (0.8.1) - Interactive Pandas plots 

---

## Installation Guide

If you would like to run the program in JupyterLab, install the [Anaconda](https://www.anaconda.com/products/distribution) distribution and run `jupyter lab` in a conda dev environment.

To ensure that your notebook runs properly you can use the [requirements.txt](/Resources/requirements.txt) file to create an exact copy of the conda dev environment used in development of this project. 

Create a copy of the conda dev environment with `conda create --name myenv --file requirements.txt`

Then install the requirements with `conda install --name myenv --file requirements.txt`

---

## Usage

The Jupyter notebook []() will provide all steps of the data collection, preparation, and analysis. Data visualizations are shown inline and accompanying analysis responses are provided.

---

## Contributors

[Ethan Silvas](https://github.com/ethansilvas)

---

## License

This project uses the [GNU General Public License](https://choosealicense.com/licenses/gpl-3.0/)