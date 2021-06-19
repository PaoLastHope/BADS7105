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
<br/>

Prepare data
- A simple process for these scenarios using Google BigQuery ML and DataStudio
- Import data file into Google Cloud Storage 
- Connect data from Google Cloud Storage, now we can do query.

<h2>Scenario</h2>

<img width='500' src="https://github.com/PaoLastHope/BADS7105/blob/d8c8a67e04efdfdc407e836617d0a2e48f659ef0/HOMEWORK%2006/images/sce.PNG">

I need to delivery the list of customers data to marketing team and crm team.<br/>
So they can use the data to make the promotions on each customer or improve services.<br/>
To learn characteristics of a product group.
To learn how to reduce cannibalization or improve cross-selling.

<img width='500' src="https://github.com/PaoLastHope/BADS7105/blob/d8c8a67e04efdfdc407e836617d0a2e48f659ef0/HOMEWORK%2006/images/seg.PNG">

<h2>Process</h2><br/>

<b>Separate customer into 2 groups</b><br/>
one-time customer - only one transaction<br/>
return customer - more than one transaction<br/>
<b>Note: record of transactions with no customer code will set as one-time customer(basket id per customer)</b>

Query to retrieve one-time customer ( result = 27,052 )
<pre><code>
SELECT
  CUST_CODE,
  SUM(SPEND) AS TOTAL_SALES,
  COUNT(DISTINCT BASKET_ID) AS TOTAL_VISIT
FROM `apiwats-project.my_dataset.my_market`
WHERE CUST_CODE IS NOT NULL
GROUP BY CUST_CODe
HAVING TOTAL_VISIT = 1
UNION ALL
SELECT
  NULL AS CUST_CODE,
  SUM(SPEND) AS TOTAL_SALES,
  COUNT(DISTINCT BASKET_ID) AS TOTAL_VISIT
FROM `apiwats-project.my_dataset.my_market`
WHERE CUST_CODE IS NULL
GROUP BY BASKET_ID;
</pre></code>

Query to retrieve return customer ( result = 4,075)
<pre><code>
SELECT
  CUST_CODE,
  SUM(SPEND) AS TOTAL_SALES,
  COUNT(DISTINCT BASKET_ID) AS TOTAL_VISIT
FROM `apiwats-project.my_dataset.my_market`
WHERE CUST_CODE IS NOT NULL
GROUP BY CUST_CODE
HAVING TOTAL_VISIT > 1
ORDER BY CUST_CODE;
</pre></code>

Select group of clustering
- Using K-means algorithm on Google BigQuery ML, so it's need to set the right value of k (number of clustering)
- Using <b>simple_kmean</b> program to desire k-mean value 

<b>Comparing one-time customer</b><br/>
First, about null customer code, we can assign running number for each bastker id

<img width='500' src="https://github.com/PaoLastHope/BADS7105/blob/00584dd9b4ee1b33cc20068174ea494a1811a7dd/HOMEWORK%2006/images/1-4.PNG">

Choosing K number for one-time customer ...

<img width='500' src="https://github.com/PaoLastHope/BADS7105/blob/2f6001500cb4ccbe581511b4a93d67d14eb90f6f/HOMEWORK%2006/images/1-1.PNG">
<img width='500' src="https://github.com/PaoLastHope/BADS7105/blob/00584dd9b4ee1b33cc20068174ea494a1811a7dd/HOMEWORK%2006/images/1-2.PNG">
<img width='500' src="https://github.com/PaoLastHope/BADS7105/blob/00584dd9b4ee1b33cc20068174ea494a1811a7dd/HOMEWORK%2006/images/1-3.PNG">
<img src="https://github.com/PaoLastHope/BADS7105/blob/00584dd9b4ee1b33cc20068174ea494a1811a7dd/HOMEWORK%2006/images/11-1.PNG">

Since one-time customer mean they only visit = 1, so we can compare only basket's value <br/>
Starting compare at k=2 to 4, we can see that k=4 the clustering start overapping. So <b>k=3</b> is the right one. 

<b>Comparing return customer distribution</b>

Choosing K number for return customer ...

<img width='500' src="https://github.com/PaoLastHope/BADS7105/blob/2f6001500cb4ccbe581511b4a93d67d14eb90f6f/HOMEWORK%2006/images/2-1.PNG">
<img width='500' src="https://github.com/PaoLastHope/BADS7105/blob/00584dd9b4ee1b33cc20068174ea494a1811a7dd/HOMEWORK%2006/images/2-2.PNG">
<img width='500' src="https://github.com/PaoLastHope/BADS7105/blob/00584dd9b4ee1b33cc20068174ea494a1811a7dd/HOMEWORK%2006/images/2-3.PNG">
<img src="https://github.com/PaoLastHope/BADS7105/blob/00584dd9b4ee1b33cc20068174ea494a1811a7dd/HOMEWORK%2006/images/22-1.PNG">
<img src="https://github.com/PaoLastHope/BADS7105/blob/00584dd9b4ee1b33cc20068174ea494a1811a7dd/HOMEWORK%2006/images/22-2.PNG">

For roughly choosing, we can choose k = 4. At this point, we can see most customers are cleary clustering <br/>
For K = 8, cluster 0 1 start overlapping. Then, recommend to choose <b>k = 7</b> for deeply focusing on customer's visit or value. <br/>
Also, technically, we can grouping back to k = 4 

Finally, we can export the list of customers which according to the group of segmentation for the teams.

For further customer segmentation, we can analyze in the way such as 
- Priori based
- Value based
- Needed based

Reference<br/>
https://www.dunnhumby.com/source-files/<br/>
https://thanachart-rit.medium.com/upload-data-to-google-bigquery-using-google-cloud-sdk-set-up-data-environment-with-supermarket-fc144a0ce4d1<br/>
https://openviewpartners.com/blog/customer-segmentation/#.YMCXe_kzY2w<br/>
https://cloud.google.com/bigquery-ml/docs/introduction<br/>
https://towardsdatascience.com/how-to-use-k-means-clustering-in-bigquery-ml-to-understand-and-describe-your-data-better-c972c6f5733b<br/>
