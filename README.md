# Author-Features-NLP
Classified 10000 blog posts and matched them with the most probable author features such as name, gender, age, etc.
## 0. Software
-  Python version: 3.8
-  Libraries Used
    - Numpy
    - Pandas
    - Scikit-Learn
    - NLTK (pip installed, downloaded the 'punkt' corpus))   
## 1. Dataset: 
- Data set used: Blog Authorship Corpus
- The original dataset was large and consisted of over 600000 rows and 7 columns
- For the purpose of this project the number of rows was limited to 10000
- The dataset contains author features such as name, gender, age, etc. and one column of text written by each of the authors
## 2. Objective
- The objective of this project was to be able to classify features of an author by just looking at the text written.
- The project performed a multiclass classification wherein instead of trying to identify the specific author I tried to isolate the features of the authors and perform a binary classification for each of the features provided.
## 3. Text- Preprocessing
- Removed punctuation
- Removed trailing spaces
- Changed all text to lower case
- Stemmed the words using Porter Stemmer from the nltk library
## 4. Vectorizing the Text
- Only used the Count Vectorizer for maintaining simplicity
- Hyperparameters used for Count Vectorizer:
    - words can be taken individually or clubbed with one other word
    - words appearing in more than 75% of the documents can be skipped
    - words should appear in at least 3 documents to be included
    - limited stop words to only english
## 5. Model Building
- Model Used: Logistic Regression with the lbfgs solver
    - The number of iterations for the model was increased from the default 100 to 170 since the error variation was high between outputs futher resulting in the model to be unable to converge. 
- Multiclass Classification Model used: One vs Rest Classifier
## 6. Results
The model built provided the following results
- Accuracy:  0.32
- F1 Score:  0.64
- Precision:  0.75
- Recall:  0.56
Note: Since the labels were imbalanced micro average was taken to calculate F1 Score, Precision and Recall.

## 7. Conclusion
- The accuracy of the model was low but we need to keep in mind that the underlying data was imbalanced and accuracy would not be a very reliable metric
- The other metrics on the other hand provided a decent result 
- I believe including more data for this model would provide improve these results but since my laptop is not as equipped to handle more data I'm concluding this project here.

