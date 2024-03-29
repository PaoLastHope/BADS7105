<h1>Customer Behavior Analysis</h1>

<p align="left">
<img src="https://cdn.iconscout.com/icon/free/png-512/microsoft-excel-2-569282.png"
     width="100" height="100" ><br>
Data file : Customer Behaviors (Responses).xlsx <br>
Details   : 63 rows, 64 columns
</p>

<b>Data Checking</b>

<img width="800" src="https://github.com/PaoLastHope/BADS7105/blob/5d27ae9de85c26c39c4a902ec475effa31bfb96b/HOMEWORK%2001/images/1.PNG">

<b>Data Cleasing and Preparetion</b>

- Data contain Thai language, need to install Thai font
- Edit column text 'คุณมีความสนใจในสิ่งเหล่านี้มากน้อยเพียงใด' -> Interest 
- Edit column text 'คุณบริโภคสิ่งเหล่านี้บ่อยขนาดไหน' -> Consume
- Edit gender 'ชาย' -> 'M' and 'หญิง' -> 'F'
- New 'Age' column by calculate from birthday, also check year conversion 'พศ' -> 'คศ'
- Drop record that sex is 'ไม่ต้องการระบุ'. For more accuracy data, we should not provide this option 
 
 <p align="Left">
 <img width="300" src="https://github.com/PaoLastHope/BADS7105/blob/5d27ae9de85c26c39c4a902ec475effa31bfb96b/HOMEWORK%2001/images/2.PNG">
 <img width="300" src="https://github.com/PaoLastHope/BADS7105/blob/5d27ae9de85c26c39c4a902ec475effa31bfb96b/HOMEWORK%2001/images/3.PNG">
 </p>
 
<b>Frequency Data</b>

- Sum categorical data of each colum. Index 0-30 is Interest, Index 31-60 is Consuming. 
- Convert data into matrix form
- Using heatmap function to visualize data from matrix data
     
<img width="700" src="https://github.com/PaoLastHope/BADS7105/blob/5d27ae9de85c26c39c4a902ec475effa31bfb96b/HOMEWORK%2001/images/4.PNG">
     
- Interest Topic Frequency
- We can see how much users choose their interesting topics. Also, compare number between Male and Female 
<img width="700" src="https://github.com/PaoLastHope/BADS7105/blob/5d27ae9de85c26c39c4a902ec475effa31bfb96b/HOMEWORK%2001/images/5.png">
  
- Consume Topic Frequency
- We can see how much users choose their Consume topics. Also, compare between Male and Female
<img width="700" src="https://github.com/PaoLastHope/BADS7105/blob/5d27ae9de85c26c39c4a902ec475effa31bfb96b/HOMEWORK%2001/images/6.png">
     
<b>Correlation</b>

- Convert categorical data into scale 'ไม่สนใจอย่างมากที่สุด' -> 1, ..., 'สนใจอย่างมากที่สุด' -> 7
- Convert categorical data into scale 'แทบไม่ได้บริโภคเลย' -> 1, ..., 'แทบทุกวัน' -> 6

<img width="800" src="https://github.com/PaoLastHope/BADS7105/blob/5d27ae9de85c26c39c4a902ec475effa31bfb96b/HOMEWORK%2001/images/7.PNG">

- Total correlation mapping
- Sorting score, top 5 and bottom 5 rank
<img width="700" src="https://github.com/PaoLastHope/BADS7105/blob/5d27ae9de85c26c39c4a902ec475effa31bfb96b/HOMEWORK%2001/images/8mf.png">
<img width="500" src="https://github.com/PaoLastHope/BADS7105/blob/5d27ae9de85c26c39c4a902ec475effa31bfb96b/HOMEWORK%2001/images/11tb.PNG">

- Male correlation mapping 
- Sorting score, top 5 and bottom 5 rank
<img width="700" src="https://github.com/PaoLastHope/BADS7105/blob/5d27ae9de85c26c39c4a902ec475effa31bfb96b/HOMEWORK%2001/images/9m.png">
<img width="500" src="https://github.com/PaoLastHope/BADS7105/blob/5d27ae9de85c26c39c4a902ec475effa31bfb96b/HOMEWORK%2001/images/12tb.PNG">
     
- Female correlation mapping
- Sorting score, top 5 and bottom 5 rank
<img width="700" src="https://github.com/PaoLastHope/BADS7105/blob/5d27ae9de85c26c39c4a902ec475effa31bfb96b/HOMEWORK%2001/images/10f.png">
<img width="500" src="https://github.com/PaoLastHope/BADS7105/blob/5d27ae9de85c26c39c4a902ec475effa31bfb96b/HOMEWORK%2001/images/13tb.PNG">

<b>Interest topic analysis</b>

- Tokenize words from question of interesting column
- Do word count using WordClound, this is required to install Thai font
- From counting result, most frequency word are <b>'สัตว์เลี้ยง', 'รถยนต์', 'กีฬา', 'เทคโนโลยี' and 'ฟุตบอล'</b> 

<img src="https://github.com/PaoLastHope/BADS7105/blob/5d27ae9de85c26c39c4a902ec475effa31bfb96b/HOMEWORK%2001/images/wc1.PNG">
<img width="600" src="https://github.com/PaoLastHope/BADS7105/blob/5d27ae9de85c26c39c4a902ec475effa31bfb96b/HOMEWORK%2001/images/wcc2.png">

Reference <br/>
https://www.python-graph-gallery.com/92-control-color-in-seaborn-heatmaps<br/>
https://towardsdatascience.com/better-heatmaps-and-correlation-matrix-plots-in-python-41445d0f2bec<br/>
