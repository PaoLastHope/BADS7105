<h1>Campaign Response Model</h1>

<p align="left">
<img src="https://cdn.iconscout.com/icon/free/png-512/microsoft-excel-2-569282.png"
     width="100" height="100" ><br/>
Data file : Retail_Data_Response.csv <br/>
Details   : 6885 rows, 2 columns

Data file : Retail_Data_Transactions.csv <br/>
Details   : 125001 rows, 3 columns
</p>

<b>Data Checking</b>

<img widte="450" src="https://github.com/PaoLastHope/BADS7105/blob/4440ebe452a82ef378454d4d71c1d712c3bb99ed/HOMEWORK%2008/images/1.PNG">
<img widte="450" src="https://github.com/PaoLastHope/BADS7105/blob/4440ebe452a82ef378454d4d71c1d712c3bb99ed/HOMEWORK%2008/images/2.PNG">

<b>Data Preparetion</b>

- Calculate value of recency, frequency, monetary_value, AOU andticket_size
- Perform data imbalance with SMOTE 

<img widte="450" src="https://github.com/PaoLastHope/BADS7105/blob/4440ebe452a82ef378454d4d71c1d712c3bb99ed/HOMEWORK%2008/images/3.PNG">

<b>Visualization</b>

<img widte="450" src="https://github.com/PaoLastHope/BADS7105/blob/4440ebe452a82ef378454d4d71c1d712c3bb99ed/HOMEWORK%2008/images/4.PNG">
<img widte="450" src="https://github.com/PaoLastHope/BADS7105/blob/4440ebe452a82ef378454d4d71c1d712c3bb99ed/HOMEWORK%2008/images/5.PNG">
<img widte="450" src="https://github.com/PaoLastHope/BADS7105/blob/4440ebe452a82ef378454d4d71c1d712c3bb99ed/HOMEWORK%2008/images/6.PNG">

<b>Process ML - SVM </b>

- Running with SVM RFM
<img src="https://github.com/PaoLastHope/BADS7105/blob/4440ebe452a82ef378454d4d71c1d712c3bb99ed/HOMEWORK%2008/images/svm1.PNG">

- Running with SVM CLV
<img src="https://github.com/PaoLastHope/BADS7105/blob/4440ebe452a82ef378454d4d71c1d712c3bb99ed/HOMEWORK%2008/images/svm2.PNG">

<b>Process ML - Logistic Regression with RMF and CLV</b>

- Running with LR RFM
<img src="https://github.com/PaoLastHope/BADS7105/blob/4440ebe452a82ef378454d4d71c1d712c3bb99ed/HOMEWORK%2008/images/log1.PNG">
- Running with LR CLV
<img src="https://github.com/PaoLastHope/BADS7105/blob/4440ebe452a82ef378454d4d71c1d712c3bb99ed/HOMEWORK%2008/images/log2.PNG">

<b>Process ML - XGBoost with RMF and CLV</b>

- Running with XGBoost RFM
- Running with XGBoost CLV
- Running with XGBoost Tuning

<img src="https://github.com/PaoLastHope/BADS7105/blob/4440ebe452a82ef378454d4d71c1d712c3bb99ed/HOMEWORK%2008/images/xg1.PNG">
<img src="https://github.com/PaoLastHope/BADS7105/blob/4440ebe452a82ef378454d4d71c1d712c3bb99ed/HOMEWORK%2008/images/xg2.PNG">
<img src="https://github.com/PaoLastHope/BADS7105/blob/4440ebe452a82ef378454d4d71c1d712c3bb99ed/HOMEWORK%2008/images/xg3.PNG">

<b>Best Model</b>

<img src="https://github.com/PaoLastHope/BADS7105/blob/4440ebe452a82ef378454d4d71c1d712c3bb99ed/HOMEWORK%2008/images/7.PNG">




Reference
<p align="left">
<img width="200" alt="1" src="https://upload.wikimedia.org/wikipedia/commons/7/7c/Kaggle_logo.png">
</p>
https://www.kaggle.com/regivm/retailtransactiondata <br/>
https://www.datacamp.com/community/tutorials/svm-classification-scikit-learn-python <br/>
https://towardsdatascience.com/building-a-logistic-regression-in-python-step-by-step-becd4d56c9c8<br/>
https://www.datacamp.com/community/tutorials/xgboost-in-python
