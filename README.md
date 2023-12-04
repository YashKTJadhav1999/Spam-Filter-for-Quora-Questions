# Spam-Filter-for-Quora-Questions
Download data from here: https://www.dropbox.com/sh/kpf9z73woodfssv/AAAw1_JIzpuVvwteJCma0xMla?dl=0

Goal: Build a model for identifying if a question on Quora is spam 

Steps :
1. Initially the data preprocessing functionalities using data preprocessing functions like:
     1. Data cleaning using regex(Regular Expression).
     2. Lowercase translation.
     3. Tokenization.
     4. Stop word removal.
     5. Lemmetization.
     6. Joining the words in preprocessed questions.

2. Split the dataset shared into training and validation data.
3. Used the following models and compared the F1 scores and accuracy:
     Model_1: Using Bag Of Words(CountVectorizer) :
        Validation accuracy: 0.9270       Validation f1_score: 0.5412
   
     Model_2: TFIDF (Term Frequency Inverse Document Frequency) :
        Validation accuracy: 0.9379       Validation f1_score: 0.5113

     Model_3: Hashing Vectorizer:
        Validation accuracy: 0.8696       Validation f1_score: 0.2697

5. With the necessary preprocessing steps, first train a Bidirectional GRU model.
6. Then without using any pre-trained word embeddings fpr this Bidirectional GRU model, the best threshold f1_score was found to be 0.25 with an accuracy score of 0.6405.
7. Pretrained Embedding 1: Now repeat step 4 and train a Bidirectional GRU model with "GloVe Embeddings", the best threshold for f1_score was found to be 0.38 with an accuracy score of 0.6723.
8. Pretrained Embedding 2: Now repeat step 4 and train a Bidirectional GRU model with "Wiki News FastText Embeddings", the best threshold for f1_score was found to be 0.32 with an accuracy score of 0.6638.
9. The final blend was with 0.70*(predicted values of GloVe Embeddings) + 0.30*(predicted values of Wiki Embeddings).
10. The best threshold for f1_score was found to be 0.37 with an accuracy score pf 0.6747.
