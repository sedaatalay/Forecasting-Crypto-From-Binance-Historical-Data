# Forecasting-Crypto-From-Binance-Historical-Data

This Project is Forecastor Project Which PreProcess all Historical Binance Dataset and Create Forecast Models with 25 Algorithm
BTC-EUR Forecast Table Forecast vs Real
image

Example Inference
python inference_one.py --df <Path to Parquet File> \
                        --model <Path to Trained Model> \
                        --forecast_range_min <Forecast Range in Mintes> \
                        --num_of_lag <Number of Lags which trained in Model>

python inference_one.py --df BTC_EUR.parquet --model rf_model.pkl --forecast_range_min 30 --num_of_lag 10
Models List:
Models Shortcut	Model Name
lr	Linear Regression
lasso	Lasso Regression
ridge	Ridge Regression
en	Elastic Net
lar	Least Angle Regression
llar	Lasso Least Angle Regression
omp	Orthogonal Matching Pursuit
br	Bayesian Ridge
ard	Automatic Relevance Determination
par	Passive Aggressive Regressor
ransac	Random Sample Consensus
tr	TheilSen Regressor
huber	Huber Regressor
kr	Kernel Ridge
svm	Support Vector Regression
knn	K Neighbours Regressor
dt	Decisiopn Tree Regressor
rf	Random Forest Regressor
et	Extra Trees Regressor
ada	AdaBoost Regressor
gbr	Gradient Boosting Regressor
mlp	MLP Regressor
xgboost	Extreme Gradient Boosting
lightgbm	Light Gradient Boosting Machine
catboost	CatBoost Regressor
About Dataset
Introduction
This is a collection of 1 minute candlesticks of the top 1000 cryptocurrency pairs on Binance.com. In total there are 1971, but Kaggle limits file count to 1000. Both retrieval and uploading the data is fully automated—see this GitHub repo.

Content
For every trading pair, the following fields from Binance's official API endpoint for historical candlestick data are saved into a Parquet file:

 #   Column                        Dtype         
---  ------                        -----         
 0   open_time                     datetime64[ns]
 1   open                          float32       
 2   high                          float32       
 3   low                           float32       
 4   close                         float32       
 5   volume                        float32       
 6   quote_asset_volume            float32       
 7   number_of_trades              uint16        
 8   taker_buy_base_asset_volume   float32       
 9   taker_buy_quote_asset_volume  float32       
dtypes: datetime64[ns](1), float32(8), uint16(1)
The dataframe is indexed by open_time and sorted from oldest to newest. The first row starts at the first timestamp available on the exchange, which is July 2017 for the longest running pairs.

Here are two simple plots based on a single file; one of the opening price with an added indicator (MA50) and one of the volume and number of trades:


Inspiration
One obvious use-case for this data could be technical analysis by adding indicators such as moving averages, MACD, RSI, etc. Other approaches could include backtesting trading algorithms or computing arbitrage potential with other exchanges.

License
This data is being collected automatically from crypto exchange Binance.

🥏 Kaggle Dataset Link: https://www.kaggle.com/datasets/jorijnsmit/binance-full-history

You can check tutorial from BigDataProject.ipynb.
