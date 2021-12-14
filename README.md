# TimeSeriesForecasting 
## Full consumption forecast

My client's goal was Full consumption forecast.
I got folders with log files from power devices and develop script for dataset preparing. Then I made Exploratory Data Analysis (also check seasonity, stationarity, decompose, etc.), finde SARIMA model, made regression+SARIMA forecast and made decision use LSTM model for speed and streaming forecasting.

The training took place on the observation segment until 20.08, the prediction on the segment from 20.08, where the data were sampled on average every 30 minutes. Training and prediction were carried out according to the daily observation window. At the same time, even though the 20-23 day spike did not get into the training segment, this spike was predicted on the test.

Suggested optimization methods:
1. encode the outliers separately, taking into account that in high-frequency data, the "outlier” can last for several observations.
2. aggregation using calendar information (processing data on holidays, weekends in a specific territory, leap year corrections, etc.)
3. take into account the temperature outside, sunny/cloudy, geolocation, type of consumer and find cause-and-effect relationships with other indicators and take them into account
4. Make a forecast using BiLSTM
