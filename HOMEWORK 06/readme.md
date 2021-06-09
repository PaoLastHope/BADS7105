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

<b>Scenario</b><br/>
I need to delivery the list of customers data to marketing team and crm team.
So they can use the data to make the promotions on each customer or improve services.


Separate customer into 2 group, because one-time customer cannot do 
one-time customer ( only one transaction )
-    priori-based - segment 1
-    value-based - segment 2
-    need-based - segment 3 <br/>
note: record of transactions with no customer code will set as one-time customer
     
return customer ( more than one transactions )
-    priori-based - segment 4
-    value-based - segment 5
-    need-based - segment 6 <br/>

Final result is list of customers on each segmentation

<b>Proceed segmentation</b>
- Keep it simple
- For these scenarions, I will use google BigQuery ML and DataStudio











Reference<br/>
https://www.dunnhumby.com/source-files/<br/>
https://thanachart-rit.medium.com/upload-data-to-google-bigquery-using-google-cloud-sdk-set-up-data-environment-with-supermarket-fc144a0ce4d1<br/>
https://openviewpartners.com/blog/customer-segmentation/#.YMCXe_kzY2w<br/>
https://cloud.google.com/bigquery-ml/docs/introduction<br/>
