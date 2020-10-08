# Classification of amazon fine food reviews Using NLP transfer Learning - BERT base model
----

### Objective:
Given a restaurant review, determine the sentiment of the review whether its positive or negative using Pre trained Bert base model.

### Data:
--> https://www.kaggle.com/snap/amazon-fine-food-reviews
This dataset consists of reviews of fine foods from amazon. The data span a period of more than 10 years, including all ~500,000 reviews up to October 2012. Reviews include product and user information, ratings, and a plain text review. It also includes reviews from all other Amazon categories.

### Summary 
---
---
---
*  removed null elements and removed html tags from the dataset.
*  Changed ratings into 0 and 1. '0' - rating 1 & 2, '1' - ratings 4 & 5.
*  Removed rating 3 from the dataset.
*  Considered sample of 100000 rows from the dataset.
*  After that we perform Train and test split.
---
*  Creating bert model with maaximum length of input words as 55.
*  Then we tokenize original sentence using tokenizer python file.
*  we then pad sentences for the text in the dataset, pre padding is done for both test and train dataset.
*  Then we will append tokens - [CLS] & [SEP] to the start and end respectively to each sentence in the dataset.
*  For bert input model we need three parameters such as input tokens, input mask, input segments.
* INput tokens will be the sentence tokens created,mask will be the zeros where [PAD] is and others will be zero and segment is the size of max length text fixed with zeroes in it. these paramters is then converted into array format. 
---
* Getting Embeddings from BERT Model.
* we have already created a bert model and creted input tokens,mask and segments for the bert model.
* Now we will get the embedding vectors for each train and test dataset from bert model.
* we are using bert base so our output of [cls] will be of size - 768.
* at the end we will get the pooled output from bert model of shape(None,768)
---
* Then we will train a neural network with some dense layers and dropouts, input of this neural network is the embeddings from the bert model(Pooled output).
* We will train that neural network with the trained pool outputs from the bert model.
* Metrics considered is AUC in this model. We will train it for 10 epochs and the validation auc is around 95%.
---
* We than have a seperate test dataset with text and ratings in it.
* we follow the same  pipeline as training dataset, we preprocess and get pooled output from bert model.
* we then pass this pooled output of size(None, 768) to the NN model which has been trained before.
* Prediction is got from model predict funtion and is displayed at the end.
---
---
---



