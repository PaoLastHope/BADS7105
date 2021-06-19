<h1>Customer Lifetime Value</h1>

<p align="left">
<img width="367" alt="1" src="https://user-images.githubusercontent.com/5312356/120929641-fb56ae00-c713-11eb-9d10-a13e69f00b15.PNG">

<b>DIRECT MARKETING TO CUSTOMERS - Let’s Get Sort-of-Real</b>

<img src="https://cdn.iconscout.com/icon/free/png-512/microsoft-excel-2-569282.png"
     width="100" height="100" ><br>
Data file : supermarket.xlsx <br>
Details   : 956,575 rows, 22 columns, 132,537 KB  ( Sample Data, not the actual)
</p>
<br/>

Prepare data
- A simple process for these scenarios using Google BigQuery ML and DataStudio
- Import data file into Google Cloud Storage 
- Connect data from Google Cloud Storage, now we can do query.

<b>Customer Lifetime Value Formulas</b>

<p align="left">
<img width="400" src="https://github.com/PaoLastHope/BADS7105/blob/7ef74a0ac9c9252dbcfebd53d5728f82b1338270/HOMEWORK%2005/images/APFR.PNG">
<img width="400" src="https://github.com/PaoLastHope/BADS7105/blob/7ef74a0ac9c9252dbcfebd53d5728f82b1338270/HOMEWORK%2005/images/apv.PNG">
<img width="400" src="https://github.com/PaoLastHope/BADS7105/blob/7ef74a0ac9c9252dbcfebd53d5728f82b1338270/HOMEWORK%2005/images/CV.PNG">
<img width="400" src="https://github.com/PaoLastHope/BADS7105/blob/7ef74a0ac9c9252dbcfebd53d5728f82b1338270/HOMEWORK%2005/images/ACL.PNG">
<img width="400" src="https://github.com/PaoLastHope/BADS7105/blob/7ef74a0ac9c9252dbcfebd53d5728f82b1338270/HOMEWORK%2005/images/CLTV.PNG">
</p>

- SQL Query in Google BigQuery to retrieve data from source
<pre>
  <code>
select 
left(shop_date,4) as shop_year,
SUM(spend) as total_spend,
count(DISTINCT basket_id) as total_basket,
count(DISTINCT CUST_CODE) as total_customer,
(SUM(spend) / count(DISTINCT basket_id)) as APV,
(SUM(spend) / count(DISTINCT CUST_CODE)) as APFR
from `my_dataset.my_market`
group by shop_year;
  </code>
</pre>

- Display Customer Lite Time Value using Google Data Studio 
- Customer code contain NULL value, this mean we need to assign customer code. To get correct couting number
- Fixed churn rate percentage with 1. This value is various depend on each customer.
<img width="700" src="https://github.com/PaoLastHope/BADS7105/blob/7138c70a044db016bfd5aba649f9e50fa1da67ad/HOMEWORK%2005/images/gds.PNG">

<h2>Dashboard</h2>
We can display the variety of data using dashboard tool
By Power BI, connect and load data from Google BigQuery
<img width="500" src="https://github.com/PaoLastHope/BADS7105/blob/958ee592cc36702270b4cda2ea6f5c2f657ee746/HOMEWORK%2005/images/bicon.PNG">

- Basket
<p align='left'>
<img width="300" src="https://github.com/PaoLastHope/BADS7105/blob/7361825da079e2b0578867801755cd1b023babf0/HOMEWORK%2005/images/bas1.PNG">
<img width="300" src="https://github.com/PaoLastHope/BADS7105/blob/7361825da079e2b0578867801755cd1b023babf0/HOMEWORK%2005/images/bas2.PNG">
<img width="300" src="https://github.com/PaoLastHope/BADS7105/blob/7361825da079e2b0578867801755cd1b023babf0/HOMEWORK%2005/images/bas3.PNG">
</p>

- Customer
<p align='left'>
<img width="300" src="https://github.com/PaoLastHope/BADS7105/blob/7361825da079e2b0578867801755cd1b023babf0/HOMEWORK%2005/images/cus1.PNG">
<img width="300" src="https://github.com/PaoLastHope/BADS7105/blob/7361825da079e2b0578867801755cd1b023babf0/HOMEWORK%2005/images/cus2.PNG">
</p>

- Product
<img width="500" src="https://github.com/PaoLastHope/BADS7105/blob/7361825da079e2b0578867801755cd1b023babf0/HOMEWORK%2005/images/prod1.PNG">

- Store
<p align='left'> 
<img width="300" src="https://github.com/PaoLastHope/BADS7105/blob/7361825da079e2b0578867801755cd1b023babf0/HOMEWORK%2005/images/sto1.PNG">
<img width="300" src="https://github.com/PaoLastHope/BADS7105/blob/7361825da079e2b0578867801755cd1b023babf0/HOMEWORK%2005/images/sto2.PNG">
<img width="300" src="https://github.com/PaoLastHope/BADS7105/blob/7361825da079e2b0578867801755cd1b023babf0/HOMEWORK%2005/images/sto3.PNG">
</p>

- Transaction
<img width="500" src="https://github.com/PaoLastHope/BADS7105/blob/7361825da079e2b0578867801755cd1b023babf0/HOMEWORK%2005/images/tran1.PNG">
<img width="500" src="https://github.com/PaoLastHope/BADS7105/blob/7361825da079e2b0578867801755cd1b023babf0/HOMEWORK%2005/images/tran2.PNG">
     
Reference<br/>
https://www.dunnhumby.com/source-files/<br/>
https://cloud.google.com/bigquery/docs/sandbox<br/>
https://thanachart-rit.medium.com/upload-data-to-google-bigquery-using-google-cloud-sdk-set-up-data-environment-with-supermarket-fc144a0ce4d1<br/>
https://blog.hubspot.com/service/how-to-calculate-customer-lifetime-value<br/>
https://www.zaius.com/customer-lifetime-value-cltv/<br/>
