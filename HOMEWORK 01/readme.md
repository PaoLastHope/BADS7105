<h1>Customer Behavior Analysis</h1>

<p align="left">
<img src="https://cdn.iconscout.com/icon/free/png-512/microsoft-excel-2-569282.png"
     width="100" height="100" ><br>
Data file : Customer Behaviors (Responses).xlsx <br>
Details   : 63 rows, 64 columns
</p>

<b>Data Checking</b>

<img src="">
<b>Data Cleasing and Preparetion</b>

- Data contain Thai language, need to install Thai font
- Edit column text 'คุณมีความสนใจในสิ่งเหล่านี้มากน้อยเพียงใด' -> Interest 
- Edit column text 'คุณบริโภคสิ่งเหล่านี้บ่อยขนาดไหน' -> Consume
- Edit gender 'ชาย' -> 'M' and 'หญิง' -> 'F'
- New 'Age' column by calculate from birthday, also check year conversion 'พศ' -> 'คศ'
- Drop record that sex is 'ไม่ต้องการระบุ'. For more accuracy data, we should not provide this option 
 
<b>Frequency plot of Interesting</b>

- Sum categorical data of each column(index 0-30), then convert data into matrix form
- Using heatmap function to visualize matrix data

<b>Frequency plot of Consume</b>

- Sum categorical data of each column(index 30-60), then convert data into matrix form
- Using heatmap function to visualize matrix data


<b>Correlation of Interesting</b>

- Convert categorical data into scale 'ไม่สนใจอย่างมากที่สุด' -> 1, ..., 'สนใจอย่างมากที่สุด' -> 7
- 

<b>Correlation of Consume</b>

- Convert categorical data into scale 'แทบไม่ได้บริโภคเลย' -> 1, ..., 'แทบทุกวัน' -> 6

<b>Interest topic analysis</b>

- Tokenize words from question of interesting column
- Do word count using WordClound, this is required to install Thai font



- From counting result, most frequency word are <b>สัตว์เลี้ยง, รถยนต์, กีฬา, เทคโนโลยี and ฟุตบอล</b> 

Reference
