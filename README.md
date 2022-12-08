# The Potential of Predicting Election Violence from Global News

Author: William Simpson \
Course: DATA606 - Capstone in Data Science \
Instructor: Professor Barber \
Term: Fall 2022

## Abstract
Multiple confounding crises ranging from climate change, the COVID-19 pandemic, and violent armed conflict in Ukraine have recently caused a global decline in human development for the first time in over three decades (Conceição, 2022). Conflict disrupts elections, which are foundational to a functioning democracy, reducing or corrupting electoral participation and destabilizing democracies (Norris, 2014). This research advances Machine Learning (ML) and Natural Language Processing (NLP) approaches for predictive conflict modeling by employing a novel methodology to predict election-related fatalities during Kenya’s 2017 national elections using features of global news from the Global Database of Events, Language, and Tone (GDELT). The current study consists of three stages: Part 1 builds a ML model to identify the most important risk factors of election-related violence across historical elections globally; Part 2 curates a dataset of global news articles that discuss the top election violence risk factors identified in Part 1; From this curated news data, Part 3 uses the news text at time T to predict the presence of election related fatalities at time T+1. Reported results are comparable to similar research (Mueller & Rauh, 2018; 2022), measured by the area under the Receiver Operator Curve equal to 0.77. This research exemplifies the use of data science and ML for anticipatory policy making by forecasting specific characteristics of conflict with the aim of minimizing the social and economic impacts of violence. 

## Code Descriptions
- Part 1: Risk Factors of Historical Election Violence
    - Part_1_Final.ipynb
        - Conducts EDA of datasets
        - Preprocesses data for Model 1
        - Model 1 classifies historical elections by 3 levels of violence using fatalities from DECO as a metric
        - Outputs a list of the top most impactful risk factors of election violence based on historical global data of elections
- Part 2: Election Violence-related News
    - Part_2A_Final_GDELT_GKG_download.ipynb
        - Downloads GDELT GKG 1.0 data from the GDELT GKG master list for a specified time frame and specified country 
        - Requires High-RAM VM or reduced batch size
    - Part_2B_Final_GDELT_news_text_scraper.ipynb
        - Custom news scraper to pull the text for news articles in GDELT GKG 1.0
        - For ~600,000 news articles, script runs approximately 200 compute hours (8 days) on a machine with 8 CPU cores
    - Part_2C_Final_news_relevance.ipynb
        - Filters GDELT GKG news data by articles similar to textual descriptions of the top risk factors of election violence identified in Part 1
- Part 3: Election Violence Prediction
    - Part_3A_Final_BEST.ipynb
        - Search for the best model among defined parameter space (different number of days of news aggregated together, different thresholds of violence, different algorithms and hyperparameters
        - Faster if run on GPU 
    - Part_3B_Final_Model_Performance_Statistical_Tests.ipynb
        - Conduct statistical analysis (Mann-Whitney U test) on the differences in performance from the models trained in Part 3A
    - Part_3C_Final_Analysis.ipynb
        - Trains the model with the best parameters determined in Part 3B
        - Conducts analysis of the results using t-SNE dimensionality reduction of news embeddings and topic modeling
        - Comparison of news in cases of correct model predictions vs incorrect predictions 
        - Comparison of news in period leading up to fatal violence, during violence, and outside contexts of fatal election violence 
        - Faster if run on GPU 
