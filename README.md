# **News Detection System**

For training the model, dataset used is [Liar, Liar dataset](https://www.cs.ucsb.edu/~william/data/liar_dataset.zip)

The original dataset comes with following columns -
- Column 1: the ID of the statement ([ID].json)
- Column 2: the label
- Column 3: the statement
- Column 4: the subject(s)
- Column 5: the speaker
- Column 6: the speaker's job title
- Column 7: the state info
- Column 8: the party affiliation
- Column 9-13: the total credit history count, including the current statement
  - 9: barely true counts
  - 10: false counts
  - 11: half true counts
  - 12: mostly true counts
  - 13: pants on fire counts
- Column 14: the context (venue / location of the speech or statement)

For the simplicity, I have converted it to 2 column format (working of which is mentioned in dataset preprocessing):
- Column 1: Statement (News headline or text)
- Column 2: Label (Label class contains: True, False)
The labels have been reduced to 2 classes as for multi label classification ( with as much as 6 labels ) a huge dataset would be required for even considerable accuracy. Also *Liar, Liar dataset* is best dataset available for training these kinds of model. 


I have used [Google colaboratory](https://colab.research.google.com/) for designing this project of *News Detection System* using Natural Language Processing (NLP). If you want to create the same project either import one-by-one each file in order to it's next file or copy the whole code in one colab sheet and run.

For training models I considered these options-
- Naive Bayes
- Logistic Regression
- Support Vector Machine
- Random Forest

Techniques used are -
- **BOW** ( Bag of words )
- **N-grams**
- **POS** ( Parts of speech )
- **TF-IDF** ( Term frequency - Inverse document frequency )

For plots, I plotted 2 kinds of plot - 
- Learning Curve
- Precision-Recall Curve (PR - curve)
For balanced dataset it is better to use ROC curve but for moderately or highly imbalanced dataset it is better to use PR curves and thus I have used PR curve for visualization. 


#### Future work- ####
- As we know in the times like this the biggest source of hoaxes is whatsApp so to make this project a bit more powerfull we cann connect it with Twilio WhatsApp Sandbox with the help flask app, So that user can directly enter the news in the chat and get result there itself in his/her whatsApp inbox. [*Idea reference*](https://dzone.com/articles/fake-news-foe-machine-learning-and-twilio) 
- To use this system in times like this one should train the model on dataset related to corona virus news and that's how we can help the society right now by preventing the spread of rumours and verifying them in their initial stages only. I couldn't use required dataset as right now it's not available, only one dataset is available right now that's by [Poynter](https://www.poynter.org/ifcn-covid-19-misinformation/) but it is a multi lingual (40 languages) dataset. So one can use that to train the model also.
