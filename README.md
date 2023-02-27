# covid19-graph

Apply Non-Negative Matrix Factoriazation(NMF) topic modelling to COVID research articles.

## prerequisite

- Download "search_results.json.zip" file from ... and save into 'data/search_results/' directory.
- Install required packages by using requirements.txt.

## About program process
**Step1. Data preprocessing.ipynb**
<sub>Load JSON file and preprocess text data.</sub>
- INPUT: data/search_results/search_results.json.zip
- OUTPUT: data/processed_data/processed_data.tsv

**Step2. Extract Features.ipynb**
<sub>Convert preprocessed data into TF-IDF matrix and train a word2vec model.</sub>
- INPUT: data/processed_data/processed_data.tsv
- OUTPUT: 
  - data/extracted_features/covid_100d.model
  - data/extracted_features/vocid_100d.txt
  - data/extracted_features/covid_tfidf_d.pkl
  - data/extracted_features/covid_tfidf_v.pkl

**Step3. Apply topic modelling (NMF).ipynb**
<sub>Apply NMF topic modelling and produce outputs in JSON format.</sub>
- INPUT: 
  - data/processed_data/processed_data.tsv
  - data/extracted_features/covid_100d.model
  - data/extracted_features/covid_tfidf_d.pkl
  - data/extracted_features/covid_tfidf_v.pkl
- OUTPUT: 
  - data/dataset/*.json
  - data/technical_validation/*.csv
