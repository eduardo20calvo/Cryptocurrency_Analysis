# Cryptocurrency Analysis

The purpose of this analysis is to analyze the metrics of three of the most popular cryptocurrencies; Bitcoin, Ethereum and Cardano, and determine if there is any correlation among their metrics. These metrics include Closing Price, Marketcap Dominance, Volatility, Active Addresses Count, Addresses with Balance Greater than $100K and Average Transaction Fees. In addition, a time series analysis was performed for each cryptocurrency to forecast its price in one month as of November 2022. The data for the metrics was pulled from a source called Messari where the data was downloaded as CSV files. The tools/libraries used include Numpy, Pandas, hvPlot, Seaborn, Matplotlib, Pystan, HoloViews and Prophet. The main programming language used was Python. 

## Bitcoin, Ethereum, Cardano Metrics Correlation

The dataset containing metrics for each of the coins were organized in a DataFrame and each metric was plotted as an hvPlot. Below are the hvPlots for each of the coin's metrics:

![Screenshot 2022-12-19 205459](https://user-images.githubusercontent.com/104874384/208562926-7b50a928-23e1-438d-9da7-d597540d5e66.png)

![Screenshot 2022-12-19 205540](https://user-images.githubusercontent.com/104874384/208563068-0227c17a-ab0b-4a87-aa0a-a5a282af594f.png)

![Screenshot 2022-12-19 205644](https://user-images.githubusercontent.com/104874384/208563143-d776b79e-e76d-47f7-8cc3-480483bd03cb.png)

![Screenshot 2022-12-19 205715](https://user-images.githubusercontent.com/104874384/208563197-605a8ecf-4936-4b43-8fe3-740862b6ed3e.png)

![Screenshot 2022-12-19 205800](https://user-images.githubusercontent.com/104874384/208563277-1244ca02-a561-4e98-8aa9-fdb9f4e04d24.png)

Each of the coin's metrics were also compared to one another for correlation using a heatmap. Below is the heatmap for Bitcoin's metrics:

![Screenshot 2022-12-19 213826](https://user-images.githubusercontent.com/104874384/208568963-527d2a5b-cc0c-4fe3-9adf-4bb93f50d609.png)

Based on the graph above, the metrics most correlated to each other are Price with Addresses with Balance Greater than $100K and Active Addresses Count with Addresses with Balance Greater than $100K.

The following shows the correlation for Ethereum's metrics:

![Screenshot 2022-12-19 214111](https://user-images.githubusercontent.com/104874384/208569267-ef192adf-d2d9-4584-a381-73a697414146.png)

Based on the graph above, it seems as if Price is fairly correlated with all the metrics except Volatilty.

Last but not least, the following shows the correlation for Cardano's metrics:

![Screenshot 2022-12-19 214340](https://user-images.githubusercontent.com/104874384/208569526-9b8a3aa3-b3bc-4f6a-a101-2d5d6c216366.png)

Similar to Ethereum's metrics, Price is heavily correlated with all the metrics except Volatility. The only difference is that the correlation is more amplified with Cardano's metrics. All in all, Ethereum and Cardano share similar correlations in their metrics. Based on the heatmaps, it is clear that there is a strong negative correlation with Volatilty in the market. You can determine as the volatility is high, there is more uncertainty in the market for Ethereum and Cardano, which will drive users/investors to sell and not participate. 

Bitcoin on the other hand, you can infer that the whales seem to have more influence in the market as there is a heavy correlation with users who have at least $100K in their wallets and the price. These whales also seem to be the most active in the market as seen in the correlation between Active Addresses Count with Addresses with Balance Greater than $100K.

## Bitcoin, Ethereum and Cardano Time Series Analysis

To make the time series analysis for all coins, Google Colab IDE was used as it's the only IDE that supports the usage of the Prophet Model.

To begin, the historical price of Bitcoin was graphed into the hvPlot below:

![bokeh_plot (14)](https://user-images.githubusercontent.com/104874384/208578009-4f90f0c8-65e8-48f8-af3c-234b9274b4ce.png)

Before the Prophet model was called, both the Date and Price columns of the DataFrame from earlier were renamed to "ds" and "y" respectively, so that the model can be recognized. Once this was ready, the Prophet Model was called. The new dataset created was then fitted into the model. A new DataFrame was created to hold Prophet predictions as far as 40 days. Finally, the predictions were made using the model. Below is the resulting plot of the Bitcoin Price predictions:

![Screenshot 2022-12-19 223945](https://user-images.githubusercontent.com/104874384/208578571-87716357-a139-44e2-a2c2-15517f8a27e8.png)

As you can see, it predicted the price of Bitcoin will continue to go down at the time of this analysis. With the other predictions generated from the model, we were also able to pull 3 metrics from the predictions Dataframe, being "Worst Case", "Most Likely Case", and "Best Case" prices. Below you will find the average price for each of the categories:

![bokeh_plot (15)](https://user-images.githubusercontent.com/104874384/208578918-7d73cf95-89b9-409b-a517-a23d44e799b1.png)

As you see, with Prophet, we were able to find that the worst case price for Bitcoin in 40 days at the time of this analysis would be about $16,010. The best case price would be about $24,260. But the most likely price would be about $20,140.

The results for Ethereum are as follows:

![bokeh_plot (16)](https://user-images.githubusercontent.com/104874384/208579337-e1db0658-1c1f-4e54-8830-903927a8c001.png)

![Screenshot 2022-12-19 224911](https://user-images.githubusercontent.com/104874384/208579441-18d5fe9a-ed1a-478b-9501-bcc6a64fdf88.png)

![bokeh_plot (17)](https://user-images.githubusercontent.com/104874384/208579471-33421846-a86b-49d2-aa09-c17bbea4b164.png)

The worst case price for Ethereum would be about $772. The best case price would be $1,481. Last but not least, the most likely price would be $1,127.

The results for Cardano are as follows:

![bokeh_plot (18)](https://user-images.githubusercontent.com/104874384/208579862-9afd6ed1-5064-47de-8392-6cd5c158caac.png)

![Screenshot 2022-12-19 225342](https://user-images.githubusercontent.com/104874384/208579950-52fa02ce-e8ce-4060-8851-23e49df05680.png)

![bokeh_plot (19)](https://user-images.githubusercontent.com/104874384/208579989-a25b83b0-1b8c-42e1-86f2-51a9f97d7616.png)

The worst case price for Cardano would be about $0.26. The best case price would be $0.71. Finally, the most likely price would be $0.49.
