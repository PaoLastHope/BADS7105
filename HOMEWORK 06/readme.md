<h1>Customer Segmentation</h1>



<b>Data Sources</b>
<p align="left">
<img width="367" alt="1" src="https://user-images.githubusercontent.com/5312356/120929641-fb56ae00-c713-11eb-9d10-a13e69f00b15.PNG">

<b>DIRECT MARKETING TO CUSTOMERS - Let’s Get Sort-of-Real</b>

<img src="https://cdn.iconscout.com/icon/free/png-512/microsoft-excel-2-569282.png"
     width="100" height="100" ><br>
Data file : supermarket.xlsx <br>
Details   : 956,575 rows, 22 columns, 132,537 KB  ( Sample Data, not the actual)
</p>
<br>

<h2>Scenario</h2>

<img width='500' src="https://github.com/PaoLastHope/BADS7105/blob/d8c8a67e04efdfdc407e836617d0a2e48f659ef0/HOMEWORK%2006/images/sce.PNG">

I need to delivery the list of customers data to marketing team and crm team.<br/>
So they can use the data to make the promotions on each customer or improve services.

<img width='500' src="https://github.com/PaoLastHope/BADS7105/blob/d8c8a67e04efdfdc407e836617d0a2e48f659ef0/HOMEWORK%2006/images/seg.PNG">

Separate customer into 2 group, because one-time customer cannot do 

<b>one-time customer</b> ( only one transaction )
-    priori-based - segment 1
-    value-based - segment 2
-    need-based - segment 3 <br/>
<b>Note: record of transactions with no customer code will set as one-time customer</b>
     
<b>return customer</b> ( more than one transactions )
-    priori-based - segment 4
-    value-based - segment 5
-    need-based - segment 6 <br/>

Final result is list of customers on each segmentation

<h2>Proceed segmentation</h2><br/>

Select group of clustering
- Using K-means algorithm, so it's need to set the right value of k
- Using <b>simple_kmean</b> program to desire k-mean value 

comparing one-time customer distribution
<pre><code>
SELECT
  CUST_CODE,
  SUM(SPEND) AS TOTAL_SALES,
  COUNT(DISTINCT BASKET_ID) AS TOTAL_VISIT
FROM
  `apiwats-project.my_dataset.my_market`
WHERE
  CUST_CODE IS NOT NULL
GROUP BY
  CUST_CODe
HAVING
  total_visit = 1
UNION ALL
SELECT
  NULL AS cust_code,
  SUM(SPEND) AS TOTAL_SALES,
  COUNT(BASKET_ID) AS TOTAL_VISIT
FROM
  `my_dataset.my_market`
WHERE
  cust_code IS NULL
GROUP BY
  basket_id
</pre></code>

comparing return customer distribution
<pre><code>
SELECT
  CUST_CODE,
  SUM(SPEND) AS TOTAL_SALES,
  COUNT(DISTINCT BASKET_ID) AS TOTAL_VISIT
FROM
  `apiwats-project.my_dataset.my_market`
WHERE
  CUST_CODE IS NOT NULL
GROUP BY
  CUST_CODe
HAVING
  TOTAL_VISIT > 1
ORDER BY
  cust_code;
</pre></code>

Prepare data
- A simple process for these scenarios using Google BigQuery ML and DataStudio
- Import data file into Google Cloud Storage 
- Proceed query in Google BigQuery by connect data from Google CLoud Storage



Reference<br/>
https://www.dunnhumby.com/source-files/<br/>
https://thanachart-rit.medium.com/upload-data-to-google-bigquery-using-google-cloud-sdk-set-up-data-environment-with-supermarket-fc144a0ce4d1<br/>
https://openviewpartners.com/blog/customer-segmentation/#.YMCXe_kzY2w<br/>
https://cloud.google.com/bigquery-ml/docs/introduction<br/>
https://towardsdatascience.com/how-to-use-k-means-clustering-in-bigquery-ml-to-understand-and-describe-your-data-better-c972c6f5733b<br/>
