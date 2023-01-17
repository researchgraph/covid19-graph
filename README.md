# covid19-graph

Apply Non-Negative Matrix Factoriazation(NMF) topic modelling to COVID research articles.

## About program code

Step1. Data preprocessing.ipynb
  - Load covid articles JSON files
  - Merge into one dataframe
  - Preprocess text in the articles' title
  - Save the preprocessed text data as csv file

Step2. Extract Features.ipynb
- Read preprocessed text data
- Train word2vec model with the preprocessed text data
- Vectorize the text data into TF-IDF matrix

Step3. Apply topic modelling (NMF).ipynb
- Identify the optimal topic size by computing coherence scores with word2vec model
- Apply NMF topic modelling with the optimal topic size
- Explore the results
