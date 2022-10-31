# covid19-graph

Apply Non-Negative Matrix Factoriazation(NMF) topic modelling to COVID research articles.

## About program code

Step1. Data preprocessing.ipynb
  - Load covid articles JSON files
  - Merge into one dataframe
  - Preprocess text in the articles' title and abstract
  - Save the preprocessed text data as csv file

Step2. Word2vec Model Generation.ipynb
- Train word2vec model with the preprocessed covid article data
- Save the trained word2vec model

Step3. Apply topic modelling (NMF).ipynb
- Convert the article text into tfidf matrix
- Identify the optimal topic size by computing coherence scores with word2vec model
- Apply NMF topic modelling 
- Explore the results and save the outputs
