# RuBia-Dataset
Bias detection dataset for the Russian language.

The rubia.tsv file contains the final version of the dataset.

<img src="/Misc/structure.jpg" alt="Dataset Structure" title="Dataset Structure">

# Structure of this repo

## Main Folder 
* *rubia.tsv* - contains the examples included in the dataset
* *scored_data.tsv* - contains the examples and PPL scores of nine LMs on the examples

## Analysis
Contains files related to processing the data and running the experiments
* *Preprocess.ipynb* - data preprocessing and aggregating validation results
* *Model-Scoring.ipynb* - scoring nine LMs on the dataset using [lmppl library](https://github.com/asahi417/lmppl) by @asahi417
* *lmppl-main.zip* - code of the library modified to work with the chosen models
* *statistics.tsv* - a table containing raw scoring results

## Data-Collection
Contains files related to data collection and the Telegram bot
* *Bot-Runtime.ipynb* - code of the response collection Telegram bot
* *config.json* - config for the bot. Includes:
  *  paths to files with interface messages (greeting message, error message, etc.)
  *  path to the location where responses should be stored
  *  bot ids (validator bot id field can be left empty as the validator bot is strictly auxiliary)
  *  lists of domains, tasks included in each domain and their relative frequencies (if one task has freq 1 and another has freq 2, the second will be shown twice as often)
*  *tasks* - a folder containing txt files with tasks for different subdomains
*  *interface* - a folder containing txt files with interface messages

## Data-Validation
Contains files related to data validation using Toloka. Each file contains text instructions for validation of a subdomain or a group of subdomains. Subdomains are split into two types - those that contain mostly direct stereotyping and those that contain mostly representational bias. LGBTQ+ domain was not validated.
* *Type-1-Ru* - contains files with questions for each domain, relevant for:
  * all subdomains of the nationality domain
  * freeform_full (Freform) and template_assoc (Common Stereotypes) subdomains of the gender domain
  * template_poor and template_rich (Common Stereotypes), freeform_full (Freeform), freeform_prof (Professional Status)
* *Type-1-Translated* - contains files with English translations of the instructions. They are given in a more readable format, not immediately compatible with Toloka
