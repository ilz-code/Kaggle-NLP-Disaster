# Kaggle-NLP-Disaster  
Problem description  
-------------------  
Task is to analyze texts from Twitter and determine if there is anouncing emergency or disaster, or not.  
The words contained in each tweet are a good indicator of whether they're about a real disaster or not.  
The presence of particular word (or set of words) in a tweet might link directly to whether or not that tweet is real.  

Exploratory Data Analysis  
-------------------------  
In given dataset, there are two csv files: train and test.  
Train dataset has 7631 entries, test 3263. Most important columns are 'text' and 'target'.  
Text should be analyzed, but target indicates, if there is disaster anounced (1) or not (0).  
Count of non-null in text and target columns is the same as length of dataframe. Also there are no duplicates. 
Additional columns ('keyword' and 'location' have many NaN, therefore those are not suitable for analyze.  
Data preprocessing includes tokenizer and converting to sequences.  

Model architecture  
------------------  
Model contains:  
input layer,  
2 LSTM layers,  
Dropout,  
Flatten,  
Dense with activation 'relu',  
Dropout,  
Dense with 'relu' activation  
and output: Dense with sigmoid activation  

Results and conclusions  
-----------------------
I run model fitting with 100 epochs, but with early stopping. Although model accuracy improves for train data, for validation data there were no significant improvements after approximately 20 epochs, and after 31 epoch fitting was stopped by early stopping.  
Final accuracy for validation data was 0.7945, but from Kaggle 0.78516
