# covid19-graph

Apply Non-Negative Matrix Factoriazation(NMF) topic modelling to COVID research articles.

## About program code

** Step1. Data preprocessing.ipynb **
Load JSON file and preprocess text data.
INPUT: data/search_results/search_results.json.zip
OUTPUT: data/processed_data/processed_data.tsv


** Step2. Extract Features.ipynb **
Convert preprocessed data into TF-IDF matrix and train a word2vec model.
INPUT: data/processed_data/processed_data.tsv
OUTPUT: 
- data/extracted_features/covid_100d.model
- data/extracted_features/vocid_100d.txt
- data/extracted_features/covid_tfidf_d.pkl
- data/extracted_features/covid_tfidf_v.pkl

** Step3. Apply topic modelling (NMF).ipynb **
Apply NMF topic modelling and produce outputs in JSON format.
INPUT: 
- data/processed_data/processed_data.tsv
- data/extracted_features/covid_100d.model
- data/extracted_features/covid_tfidf_d.pkl
- data/extracted_features/covid_tfidf_v.pkl
OUTPUT: 
- data/dataset/*.json
- data/technical_validation/*.csv
