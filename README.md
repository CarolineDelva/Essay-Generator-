
# Essay Generator (Natural Language Processing)

![NLP](data/NLP.jpeg)

#### -- Project Status: [Completed]


## Project Description

Writer’s block is incredibly inconvenient for professional writers. Tight deadlines and lack of inspiration are a few reasons why editors may have a difficult time producing compelling content. The objective of this project is to tackle this specific problem by creating an application that creates business and sports excerpts through an user interface. 

The dataset 

The dataset, Articles.csv is retrieved from Kaggle, which is an online community where data enthusiasts publish datasets, notebooks and participate in online data competitions. Datasets collected from this website are protected by copyright and other intellectual property laws, which means that downloaded datasets must be cited and must not be used for monetary gain. The Articles.csv was authored by Asad Mahmood, who is Research Assistant at University of Iowa.  It consists of articles scraped from The News, an international news platform.  It consists of the following columns: 
Article : text body 
Date:  12/31/2014 - 03/26/17
Heading: article titles 
NewsType: Topic either business and sports
This dataset is appropriate for this project because it only contains two categories of articles: Business and Sports. This will allow the scope of the project to not be too broad.  Users will be able to request excerpts that address business or sports.It also contains full articles of considerable length. The dataset needs a bit of cleaning to be even more appropriate for this work. HTML tags,  punctuation and space before processing. The text is encoded to ascii and decoded to utf-8. 

https://www.kaggle.com/asad1m9a9h6mood/news-articles/data?select=Articles.csv

Exploratory Analysis 

The dataset is split into sports and business articles to ensure that users receive sports or business essays when they make their requests. 
The entire dataset is fitted to a Countvectorizer to get the document frequency from all of the dataset. 
The  top most frequent words are generated from the business articles with the countvectorizer, which are “oils, percent, pakistan, prices, million” . These words are consistent with what you would expect from a business article and demonstrate that the tokenizer removes the stop words and non-alphanumeric characters. 
The most frequent words are generated from the sports section, which are “pakistan, test, match, world, england”. These top words are also consistent with what you would expect from a sports article and demonstrate that the tokenizer removes the stop words and non-alphanumeric characters.  
The most informative terms are generated from the business articles using the TF-IDF vectorizer to determine which terms are the most informative. 
The most informative terms are generated from the sports articles using the TF-IDF vectorizer to determine which terms are the most informative.
Topics are  generated using NMF and LDA on both the sports articles and business articles
Methodology 
The dataset will be split into train, validation and test sets.
The methodology is a character-lever text generation. According to the research, a  character-level text generation model ( one-hot encoding) is easier to train on short corpora than a word-level text generation model (word embeddings) because the vocabulary is smaller, the representation is less, and the model requires less memory. 
This is accomplished by finding the distinct characters for each category: business and sports. The characters are transformed into integers that are turned into one hot encoding. The one hot encodings will then be inputted into a Keras LSTM  model. In sum, The user will be able to input a seed sentence and they will receive a text. 
A word-level text generation model will also be explored to determine which model would produce better essays.
Deployment strategy
The model will be deployed using a flask application. The necessary files will be:
 HTML/CSS : this files define the frontend interface where the user will be able to request the essay 
Model.py : this file will contain the trained well performing model that will produce the new essay
App.py: This file will contain the flask server that will have the main page, the predict and result functions 
Heroku files: The app will be deployed to Heroku so anyone can open it with the Heroku link 
				
Sources
https://towardsdatascience.com/how-to-easily-deploy-machine-learning-models-using-flask-b95af8fe34d4
https://machinelearningmastery.com/text-generation-lstm-recurrent-neural-networks-python-keras/
https://stackabuse.com/text-generation-with-python-and-tensorflow-keras/
https://machinelearningmastery.com/text-generation-lstm-recurrent-neural-networks-python-keras/

