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

<h2>Topic Modeling</h2>

- Using pyldavis and gensim API to visualize possible topics from words<br/>
- Always update API, because pyldavi is not official API, some part of code maybe errors.
- Using <b>customize Tokenizer class</b> for more accurately tokenize of words, using all api dictionary.
- Always <b>normalize word</b> if spelling wrong all wrong position of char, also remove special symbol or charactors.
- Fix thai dictionary by add additional words and places from external files, so we can update more words later.
<img src="https://github.com/PaoLastHope/BADS7105/blob/8b87a45986a620b67abd8c243162fddaced08c47/HOMEWORK%2011/images/add1.PNG">
<img src="https://github.com/PaoLastHope/BADS7105/blob/8b87a45986a620b67abd8c243162fddaced08c47/HOMEWORK%2011/images/add2.PNG">

<b>Evaluate Coherance score of number for topics </b>

<img width="500" src="https://github.com/PaoLastHope/BADS7105/blob/9dc4a59c9134e8dcc597744b0c8397cceb2016a6/HOMEWORK%2011/images/co.PNG">
<img width="500" src="https://github.com/PaoLastHope/BADS7105/blob/fdc30fb1b6d1071140c96f1ab204da67b0bfd1bc/HOMEWORK%2011/images/score.PNG">

<b>Diplay Topics </b>

<p align="left">
<img width="450" src="https://github.com/PaoLastHope/BADS7105/blob/9dc4a59c9134e8dcc597744b0c8397cceb2016a6/HOMEWORK%2011/images/t1.PNG">
<img width="450" src="https://github.com/PaoLastHope/BADS7105/blob/9dc4a59c9134e8dcc597744b0c8397cceb2016a6/HOMEWORK%2011/images/t2.PNG">
<img width="450" src="https://github.com/PaoLastHope/BADS7105/blob/9dc4a59c9134e8dcc597744b0c8397cceb2016a6/HOMEWORK%2011/images/t3.PNG">
<img width="450" src="https://github.com/PaoLastHope/BADS7105/blob/9dc4a59c9134e8dcc597744b0c8397cceb2016a6/HOMEWORK%2011/images/t4.PNG">
</p>

- After running model 2-6 topics, I choose 4 topics becuase the blue bubble is clearly separation
- Topic 1 seem about <b>good taste or likely taste</b>
- Topic 2 seem about <b>what food they are eating</b>
- Topic 3 seem about <b>price of eating</b>
- Topic 4 seem about <b>choosing branch or place</b>
- The result of topic may not totally make sense, need to fine-tuning model and parameters
- To fixed new meaning words,slang, wrong spelling are difficult tasks

<h2>Word Count</h2>
<img src="https://github.com/PaoLastHope/BADS7105/blob/9dc4a59c9134e8dcc597744b0c8397cceb2016a6/HOMEWORK%2011/images/wc.PNG">
- Using Wordcloud, need to install thaifont
- Most word that customers typing are <b>น้ำ, ทาน, กิน, อร่อย, เลือก</b>

<h2>Text to Emotion</h2>
- Using Text2emotion to calculate emotional score from words. But this require to be english text. (Currently, no thai API)<br/>
- PyThaiNLP already provide translation from thai to english. But for global use, we should apply with official API<br/>
- Some part of the result may not feel make sense, because we're dealing with computer's language and human's feeling<br/>

<img src="https://github.com/PaoLastHope/BADS7105/blob/751da4bed48fe21774c449cd839949f181606db1/HOMEWORK%2011/images/9.PNG">

<img src="https://github.com/PaoLastHope/BADS7105/blob/751da4bed48fe21774c449cd839949f181606db1/HOMEWORK%2011/images/10.PNG">

Reference<br/>
https://github.com/PyThaiNLP/pythainlp
https://towardsdatascience.com/text2emotion-python-package-to-detect-emotions-from-textual-data-b2e7b7ce1153<br/>
https://hackernoon.com/how-to-perform-emotion-detection-in-text-via-python-lk383tsu<br/>
https://www.machinelearningplus.com/nlp/topic-modeling-gensim-python/<br/>
https://towardsdatascience.com/end-to-end-topic-modeling-in-python-latent-dirichlet-allocation-lda-35ce4ed6b3e0<br/>
https://cloud.google.com/translate/docs/basic/translating-text#translate_translate_text-python<br/>
https://gist.github.com/korakot/9d7f5db632351dc92607fdec72a4953f<br/>
