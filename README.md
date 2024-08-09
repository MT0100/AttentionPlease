Attention Please: Turkish NLP Project
This repository contains the code and notebooks related to the "Attention Please!" project, which is focused on Turkish Natural Language Processing (NLP). The project involves tasks such as sentiment analysis, named entity recognition (NER), and syntactic analysis using various models and tools.

Project Structure

web_service_attention_please.py: This is the main Python script that runs a FastAPI web service for performing sentiment analysis and named entity recognition on Turkish text. It integrates the Zemberek library for morphological analysis and uses Hugging Face Transformers for sentiment and NER tasks. We also pushed our models to huggingface. You can reach our sentiment model that we trained with our own dataset with model = AutoModelForSequenceClassification.from_pretrained("ikball/turkish-sentiment", from_tf=True);tokenizer = AutoTokenizer.from_pretrained("ikball/turkish-sentiment").
You can reach our entity ner model that we trained with our own dataset with model = AutoModelForTokenClassification.from_pretrained("mext741/turkish-ner-company");tokenizer = AutoTokenizer.from_pretrained("mext741/turkish-ner-company").
DATASET DESCRIPTIONS

Balanced_Sample_Sentiment_Dataset was used to train the model initially.

Unlabeled_Sentiment_Dataset was used as the test dataset after training.

high_confidence_predictions.csv: The dataset containing pseudo labels obtained after filtering predictions with an 80% confidence score.

high_confidence_predictions + Balanced_Sample_Sentiment_Dataset = merged_dataset.csv

Filtered_Sentiment_Dataset.csv: The final dataset.

If we do not filter the results based on an 80% confidence score:

predictions.csv: The dataset obtained without filtering.

predictions + Balanced_Sample_Sentiment_Dataset = Sentiment_Dataset, the final dataset.

companies.csv: A CSV file containing a list of company names, used in the NER task to identify and tag company entities in Turkish text.

MODELS

semisupervised_dataset.ipynb: A Jupyter Notebook that involves creating and processing a semi-supervised dataset for Turkish NLP tasks.

sentiment_analysis.ipynb: A Jupyter Notebook that details the sentiment analysis pipeline, including data preprocessing, model training, and evaluation.

ner.ipynb: Jupyter Notebooks (multiple versions) that describe the Named Entity Recognition (NER) pipeline, including model training and evaluation specific to Turkish text.

![image](https://github.com/user-attachments/assets/e402f4f4-2abd-420f-85e0-072c0bae2f32)




To install the required library Zemberek: https://drive.google.com/drive/u/0/folders/0B9TrB39LQKZWX1RSang3M1VkYjQ?resourcekey=0-uFoTlb0PoP0otWan6JkCLg
Select the latest version from this link and download or save the zemberek-full.jar file to your drive (don't forget to rename it back to zemberek-full.jar if you change the name).

How does it work?

First of all, the necessary libraries must be installed. These are: 
```
!pip install uvicorn,
!pip install fastapi,
!pip install pydantic,
!pip install jpype1,
!pip install transformers,
!pip install nltk,
!pip install pandas,
!pip install numpy.
```
By running these commands in order, the installation of the necessary libraries is completed.
Open a terminal and go to the location of the web_service_attention_please.py file with the cd command.
The web_service_attention_please.py file is run from the terminal.
Register and install UI from https://swagger.io/tools/swagger-ui/download/.
You can start location and sentiment analysis from your local host with the :8000 port and the /docs#/default/predict_predict__post extension.
