# covid19-graph

Apply Non-Negative Matrix Factoriazation(NMF) topic modelling to COVID research articles.

## About program code

Step1. Data preprocessing.ipynb
  - Load covid articles JSON files
  - Merge into one dataframe
  - Clean articles' title and abstract
  - Save cleaned articles data as csv file

Step2. Explore Input Data.ipynb
- Read the cleaned covid articles file and exploe the data
  - Count number of articles without abstract
  - Count number of articles published by month
  - Identify the top publishers, subjects, container titles, and funders in the data.

Step3. Word2vec Model Generation.ipynb
- Train word2vec model with the cleaned covid article data

Step4. Apply topic modelling (NMF).ipynb
- Convert the article text data into tfidf matrix
- Identify the optimal topic size by computing coherence scores
- Apply NMF topic modelling 
- Explore the results and save the outputs
