# The Potential of Predicting Election Violence from Global News

Author: William Simpson \
Course: DATA606 - Capstone in Data Science \
Instructor: Professor Barber \
Term: Fall 2022

## Abstract
INTRODUCTION: Violent conflict in association with elections can reduce or corrupt electoral participation. Such destabilization of democracy, along with crises stemming from climate change, the COVID-19 pandemic, and violent armed conflict in Ukraine, have recently caused the first global decline in human development in over three decades. Understanding societal issues predicative of electoral violence could be useful for development policy making.

OBJECTIVES: The primary objective was to pilot a novel Machine Learning (ML) and Natural Language Processing methodology to predict election-related fatalities from news media text. 

METHODS: Salient risk factors of election-related violence were initially identified through ML modeling of historical elections from the dataset of National Elections Across Democracy and Autocracy (NELDA). The identified election violence-related risk factors were used to guide curation of a subset of global news articles from the Global Database of Events, Language, and Tone (GDELT). Articles reporting on the 2017 Kenya national election were used in a case study as input data suitable for predicting forthcoming fatalities. Subsequently, analysis of the curated news text at time T served in the Kenya election model to predict the level of election-related fatalities sourced from the Deadly Electoral Conflict Dataset (DECO) at time T+1.

RESULTS: Statistical comparison of ML performance identified the optimal conflict forecasting model. Support Vector Classifier predicted election-related fatalities above a threshold of 3 deaths up to 5 days in advance, achieving an Area Under the Receiver Operating Characteristic curve (AUC) equal to 0.77.

CONCLUSION: This research exemplifies the use of data science and ML for anticipatory policy making by forecasting specific characteristics of conflict associated with elections with the aim of minimizing the social and economic impacts of violence. 

## Code Descriptions
- Part 1: Risk Factors of Historical Election Violence
    - [Part_1_Final.ipynb](https://drive.google.com/file/d/1KapV--_BYZSyWGkZnyaBKKMYVkqyZviG/view?usp=share_link)
        - Conducts EDA of datasets
        - Preprocesses data for Model 1
        - Model 1 classifies historical elections by 3 levels of violence using fatalities from DECO as a metric
        - Outputs a list of the top most impactful risk factors of election violence based on historical global data of elections
- Part 2: Election Violence-related News
    - [Part_2A_Final_GDELT_GKG_download.ipynb](https://drive.google.com/file/d/1122iTWYGfbnPMTvdZwrPWB4Rb6bRFSSG/view?usp=share_link)
        - Downloads GDELT GKG 1.0 data from the GDELT GKG master list for a specified time frame and specified country 
        - Requires High-RAM VM or reduced batch size
    - [Part_2B_Final_GDELT_news_text_scraper.ipynb](https://drive.google.com/file/d/12nKphDaHXOMIfeoUVET_scq1kzfeUCLN/view?usp=share_link)
        - Custom news scraper to pull the text for news articles in GDELT GKG 1.0
        - For ~600,000 news articles, script runs approximately 200 compute hours (8 days) on a machine with 8 CPU cores
    - [Part_2C_Final_news_relevance.ipynb](https://drive.google.com/file/d/1GAkR4-1h1uVhyM9x-XZV3b1Sd8qEK9Ni/view?usp=share_link)
        - Filters GDELT GKG news data by articles similar to textual descriptions of the top risk factors of election violence identified in Part 1
- Part 3: Election Violence Prediction
    - [Part_3A_Final_BEST.ipynb](https://drive.google.com/file/d/1xB-FsQf59VYZ7TfxY5mwDJ30S6c9s16H/view?usp=share_link)
        - Search for the best model among defined parameter space (different number of days of news aggregated together, different thresholds of violence, different algorithms and hyperparameters
        - Faster if run on GPU 
    - [Part_3B_Final_Model_Performance_Statistical_Tests.ipynb](https://drive.google.com/file/d/1Ra9pvxtJt2Wga0P-WCmYVcYLInciSpU0/view?usp=share_link)
        - Conduct statistical analysis (Mann-Whitney U test) on the differences in performance from the models trained in Part 3A
    - [Part_3C_Final_Analysis.ipynb](https://drive.google.com/file/d/11_ThdQ9yFTdDvAspRaGAl1BOvse0da54/view?usp=share_link)
        - Trains the model with the best parameters determined in Part 3B
        - Conducts analysis of the results using t-SNE dimensionality reduction of news embeddings and topic modeling
        - Comparison of news in cases of correct model predictions vs incorrect predictions 
        - Comparison of news in period leading up to fatal violence, during violence, and outside contexts of fatal election violence 
        - Faster if run on GPU 
