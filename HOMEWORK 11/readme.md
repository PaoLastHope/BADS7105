<h1>Voice of customer analysis</h1>

<p align="left">
<img src="https://cdn.iconscout.com/icon/free/png-512/microsoft-excel-2-569282.png"
     width="100" height="100" >
Data file : CustomerReviews.csv
</p>

<h2>Data Checking...</h2>
<p align="left">
<img src="https://github.com/PaoLastHope/BADS7105/blob/80d88a767b704e97dc27f3a91f350d96a3d3aa71/HOMEWORK%2011/images/1.PNG">
</p>
<br />
<h2>Data Overview</h2>

<p align="left">
<img src="https://github.com/PaoLastHope/BADS7105/blob/a2ddf1449b370707ed6baa9082d5ebce16174d4d/HOMEWORK%2011/images/over.PNG">
</p>

<h2>Word Count</h2>
<img width="369" alt="8" src="https://user-images.githubusercontent.com/5312356/121017953-0f5be780-c7c8-11eb-93b1-86da47fe472d.PNG">
- Most word that customer talking about are <b>น้ำ, ทาน, กิน, อร่อย, ดี</b>

<h2>Topic Modeling</h2>
- Using pyldavis and gensim API to display <br/>
- Always update API because pyldavi is not official API, some code maybe errors<br/>
- Using customize Tokenizer class for more accurately tokenize of words, using all api dictionary
- Always normalize word if spelling wrong all wrong position of char, also remove special symbol or charactors
- Fix thai dictionay by adding additional words such as 'เบาๆ', 'เทมปุระ', 'เนื้อออส' ...
- Fix thai dictionay by adding location or shop name such as 'โมโม่','เดอะมอลล์', 'ยูเนี่ยนมอลล์' ...

Evaluate Coherance score of number for topics 1-10

Diplay Topics 
- After running model 2-6 topics, I choose 4 topics becuase the blue bubble is clearly separation
- The result of topic may not totally make sense
- To fixed new meaning word or slang or worng spelling is difficult task

<h2>Text to Emotion</h2>
- Using Text2emotion to calculate emotional score from words. But this require to be english text. (Currently, no thai API)<br/>
- PyThaiNLP already provide translation from thai to english. But for global use, we should apply with official API<br/>
- The result may not correctly right, because we're dealing with technology of computer and human's feeling<br/>

<img src="https://github.com/PaoLastHope/BADS7105/blob/751da4bed48fe21774c449cd839949f181606db1/HOMEWORK%2011/images/9.PNG">

<img src="https://github.com/PaoLastHope/BADS7105/blob/751da4bed48fe21774c449cd839949f181606db1/HOMEWORK%2011/images/10.PNG">

Reference<br/>
https://github.com/PyThaiNLP/pythainlp
https://towardsdatascience.com/text2emotion-python-package-to-detect-emotions-from-textual-data-b2e7b7ce1153<br/>
https://hackernoon.com/how-to-perform-emotion-detection-in-text-via-python-lk383tsu<br/>
https://www.machinelearningplus.com/nlp/topic-modeling-gensim-python/
https://towardsdatascience.com/end-to-end-topic-modeling-in-python-latent-dirichlet-allocation-lda-35ce4ed6b3e0
https://cloud.google.com/translate/docs/basic/translating-text#translate_translate_text-python
