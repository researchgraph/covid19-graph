# covid19-graph

Apply Non-Negative Matrix Factoriazation(NMF) topic modelling to COVID research articles.

## prerequisite

- Download "coronavirus_twenty_years_of_research" zip file from [COVID-19 Graph](https://liveswinburneeduau-my.sharepoint.com/:f:/r/personal/jihoonwoo_swin_edu_au/Documents/COVID-19%20Graph?csf=1&web=1&e=ltKZmv) and copy 'search_results' folder from the zip file and paste to the 'data/'  directory.
- Install required packages by using requirements.txt.

## About program process
**Step1. Data preprocessing.ipynb**
<sub>Load JSON file and preprocess text data.</sub>
- INPUT: data/search_results/search_results.json
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
  - data/clusters/cluster*/*.json
  - data/technical_validation/*.csv
