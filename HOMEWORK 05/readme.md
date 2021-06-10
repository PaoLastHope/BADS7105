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

<b>Customer Value</b> 


<h2>Dashboard Power BI</h2>


Reference<br/>
https://www.dunnhumby.com/source-files/<br/>
https://cloud.google.com/bigquery/docs/sandbox
https://thanachart-rit.medium.com/upload-data-to-google-bigquery-using-google-cloud-sdk-set-up-data-environment-with-supermarket-fc144a0ce4d1
https://blog.hubspot.com/service/how-to-calculate-customer-lifetime-value
https://www.zaius.com/customer-lifetime-value-cltv/
