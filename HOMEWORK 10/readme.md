<h1>Customer Movement Analysis</h1>

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

<b>Logic</b>
- Retrieve customer data only customer with code, otherwise we cannot track the customer(not get null).
- Count the number of customer in each period of week (7 days)
- Compare customer apperance from last period using SQL function LAG()
- Set status of customer. Not found -> New customer
- Set status of customer. Less than 7 days -> Repeat customer
- Set status of customer. More than 7 days -> Return customer
- Compare Repeat customer againg with another periods. Not found -> Churn customer
- Explore result with Google Data Studio

SQL Query to calculate customer movement
<pre>
<code>
SELECT
  CUR_W AS WEEK,
  NEW_CUST,
  REPEAT_CUST,
  RETURN_CUST,
  REPEAT_CUST - LAG(TOT_C, 1) OVER(ORDER BY CUR_W) AS CHURN_CUST
FROM (
  SELECT
    CUR_w,
    COUNT(CASE
        WHEN STATUS = 'NEW' THEN CC
      ELSE
      NULL
    END
      ) AS NEW_CUST,
    COUNT(CASE
        WHEN STATUS = 'REP' THEN CC
      ELSE
      NULL
    END
      ) AS REPEAT_CUST,
    COUNT(CASE
        WHEN STATUS = 'RET' THEN CC
      ELSE
      NULL
    END
      ) AS RETURN_CUST,
    COUNT(CC) AS TOT_C
  FROM (
    SELECT
      PRE_W,
      CUR_W,
      CC,
      CASE
        WHEN DATE_DIFF(CUR_W, PRE_W, DAY) IS NULL THEN 'NEW'
        WHEN DATE_DIFF(CUR_W, PRE_W, DAY) <= 7 THEN 'REP'
        WHEN DATE_DIFF(CUR_W, PRE_W, DAY) > 7 THEN 'RET'
      ELSE
      NULL
    END
      AS STATUS
    FROM (
      SELECT
        LAG(CUR_W, 1)OVER(PARTITION BY CC ORDER BY CUR_W) AS PRE_W,
        CUR_W,
        CC
      FROM (
        SELECT
          DISTINCT DATE_TRUNC(PARSE_DATE('%Y%m%d',
              SHOP_DATE), WEEK) AS CUR_W,
          CUST_CODE AS CC
        FROM
          `apiwats-project.my_dataset.my_market`
        WHERE
          CUST_CODE IS NOT NULL)))
  GROUP BY
    CUR_W)
ORDER BY
  WEEK ASC;
</code>
</pre>

<h2>Display using Google Data Studio</h2>
Compare the number between each status of customer in period of week.

<img src="https://github.com/PaoLastHope/BADS7105/blob/84f3463117404556d6771e26ed7b785904bd62d1/HOMEWORK%2010/images/churn1.PNG">
<img src="https://github.com/PaoLastHope/BADS7105/blob/84f3463117404556d6771e26ed7b785904bd62d1/HOMEWORK%2010/images/churn2.PNG">
<img width="500" src="https://github.com/PaoLastHope/BADS7105/blob/84f3463117404556d6771e26ed7b785904bd62d1/HOMEWORK%2010/images/churn3.PNG">

Reference<br/>
https://www.dunnhumby.com/source-files/<br/>
https://thanachart-rit.medium.com/upload-data-to-google-bigquery-using-google-cloud-sdk-set-up-data-environment-with-supermarket-fc144a0ce4d1
