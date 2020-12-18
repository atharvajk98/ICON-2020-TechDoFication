# Technical-Domain-Identification
* The repository contains team SPPU_AKAH's submission for ICON 2020 TechDOfication Shared Task (Subtask-1f). We propose a hybrid Attention Ensemble BiLSTM-CNN model for the task of coarse-grained automatic technical domain identification of short texts in the Marathi Language. Our system resulted in the best submission for the subtask-1f.
* Link to ICON 2020 conference website (https://www.iitp.ac.in/~ai-nlp-ml/icon2020/index.html).
* Link to the Shared Task website (https://ssmt.iiit.ac.in/techdofication.html).

# The Dataset:
* The Subtask-1f dataset consisted of 4 labels namely: Bio-Chemistry (bioche), Communication Technology (com_tech), Computer Science (cse), and Physics (phy).
* The dataset can be downloaded from the Shared Task's website. The training and validation split is as follows:

|Label|Training Data|Validation Data|
|:-------|:--------|:-------|
|Bio-Chemistry (bioche)|5,002|420|
|Communication Technology (com_tech)|17,995|1,505|
|Computer Science (cse)|9,344|885|
|Physics (phy)|9,656|970|
|**Total**|**41,997**|**3780**|


### Machine learning results:

|Model|Input Features|Validation Accuracy|Average F1-Score|
|:-------|:--------|:-------|:--------|
|Multinomial Naive Bayes|<p>BoW<br>char-BoW<br>TF-IDF<br>n-gram TF-IDF<br>character n-gram TF-IDF</p>|<p>86.74<br>81.61<br>77.16<br>61.98<br>76.93</p>|<p>0.8532<br>0.8010<br>0.7251<br>0.5138<br>0.7329</p>|
|Linear SVC|<p>BoW<br>char-BoW<br>TF-IDF<br>n-gram TF-IDF<br>character n-gram TF-IDF<br>Indic-fasttext embeddings(mean)<br>Indic-fasttext embeddings(TF-IDF)<br>Domain-Specific fasttext Embeddings(mean)<br>Domain-Specific fasttext Embeddings(TF-IDF)</p>|<p>85.76<br>86.19<br>88.17<br>87.27<br>88.78<br>79.20<br>77.67<br>85.44<br>85.42</p>|<p>0.8435<br>0.8467<br>0.8681<br>0.8614<br>0.8757<br>0.7691<br>0.7513<br>0.8419<br>0.8414</p>|



### Deep learning results:

|Model|Input Features|Validation Accuracy|Average F1-Score|
|:-------|:--------|:-------|:--------|
|FFNN|<p>fasttext embeddings<br>Indic-fasttext embeddings<br>Domain specific fasttext embeddings</p>|<p>59.39<br>71.50<br>76.11</p>|<p>0.4475<br>0.6929<br>0.7462<br>0.7454</p>|
|CNN|<p>fasttext embeddings<br>Indic-fasttext embeddings<br>Domain specific fasttext embeddings</p>|<p>72.59<br>77.08<br>86.66</p>|<p>0.7024<br>0.7514<br>0.8312<br>0.8532</p>|
|Bi-LSTM|<p>fasttext embeddings<br>Indic-fasttext embeddings<br>Domain specific fasttext embeddings</p>|<p>80.00<br>83.12<br>89.31</p>|<p>0.7870<br>0.8215<br>0.8629<br>0.8842</p>|
|BiLSTM-CNN|Domain specific fasttext embeddings|88.99|0.8807|
|BiLSTM-Attention|Domain fasttext specific embeddings|88.14|0.8697|
|Serial BiLSTM-CNN + Attention|Domain fasttext specific embeddings|88.23|0.8727|
|**Enemble CNN-BiLSTM + Attention**|**Domain fasttext specific embeddings**|**89.57**|**0.8875**|
