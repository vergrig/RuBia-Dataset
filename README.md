# RuBia-Dataset
Bias detection dataset for the Russian language. 

**The rubia.tsv file contains the final version of the dataset.**

# Structure of this repo

## Main Folder: 
* rubia.tsv - contains the examples included in the dataset
* scored_data.tsv - contains the examples and PPL scores of nine LMs on the examples

## Analysis
* Preprocess.ipynb - data preprocessing and aggregating validation results
* Model_Scoring.ipynb - scoring nine LMs on the dataset using [lmppl library](https://github.com/asahi417/lmppl) by @asahi417
* lmppl-main.zip - code of the library modified to work with the chosen models
* statistics.tsv - a table containing raw scoring results
