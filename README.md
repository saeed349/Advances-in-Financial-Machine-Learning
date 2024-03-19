Implementations of few key topics from chapter 2 of the the book [Advances in Financial Machine Learning](https://www.amazon.in/Advances-Financial-Machine-Learning-Marcos/dp/1119482089) by Marcos Lopez de Prado.

# Overview

1. **1_rolling.ipynb**: Initial analysis and creating adjusted futures price.
2. **2_bar.ipynb**: Sampling observation and create tick, volume and dollar-traded bars.
3. **3_analysis.ipynb**: Some statistical tests on the bars created. 

The subsections of the notebooks is structured as follows

**1_rolling.ipynb**:
+ 1.1 Basic EDA (Exploratory Data Analysis)
  * 1.1.1 Initial Analysis <br>
  * 1.1.2 Checking the full dataset to see how its structured before rolling <br>
+ 1.2 Rolling Futures Contracts <br>
  * 1.2.1 Pandas Implementation - sample data <br>
  * 1.2.2 Dask Implementation - sample data <br>
  * 1.2.3 Rolling over entire dataset <br>
  * 1.2.4 Plotting to check rolling adjustment <br>

**2_bar.ipynb**:
+ 2.1 Tick Bar
+ 2.2 Volume Bar
+ 2.3 Volume Bar

**3_analysis.ipynb**:
+ 3.1 Weekly Count
+ 3.2 Serial Correlation
+ 3.3 Monthly subset
+ 3.4 Check for normality

# Environment and Tools

Since the tick data has around 900 million rows of data, doing all the computation in memory using Pandas is hard. So for the first 2 part of the project (rolling and bar sampling) we'll be using [Dask](https://www.dask.org/) which is a python library for parallel and distributed computing. The reason why we are using Dask is so that we can write all the rolling and sampling code using Pandas and just use Dask it to scale it without having to change the code. This lets us easily analyze the data and create our analytics in Pandas and just scale it using Dask without changing any code. 

For this project all the data processing (including rolling, sampling, dask tasks) was done on my local machine (Intel i7 4 cores and 16GB RAM). The code has been run in Python 3.8 with the following packages
* dask==2022.7.0 
* pandas==1.5.3 
* numpy==1.23.5 
* h5py==3.7.0 
* sklearn==1.2.1 
* scipy==1.10.0
* statsmodels==0.13.5 
* matplotlib==3.7.0 
* plotly==5.9.0 
* seaborn==0.12.2
