# Google Adjusted Close Prediction

## Objective
In this data science project, our main goal was to determine Google's adjusted close given information surrounding days, such as Volume, Open, Close, High, Low and similar ticker information such as Netflix, Microsoft, Apple.

## Dataset
For this analysis, we used the Stock Market Performance Case Study dataset(https://www.kaggle.com/datasets/bhanupratapbiswas/stock-market-performance-case-study). The dataset that is going to be used for this project features stock market information for four companies, Apple, Microsoft, Netflix and Google. It features a three month data range where every open market day has the companies open, close, high, low, and adjusted close stock price for the period. It also features the volume of trades for that day(how many shares are traded). This is public data which can be found by exploring pretty much any finance site as all of these numbers are public knowledge and checked across multiple platforms. This dataset was last updated in May and therefore features data from February 7th to May 5th of 2023. Given this dataset the plan is to determine the expected adjusted close stock price for one company Google. We will create a model to determine this value given the opening price, highs, lows, and volume traded for both Google and also the other three companies as their is expected to be correlation due to being in the same industry. It would be more beneficial to have a wider range of dates for this model, however this range should be enough to create a valid model to determine expected stock closing price.

## Data Exploration and Insights
- During the exploration phase, we observed that their is a high correlation between each companies, High, Low, Open, Close, Volume and Adjusted Close.
- The volume has little direct correlation however is important in determining predictive natures of stock market models.
- Netflix is the least correlated between the four companies interestingly enough
- ![image](https://github.com/CSC380-SU23-UofArizona/final-project-cole-suddarth/assets/87513908/3fe5b780-981f-4e67-bafb-1fd6ef972b09)
- ![image](https://github.com/CSC380-SU23-UofArizona/final-project-cole-suddarth/assets/87513908/73e08235-eb9d-4370-a81c-d8d4e7701e64)



## Data Preprocessing
To ensure data quality and suitability for modeling, we performed the following preprocessing steps:
- Created individual DataFrames for each company, and a combined one for our modelling
- Scaled our data using the MinMaxScaler between 0 and 1 for normalization

## Feature Selection/Engineering
We conducted feature selection/engineering to improve model performance. The selected features were:
- Open, High, Low, Volume
- NFLX Open, High, Low, Volume, Close, Adj Close
- MSFT Open, High, Low, Volume, Close, Adj Close
- AAPL Open, High, Low, Volume, Close, Adj Close

## Model Selection
After analyzing different algorithms, we chose deep neural networks and linear regression as they are well-suited for this task.
- Deep neural networks are currently the best model algorithm for time-series models and the LSTM model is effective in remembering and forgetting data
- Linear regression is important as all data between stock information is linear and this would make the most sense

## Model Training and Evaluation
The dataset was split into training and testing sets. We used RMSE Loss to select the best model. 
- The models were assessed based on RMSE, producing the following results:
  - LSTM: 2.0684333178996384
  - Lasso: 4.602423987158262

## Results and Conclusion
Based on the evaluation,  I aimed to determine the expected Adjusted Close of the GOOG ticker given information on GOOG open, high, low as well as similar information from tickers like MSFT, NFLX, and AAPL. In this, I decided to use a dataset containing information on a GOOG, MSFT, NFLX, AAPL and their Open, Close, Adj Close, High, Low, and Volume over a three month period. Over observing this dataset we found that their is a strong correlation between GOOG features and the features for the other tickers. In determining a model for this, I chose to use a Lasso Regression and a LSTM neural network model. After training the models, I found that the LSTM neural network worked best to predict the Adjusted Close of the GOOG ticker. In order to pick the best model, I used the RMSE as we are along a time-based prediction. When tested I found that the LSTM model gave an accurate price to within 2.07 USD, while the Lasso model gave an accurate prediction to within 4.60 USD. Given that the mean value is 100.63 USD, this gives us an accuracy of right around 2 percent. In the future, I would like to use a larger dataset with more dates.

## Future Recommendations
- For future work, we recommend adding more data and features for other stocks, as well as things such as moving avreage to further enhance the model's performance and achieve even better results.

## Limitations
It is essential to acknowledge the limitations of our approach and the dataset. Some limitations include limited data, limited computing abilities.

## Acknowledgments
We would like to express our gratitude to the owner of this dataset.

![image](https://github.com/CSC380-SU23-UofArizona/final-project-cole-suddarth/assets/87513908/8560aa1f-853e-456a-9b27-0a09f06b0e13)

