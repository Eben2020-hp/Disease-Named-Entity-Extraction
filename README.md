# Disease Named Entity Extraction


## **Introduction**

<p>
Named Entity Extraction (NER) is a sub-task of Information Extraction, which deals with finding and classifying named entities (a real-world object, such as a person, location, organization, product, etc., that can be denoted with a proper name) that are mentioned in an unstructured text into pre-defined categories such as person names, organizations, medical codes, etc. 
</p>

<img src="https://miro.medium.com/max/1400/1*0BuSAIQOLNQGVWJIxZhFuA.png" width= 1250 height= 450>

### **Named Entity Recognition Packages**

<p>
NER can be implemented with either statistical or rule-based methods, both of which require a large amount of labeled training data and are typically trained in a fully or semi-supervised manner. Statistical approaches to NER include Hidden Markov Models, Maximum Entropy, and Conditional Random Fields, as well as deep learning approaches with Recurrent Neural Networks, such as Seq2Seq. All of these processes involve sentence inputs and annotated sentence outputs. Many of these processes also involve additional feature engineering, providing as input summary statistics of the sentences.
</p>

### **Named Entity Recognition Evaluation Metrics**

<p>
NER is most commonly evaluated with Precision, Recall, and F1-score. F1-score can either be relaxed or strict, with the latter requiring the character offsets to match exactly.
</p>

### **Named Entity Recognition with SpaCy**

<p>
SpaCy is an open-source python library for NLP written in Python and Cython. It offers pre-trained models for multi-language NER, as well as allowing developers to train and deploy custom NER models on domain specific corpuses. SpaCy models are designed to be production-ready.
</p>

**_SpaCy's pretrained models are trained on the OntoNotes 5 corpus, and support the identification of the following entities:_**

<table>
<thead>
<tr><th>TYPE</th><th>DESCRIPTION</th></tr>
</thead>
<tbody>
<tr><td>PERSON</td><td>People, including fictional</td></tr>
<tr><td>NORP</td><td>Nationalities or religious or political groups</td></tr>
<tr><td>FAC</td><td>Buildings, airports, highways, bridges, etc</td></tr>
<tr><td>ORG</td><td>Companies, agencies, institutions, etc</td></tr>
<tr><td>GPE</td><td>Countries, cities, states</td></tr>
<tr><td>LOC</td><td>Non-GPE locations, mountain ranges, bodies of water</td></tr>
<tr><td>PRODUCT</td><td>Objects, vehicles, foods, etc. (Not services.)</td></tr>
<tr><td>EVENT</td><td>Named hurricanes, battles, wars, sports events, etc</td></tr>
<tr><td>WORK_OF_ART</td><td>Titles of books, songs, etc</td></tr>
<tr><td>LAW</td><td>Named documents made into laws</td></tr>
<tr><td>LANGUAGE</td><td>Any named language</td></tr>
<tr><td>DATE</td><td>Absolute or relative dates or periods</td></tr>
<tr><td>TIME</td><td>Times smaller than a day</td></tr>
<tr><td>PERCENT</td><td>Percentage, including ”%“</td></tr>
<tr><td>MONEY</td><td>Monetary values, including unit</td></tr>
<tr><td>QUANTITY</td><td>Measurements, as of weight or distance</td></tr>
<tr><td>ORDINAL</td><td>“first”, “second”, etc</td></tr>
<tr><td>CARDINAL</td><td>Numerals that do not fall under another type</td></tr>
</tbody>
</table>



## **Task at Hand**


<p>
This Jupyter notebook demonstrates Training and Serving Custom Named Entity Recognition (NER) models, which are used to identify named entities such as disease names from clinical narratives/documents in order to support clinical and translational research. NER is used in a number of business applications such as powering recommender systems, simplifying customer support, and optimizing internal search engines.
</p>

Here I will be creating a Clinical Named Entity Recognition model which can recognize the Disease Names from Clinical Text.

For this I have extracted annotated clinical text from the following github repo: https://github.com/dmis-lab/biobert.

- They provide annotated clinical text here: Named Entity Recognition: (17.3 MB), 8 datasets on Biomedical Named Entity Recognition (https://drive.google.com/open?id=1OletxmPYNkz2ltOr9pyT0b0iBtUWxslh).

- Once we download and unzip the files we get 8 Datasets with each dataset having the following files: 

   - train.tsv
   - test.tsv
   - dev.tsv
   - devel.tsv 

**In these .tsv files each word is annotated using the BIO format.**

| Annotations | Entity Type |
| --- | --- |
| B | Begin Entity |
| I | Inside Entity |
| O | Outside Entity |


***This notebook has been inpsired from :***
- https://aihub.cloud.google.com/p/products%2F2290fc65-0041-4c87-a898-0289f59aa8ba
- https://youtu.be/DxLcMI-EMYI


## Model Evaluation Scores
<img align='center' src="https://user-images.githubusercontent.com/66016994/137597878-6980e07d-c1f1-4972-a34d-06f567459d8b.png">


