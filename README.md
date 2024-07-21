# covid19-graph

Apply Non-Negative Matrix Factoriazation(NMF) topic modelling to COVID research articles.

## prerequisite

- Download "coronavirus_twenty_years_of_research" zip file from [COVID-19 Graph](https://liveswinburneeduau-my.sharepoint.com/:f:/r/personal/jihoonwoo_swin_edu_au/Documents/COVID-19%20Graph?csf=1&web=1&e=ltKZmv) upzip it in working directory. 

- Install required packages by using requirements.txt.

## About program process
**Step1. Data preprocessing.ipynb**
<sub>Load JSON file and preprocess text data.</sub>
- INPUT: 
  - coronavirus_twenty_years_of_research/search_results/covid_19.json
  - coronavirus_twenty_years_of_research/search_results/covid19.json
  coronavirus_twenty_years_of_research/search_results/sars_cov_2.json
- OUTPUT: coronavirus_twenty_years_of_research/technical_validation/merged_covid_articles.pkl

**Step2. Extract Features.ipynb**
<sub>Convert the preprocessed data into TF-IDF matrix and train a word2vec model.</sub>
- INPUT: coronavirus_twenty_years_of_research/technical_validation/merged_covid_articles.pkl
- OUTPUT: 
  - coronavirus_twenty_years_of_research/technical_validation/covid_100d.model
  - coronavirus_twenty_years_of_research/technical_validation/vocid_100d.txt
  - coronavirus_twenty_years_of_research/technical_validation/covid_tfidf_d.pkl
  - coronavirus_twenty_years_of_research/technical_validation/covid_tfidf_v.pkl

**Step3. Apply topic modelling (NMF).ipynb**
<sub>Apply NMF topic modelling and produce outputs in JSON format.</sub>
- INPUT: 
  - coronavirus_twenty_years_of_research/technical_validation/merged_covid_articles.pkl
  - coronavirus_twenty_years_of_research/technical_validation/covid_100d.model
  - coronavirus_twenty_years_of_research/technical_validation/covid_tfidf_d.pkl
  - coronavirus_twenty_years_of_research/technical_validation/covid_tfidf_v.pkl
- OUTPUT: 
  - coronavirus_twenty_years_of_research/technical_validation/NMF_topic_modelling_results(8clusters).csv

**Step4. Produce outputs of topic modelling.ipynb**
<sub>Read topic moding results and produce outputs in JSON format.</sub>
- INPUT: coronavirus_twenty_years_of_research/technical_validation/NMF_topic_modelling_results(8clusters).csv
- OUTPUT: coronavirus_twenty_years_of_research/clusters/cluster*/*.json

## About data directories
- The 'search_results' folder contains the extracted articles metadata.
- The 'clusters' folder is the core of our dataset that contains the classified articles into the eight clusters.
- The 'technical_validation' folder includes all csv files which are used to create figures in this paper.
- The 'time_lapse_visualization' folder contains a video that animates the cluster trends.
